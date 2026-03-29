# Cara Menggunakan Dashboard Apps

Dengan Dashboard Apps, Anda bisa mengintegrasikan aplikasi di dalam dashboard Katalis.app untuk digunakan agen. Fitur ini memungkinkan Anda membuat aplikasi secara independen, yang kemudian bisa disematkan untuk menyediakan informasi pelanggan, pesanan, riwayat pembayaran, dll.

Saat disematkan di dashboard Katalis.app, aplikasi Anda akan mendapatkan konteks percakapan dan kontak sebagai window event. Implementasikan listener untuk event message di halaman Anda untuk menerima konteks.

## Cara Membuat Dashboard App

**Langkah 1.** Buka Settings → Integrations → Dashboard apps. Klik tombol "Configure" yang sesuai dengan Dashboard Apps.

**Langkah 2.** Tambahkan nama aplikasi Anda dan URL tempat aplikasi Anda di-host.

Setelah selesai, tab baru dengan nama yang Anda berikan akan muncul di jendela percakapan. Dalam kasus ini, namanya "Customer Orders".

Saat Anda mengklik tab baru, Anda akan bisa melihat aplikasi Anda mengambil data di dashboard Katalis.app.

## Menerima Data dari Katalis.app ke Aplikasi Anda

Katalis.app akan mengirimkan konteks percakapan dan kontak sebagai window event. Ini bisa diakses di dalam aplikasi Anda dengan mengimplementasikan listener untuk event:

```javascript
window.addEventListener("message", function (event) {
  if (!isJSONValid(event.data)) {
    return;
  }
  const eventData = JSON.parse(event.data);
});
```

## Permintaan Data On-Demand dari Katalis.app

Jika Anda perlu meminta data percakapan sesuai permintaan dari Katalis.app, Anda bisa mengirim pesan ke jendela induk menggunakan API JavaScript postMessage.

Katalis.app akan mendengarkan key ini: `Katalis.app-dashboard-app:fetch-info`.

```javascript
window.parent.postMessage('Katalis.app-dashboard-app:fetch-info', '*')
// Anda akan mendapatkan pesan di listener on message dengan payload appContext.
```

## Payload Event

### Objek conversation

```json
{
  "meta": {
    "sender": {
      "email": "string",
      "id": "integer",
      "name": "string",
      "phone_number": "string",
      "custom_attributes": "object"
    },
    "channel": "string",
    "assignee": {
      "id": "integer",
      "email": "string",
      "name": "string",
      "role": "string"
    }
  },
  "id": "integer",
  "messages": [],
  "account_id": "integer",
  "inbox_id": "integer",
  "status": "string",
  "unread_count": "integer"
}
```

### Objek contact

```json
{
  "email": "string",
  "id": "integer",
  "name": "string",
  "phone_number": "string",
  "custom_attributes": {},
  "last_activity_at": "integer"
}
```

### Objek currentAgent

```json
{
  "email": "string",
  "id": "integer",
  "name": "string"
}
```

### Payload Akhir

```json
{
  "event": "appContext",
  "data": {
    "conversation": {},
    "contact": {},
    "currentAgent": {}
  }
}
```
