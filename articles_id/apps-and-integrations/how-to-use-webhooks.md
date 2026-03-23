# Cara Menggunakan Webhook

Webhook adalah callback HTTP yang diatur untuk setiap akun. Ini dipicu saat tindakan seperti membuat pesan terjadi di Katalis. Beberapa webhook bisa dibuat untuk satu akun.

## Cara Menambahkan Webhook

**Langkah 1.** Buka Settings → Integrations → Webhooks. Klik tombol "Configure".

**Langkah 2.** Klik tombol "Add new webhook". Modal akan terbuka. Di sini, masukkan URL tempat permintaan POST harus dikirim. Selanjutnya, Anda perlu memilih event yang ingin Anda langgani. Opsi ini memungkinkan Anda hanya mendengarkan event yang relevan di Katalis.

Katalis akan mengirim permintaan POST dengan payload berikut ke URL yang dikonfigurasi untuk berbagai pembaruan di akun Anda.

### Contoh Payload Webhook

```json
{
  "event": "message_created",
  "id": "1",
  "content": "Hi",
  "created_at": "2020-03-03 13:05:57 UTC",
  "message_type": "incoming",
  "content_type": "enum",
  "content_attributes": {},
  "source_id": "",
  "sender": {
    "id": "1",
    "name": "Agent",
    "email": "[email protected]"
  },
  "contact": {
    "id": "1",
    "name": "contact-name"
  },
  "conversation": {
    "display_id": "1",
    "additional_attributes": {}
  },
  "account": {
    "id": "1",
    "name": "Katalis"
  }
}
```

## Event Webhook yang Didukung di Katalis

Katalis menerbitkan berbagai event ke endpoint webhook yang dikonfigurasi. Setiap event memiliki struktur payload berdasarkan jenis model yang mereka gunakan.

### Objek

Payload event mungkin menyertakan objek berikut: Account, Inbox, Contact, User, Conversation, Message.

### Event Webhook

- **conversation_created** — Dipicu saat percakapan baru dibuat di akun.
- **conversation_updated** — Dipicu saat ada perubahan atribut dalam percakapan. Termasuk `changed_attributes`.
- **conversation_status_changed** — Dipicu saat status percakapan diubah.
- **message_created** — Dipicu saat pesan dibuat dalam percakapan.
- **message_updated** — Dipicu saat pesan diperbarui dalam percakapan.
- **webwidget_triggered** — Dipicu saat pengguna akhir membuka widget live-chat.
- **conversation_typing_on** — Dipicu saat agen mulai mengetik. Flag `is_private` membedakan antara catatan privat dan pesan ke pelanggan.
- **conversation_typing_off** — Dipicu saat agen berhenti mengetik atau meninggalkan jendela percakapan.

## Memverifikasi Webhook

Katalis menandatangani setiap permintaan webhook keluar sehingga server Anda bisa memverifikasi bahwa payload dikirim oleh Katalis dan belum diubah. Rahasia ditampilkan kepada Anda saat webhook dibuat, dan Anda bisa melihatnya kembali di formulir edit webhook.

Setiap permintaan webhook mengirim header berikut, yang bisa digunakan untuk menghitung tanda tangan HMAC dari payload:

- `X-Katalis-Signature`: Tanda tangan HMAC-SHA256 dengan prefix `sha256=`
- `X-Katalis-Timestamp`: Unix timestamp (detik) saat permintaan ditandatangani
- `X-Katalis-Delivery`: ID pengiriman unik untuk event webhook (jika tersedia)

Tanda tangan dihitung sebagai:

```
sha256=HMAC-SHA256(webhook_secret, "{timestamp}.{raw_body}")
```

### Langkah Verifikasi

1. Ekstrak `X-Katalis-Signature` dan `X-Katalis-Timestamp` dari header permintaan
2. Baca body permintaan mentah sebagai bytes (jangan parse dan re-serialize)
3. Hitung tanda tangan yang diharapkan: `sha256=HMAC-SHA256(secret, "{timestamp}.{raw_body}")`
4. Bandingkan tanda tangan yang dihitung dengan tanda tangan yang diterima menggunakan perbandingan constant-time
5. Opsional, tolak permintaan di mana timestamp terlalu lama untuk mencegah serangan replay

### Contoh Verifikasi

**Ruby:**
```ruby
def verify_signature(raw_body, timestamp, received_signature, secret)
  expected = "sha256=#{OpenSSL::HMAC.hexdigest('SHA256', secret, "#{timestamp}.#{raw_body}")}"
  ActiveSupport::SecurityUtils.secure_compare(expected, received_signature)
end
```

**Python:**
```python
import hmac, hashlib

def verify_signature(raw_body, timestamp, received_signature, secret):
    message = f"{timestamp}.".encode() + raw_body
    expected = "sha256=" + hmac.new(secret.encode(), message, hashlib.sha256).hexdigest()
    return hmac.compare_digest(expected, received_signature)
```

**Node.js:**
```javascript
const crypto = require("crypto");

function verifySignature(rawBody, timestamp, receivedSignature, secret) {
  const message = `${timestamp}.${rawBody}`;
  const expected = "sha256=" + crypto.createHmac("sha256", secret).update(message).digest("hex");
  return crypto.timingSafeEqual(Buffer.from(expected), Buffer.from(receivedSignature));
}
```

### Catatan Penting

- Selalu gunakan body permintaan mentah untuk verifikasi. Mem-parse JSON dan me-re-serialize mungkin mengubah urutan key, whitespace, atau unicode escaping yang akan menghasilkan tanda tangan berbeda.
- Selalu gunakan perbandingan constant-time untuk mencegah serangan timing.
