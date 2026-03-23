# Cara Menyiapkan Koneksi WebSocket

WebSocket membangun koneksi berkelanjutan antara klien dan server, memungkinkan komunikasi dua arah. Katalis menggunakan koneksi ini untuk menyediakan pembaruan real-time tentang event platform. Untuk terhubung ke WebSocket Katalis, cukup berikan token dan ikuti instruksi pengaturan yang diuraikan dalam panduan ini.

**Catatan:** Fitur ini bersifat eksperimental, dan dokumentasi mungkin berubah dengan setiap rilis. Selain itu, kompatibilitas mundur tidak dapat dijamin, jadi penting untuk memastikan Anda menggunakan versi implementasi terbaru.

## Mengapa Saya Harus Menggunakan Koneksi WebSocket?

Koneksi WebSocket memungkinkan pembaruan data real-time, menjadikannya ideal untuk klien seperti SDK Android atau iOS untuk Katalis. Ini membantu memperbarui dashboard tanpa perlu memuat ulang halaman. Oleh karena itu, ini bisa meningkatkan pengalaman pengguna dan meningkatkan produktivitas agen.

## Cara Menyiapkan Koneksi WebSocket dengan Katalis

Untuk menyiapkan koneksi WebSocket dengan Katalis, Anda perlu memulai koneksi dengan PubSub token autentikasi yang disediakan oleh Katalis. URL untuk koneksi adalah `wss://<url-instalasi-anda>/cable`. Jika menggunakan Katalis Cloud, Anda bisa menggunakan `wss://app.katalis.app/cable` sebagai URL.

PubSub token adalah token yang digunakan untuk mengautentikasi klien saat menghubungkan ke layanan PubSub (publish-subscribe). Klien harus menunjukkan token ini ke layanan untuk membangun koneksi dan mulai mempublikasikan atau berlangganan pesan.

Ada dua jenis PubSub token yang tersedia di Katalis:

1. **User PubSub Token**: Token ini memiliki hak agen/admin dan akan menerima semua event yang tercantum di halaman ini. Anda bisa mendapatkan PubSub token dengan memanggil Profile API.

2. **Contact PubSub Token**: Katalis menghasilkan PubSub token unik untuk setiap sesi yang dimiliki kontak. Token ini bisa digunakan untuk terhubung ke WebSocket dan menerima pembaruan real-time untuk sesi yang sama. Saat kontak dibuat melalui API publik, `pubsub_token` disertakan dalam payload respons. Token ini hanya memberikan akses ke event yang terkait dengan sesi saat ini, seperti `conversation.created`, `conversation.status_changed`, `message.created`, `message.updated`, `conversation_typing_on`, `conversation_typing_off`, dan `presence.update`.

Silakan merujuk ke Client API untuk membangun integrasi real-time yang menghadap pelanggan menggunakan Katalis.

**Catatan:** Token ini mungkin dirotasi secara berkala berdasarkan jenis instalasi Anda. Pastikan Anda menggunakan token terbaru.

## Cara Menghubungkan ke WebSocket Katalis

Untuk terhubung ke WebSocket Katalis, gunakan perintah `subscribe` dan sertakan `pubSubToken`, `accountId`, dan `userId` (jika menggunakan token user) dalam permintaan koneksi. Berikut contoh cara Anda bisa terhubung dengan Katalis:

```javascript
const stringify = (payload = {}) => JSON.stringify(payload);

const pubSubToken = "<contact/user-pub-sub-token>";
const accountId = "<your-account-id-in-integer>";
const userId = "<user-id-in-integer-if-using-user-token>";
const connection = new WebSocket("wss://app.katalis.app/cable");

connection.send(
  stringify({
    command: "subscribe",
    identifier: stringify({
      channel: "RoomChannel",
      pubsub_token: pubSubToken,
      account_id: accountId,
      user_id: userId,
    }),
  })
);
```

## Mempublikasikan Presence ke Server WebSocket

Untuk menjaga status pengguna tetap online di Katalis, Anda bisa mengirim event pembaruan presence ke Katalis setiap 30 detik. Tindakan ini akan menjaga status agen/kontak tetap online.

### Cara Memperbarui Presence Agen/Admin

```javascript
const userPayload = stringify({
  command: "message",
  identifier: stringify({
    channel: "RoomChannel",
    pubsub_token: "<user-pubsub-token>",
    account_id: accountId,
    user_id: userId,
  }),
  data: stringify({ action: "update_presence" }),
});

connection.send(userPayload);
```

### Cara Memperbarui Presence Kontak

```javascript
const agentPayload = stringify({
  command: "message",
  identifier: stringify({
    channel: "RoomChannel",
    pubsub_token: "<user-pubsub-token>",
  }),
  data: stringify({ action: "update_presence" }),
});

connection.send(agentPayload);
```

## Payload WebSocket

### Objek

Event bisa berisi salah satu objek berikut sebagai payload. Berbagai jenis objek yang didukung di Katalis adalah sebagai berikut.

### Conversation

Payload berikut akan dikembalikan untuk percakapan:

```json
{
  "additional_attributes": {
    "browser": {
      "device_name": "string",
      "browser_name": "string",
      "platform_name": "string",
      "browser_version": "string",
      "platform_version": "string"
    },
    "referer": "string",
    "initiated_at": {
      "timestamp": "iso-datetime"
    }
  },
  "can_reply": "boolean",
  "channel": "string",
  "id": "integer",
  "inbox_id": "integer",
  "messages": ["Array of message objects"],
  "status": "string",
  "unread_count": "integer",
  "agent_last_seen_at": "unix-timestamp",
  "contact_last_seen_at": "unix-timestamp",
  "timestamp": "unix-timestamp",
  "account_id": "integer"
}
```

### Contact

```json
{
  "additional_attributes": "object",
  "custom_attributes": "object",
  "email": "string",
  "id": "integer",
  "identifier": "string or null",
  "name": "string",
  "phone_number": "string or null",
  "thumbnail": "string"
}
```

### User

```json
{
  "id": "integer",
  "name": "string",
  "available_name": "string",
  "avatar_url": "string",
  "availability_status": "string",
  "thumbnail": "string"
}
```

### Message

```json
{
  "id": "integer",
  "content": "string",
  "account_id": "integer",
  "inbox_id": "integer",
  "message_type": "integer",
  "created_at": "unix-timestamp",
  "updated_at": "datetime",
  "private": "boolean",
  "status": "string",
  "source_id": "string / null",
  "content_type": "string",
  "content_attributes": "object",
  "sender_type": "string",
  "sender_id": "integer",
  "sender": {
    "type": "string - contact/user"
  }
}
```

### Notification

```json
{
  "id": "integer",
  "notification_type": "string",
  "primary_actor_type": "string",
  "primary_actor_id": "integer",
  "read_at": "unix-timestamp",
  "secondary_actor": "object/null",
  "created_at": "unix-timestamp",
  "account_id": "integer",
  "push_message_title": "string"
}
```

## Jenis Event

### conversation.created
Event ini dipicu saat percakapan baru dimulai. Tersedia untuk: agent/admin, contact

### conversation.read
Event ini dipicu saat kontak telah membaca pesan. Tersedia untuk: agent/admin

### message.created
Event ini dipicu saat pesan baru dibuat dalam percakapan. Tersedia untuk: agent/admin, contact

### message.updated
Event ini dipicu saat pesan diperbarui dalam percakapan. Tersedia untuk: agent/admin, contact

### conversation.status_changed
Event ini dikirim saat status percakapan diperbarui. Tersedia untuk: agent/admin, contact

### conversation.typing_on
Event ini dikirim saat kontak atau agen mulai mengetik respons. Tersedia untuk: agent/admin, contact

### conversation.typing_off
Event ini dikirim saat kontak atau agen selesai mengetik respons. Tersedia untuk: agent/admin, contact

### assignee.changed
Event ini dikirim saat agen yang ditugaskan diubah. Tersedia untuk: agent/admin

### team.changed
Event ini dikirim saat tim yang ditugaskan diubah. Tersedia untuk: agent/admin

### conversation.contact_changed
Event ini dikirim saat dua kontak digabungkan dan semua percakapan dikonsolidasikan di bawah satu kontak. Tersedia untuk: agent/admin

### contact.created
Event ini dikirim saat kontak dibuat. Tersedia untuk: agent/admin

### contact.updated
Event ini dikirim saat kontak diperbarui. Tersedia untuk: agent/admin

### presence.update
Event ini menyediakan pembaruan real-time tentang status ketersediaan pengguna dalam sistem. Tersedia untuk: agent/admin, contact

### notification_created
Event ini dikirim saat notifikasi dibuat. Tersedia untuk: agent/admin
