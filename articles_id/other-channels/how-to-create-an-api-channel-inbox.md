# Cara Membuat Inbox Channel API

Untuk membuat dan mengonfigurasi inbox channel API di instalasi Katalis.app, ikuti langkah-langkah yang dijelaskan di bawah ini.

## Menyiapkan Channel API

**Langkah 1.** Buka Settings → Inboxes → "Add Inbox".

**Langkah 2.** Klik ikon "API".

**Langkah 3.** Berikan nama untuk channel dan Callback URL. Berikut contohnya:

**Langkah 4.** "Add agents" ke inbox API Anda.

Pengaturan inbox selesai.

## Mengirim Pesan ke Channel API

Untuk mengirim pesan ke channel API, pastikan Anda memahami model dan tata nama yang digunakan di Katalis.app.

1. **Channel**: Channel mendefinisikan jenis sumber percakapan. Contoh: Facebook, Twitter, API, dll.

2. **Inbox**: Anda bisa membuat beberapa sumber percakapan dengan jenis channel yang sama. Contoh: Anda bisa memiliki lebih dari satu halaman Facebook yang terhubung ke akun Katalis.app. Setiap halaman disebut inbox di Katalis.app.

3. **Conversation**: Conversation adalah kumpulan pesan.

4. **Contact**: Setiap percakapan memiliki orang nyata yang terkait dengannya, yang disebut contact.

5. **Contact Inboxes**: Ini adalah sesi untuk setiap contact di inbox. Sebuah contact bisa memiliki beberapa sesi dan beberapa percakapan di inbox yang sama.

## Cara Mengirim Pesan di Channel API

Untuk mengirim pesan di channel API, buat contact, mulai percakapan, dan terakhir kirim pesan.

API memerlukan `api_access_token` di header permintaan. Anda bisa mendapatkan token ini dengan mengunjungi Profile settings → Access Token.

### 1. Membuat Contact

Ref: Dokumentasi API

Kirimkan inbox ID dari channel API beserta parameter lain yang ditentukan. Ini akan membuat sesi untuk Anda secara otomatis. Contoh respons akan terlihat seperti di bawah ini.

```json
{
  "email": "string",
  "name": "string",
  "phone_number": "string",
  "thumbnail": "string",
  "additional_attributes": {},
  "contact_inboxes": [
    {
      "source_id": "string",
      "inbox": {
        "id": 0,
        "name": "string",
        "website_url": "string",
        "channel_type": "string",
        "avatar_url": "string",
        "widget_color": "string",
        "website_token": "string",
        "enable_auto_assignment": true,
        "web_widget_script": "string",
        "welcome_title": "string",
        "welcome_tagline": "string",
        "greeting_enabled": true,
        "greeting_message": "string"
      }
    }
  ],
  "id": 0,
  "availability_status": "string"
}
```

Seperti yang bisa Anda lihat di payload, Anda akan bisa melihat `contact_inboxes` dan setiap `contact_inbox` akan memiliki `source_id`. Source ID dapat dianggap sebagai pengidentifikasi sesi. Anda akan menggunakan `source_id` ini untuk membuat percakapan baru seperti yang dijelaskan di bawah.

### 2. Membuat Percakapan

Ref: Dokumentasi API

Gunakan `source_id` yang diterima dari panggilan API sebelumnya. Anda akan menerima conversation ID yang bisa digunakan untuk membuat pesan.

```json
{
  "id": 0
}
```

### 3. Membuat Pesan Baru

Ref: Dokumentasi API

Ada 2 jenis pesan:

1. **Incoming**: Pesan yang dikirim oleh pengguna akhir diklasifikasikan sebagai pesan masuk.
2. **Outgoing**: Pesan yang dikirim oleh agen diklasifikasikan sebagai pesan keluar.

Jika Anda memanggil API dengan konten yang benar, Anda akan menerima payload serupa seperti ini:

```json
{
    "id": 0,
    "content": "This is a incoming message from API Channel",
    "inbox_id": 0,
    "conversation_id": 0,
    "message_type": 0,
    "content_type": null,
    "content_attributes": {},
    "created_at": 0,
    "private": false,
    "sender": {
        "id": 0,
        "name": "Pranav",
        "type": "contact"
    }
}
```

Jika semuanya berhasil, Anda akan melihat percakapan di dashboard seperti berikut.

Anda akan diberi notifikasi saat pesan baru dibuat di URL yang ditentukan saat membuat channel API. Anda bisa membaca tentang payload pesan di sini.

## Menerima Pesan Menggunakan Callback URL

Ketika pesan baru dibuat di channel API, Anda akan mendapatkan permintaan POST ke Callback URL yang ditentukan saat membuat channel API. Payload akan terlihat seperti ini.

Temukan daftar lengkap event yang didukung oleh webhook di sini.

Jenis event: `message_created`

```json
{
  "id": 0,
  "content": "This is a incoming message from API Channel",
  "created_at": "2020-08-30T15:43:04.000Z",
  "message_type": "incoming",
  "content_type": null,
  "content_attributes": {},
  "source_id": null,
  "sender": {
    "id": 0,
    "name": "contact-name",
    "avatar": "",
    "type": "contact"
  },
  "inbox": {
    "id": 0,
    "name": "API Channel"
  },
  "conversation": {
    "additional_attributes": null,
    "channel": "Channel::Api",
    "id": 0,
    "inbox_id": 0,
    "status": "open",
    "agent_last_seen_at": 0,
    "contact_last_seen_at": 0,
    "timestamp": 0
  },
  "account": {
    "id": 1,
    "name": "API testing"
  },
  "event": "message_created"
}
```

## Membuat Antarmuka Menggunakan Client API

Client API yang tersedia untuk channel API akan membantu Anda membangun antarmuka yang menghadap pelanggan untuk Katalis.app.

API ini berguna untuk kasus-kasus seperti yang tercantum di bawah ini:

1. Menggunakan antarmuka chat kustom alih-alih widget chat Katalis.app.
2. Membangun antarmuka percakapan ke dalam aplikasi mobile Anda.
3. Menambahkan Katalis.app ke platform lain yang belum memiliki SDK resmi Katalis.app.

### Membuat Objek Pelanggan

Anda bisa membuat dan mengambil objek data pelanggan menggunakan `inbox_identifier` dan `customer_identifier`.

**Inbox Identifier**

Anda bisa mendapatkan `inbox_identifier` dari channel API Anda → Settings → Configuration.

**Customer Identifier**

`customer_identifier` atau `source_id` bisa diperoleh saat membuat pelanggan menggunakan API create. Anda perlu menyimpan pengidentifikasi ini di sisi klien untuk membuat permintaan selanjutnya atas nama pelanggan. Ini bisa dilakukan di cookies, local storage, dll.

### API yang Tersedia

Client API yang tersedia didokumentasikan di sini. Beberapa hal yang bisa Anda lakukan dengan API:

- Membuat, Melihat, dan Memperbarui Contact
- Membuat dan Mendaftar Conversation
- Membuat, Mendaftar, dan Memperbarui Message

### Autentikasi HMAC

Client API juga mendukung Autentikasi HMAC. Token HMAC untuk Channel bisa diperoleh melalui menjalankan perintah berikut di rails console Anda.

```ruby
# ganti api_inbox_id dengan inbox id Anda
Inbox.find(api_inbox_id).channel.hmac_token
```

## Menghubungkan ke WebSocket Katalis.app

Untuk mendapatkan pembaruan real-time dari dashboard agen, hubungkan ke WebSocket Katalis.app menggunakan URL berikut.

```
<url instalasi anda>/cable
```

### Mengautentikasi Koneksi WebSocket Anda

Setelah berlangganan menggunakan `pubsub_token` pelanggan, Anda akan menerima event yang ditujukan ke objek pelanggan Anda. `pubsub_token` disediakan selama panggilan API pembuatan pelanggan.

**Contoh**

```javascript
const connection = new WebSocket('ws://localhost:3000/cable');
connection.send(JSON.stringify({ command:"subscribe", identifier: "{\"channel\":\"RoomChannel\",\"pubsub_token\":\"" + customer_pubsub_token + "\"}" }));
```

Temukan daftar lengkap event yang didukung oleh WebSocket di sini.
