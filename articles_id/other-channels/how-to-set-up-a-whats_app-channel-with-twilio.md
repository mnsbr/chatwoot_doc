# Cara Menyiapkan Channel WhatsApp dengan Twilio

Kelola percakapan akun bisnis WhatsApp Anda melalui Katalis.app. Anda memiliki dua pilihan provider:

1. WhatsApp Cloud API (cara yang disarankan)
2. Twilio

Panduan ini akan memandu Anda melalui proses pengaturan.

## Prasyarat

1. Nomor telepon yang valid
2. Akun Twilio. Jika belum memiliki, buat di sini: https://www.twilio.com/en-us/messaging/channels/whatsapp

## Menggunakan Twilio API

Ada dua cara menggunakan Twilio dengan Katalis.app:

1. Cara reguler tanpa messaging service
2. Dengan messaging service

### Menyiapkan Twilio Tanpa Messaging Service

Masuk ke akun Twilio Anda dan klik "Create New Account".

Lengkapi semua kolom yang diperlukan dan selesaikan proses pembuatan akun.

Salin Account SID, Auth Token, dan nomor telepon Anda. Jika Anda belum menambahkan nomor telepon ke akun Twilio, lakukan sebelum melanjutkan.

Masuk ke akun Katalis.app Anda, klik Settings > Inbox > Add Inbox dan pilih Whatsapp.

Masukkan Account SID, Auth Token, dan nomor WhatsApp Anda di sini.

Tambahkan agen untuk mengelola inbox WhatsApp Anda.

Buka Settings > Inbox, pilih inbox Anda, klik Configuration, dan salin webhook URL Anda.

Kembali ke dashboard Twilio Anda:

1. Buka Twilio Console → Phone Numbers → Manage → Active Numbers
2. Klik nomor WhatsApp Anda.
3. Klik Configure
4. Di bagian Messaging, centang kolom "Webhook (When a message comes in)".
5. Perbarui webhook URL.

Selesai! Anda siap untuk mulai mengirim pesan WhatsApp melalui Katalis.app.

### Menyiapkan Twilio dengan Messaging Service

Menyiapkan Twilio dengan messaging service memerlukan langkah tambahan dibandingkan pengaturan reguler.

Navigasi ke Messaging > Services dan klik tombol "Create Messaging Service".

Isi semua kolom yang diperlukan pada langkah-langkah berikutnya sampai Anda mencapai halaman ini. Salin messaging service ID Anda dan klik "Save".

Masuk ke akun Katalis.app Anda. Saat membuat inbox, centang kotak "Use Twilio Message Service". Kemudian salin dan tempel Account ID, Message Service ID, dan Token ke kolom yang sesuai.

Buka dashboard Twilio Anda, navigasi ke Messaging > Services > Select Service > Integration, dan tempel Webhook URL Anda di sini.

Selesai — Anda sudah siap! Sekarang Anda bisa mulai mengirim pesan WhatsApp melalui Katalis.app.

## FAQ

### Jenis template WhatsApp apa yang didukung Katalis.app saat menggunakan Twilio?

Saat ini, Katalis.app tidak mendukung template dengan Twilio.

### Saya menggunakan Twilio Studio. Apakah ada langkah tambahan yang diperlukan?

Jika Anda menggunakan Twilio Studio untuk alur percakapan kustom, memperbarui webhook URL secara langsung akan merusak integrasi yang ada.

Ikuti langkah-langkah ini sebagai gantinya:

1. Identifikasi langkah dalam alur Anda di mana Anda ingin "agent handoff" terjadi.
2. Tambahkan "make http request widget" seperti yang ditunjukkan di bawah dengan nilai yang diberikan.
