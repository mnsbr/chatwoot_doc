# Cara Menyiapkan Channel WhatsApp (Alur Manual)

Anda bisa mengelola percakapan akun bisnis WhatsApp dari Katalis. Untuk menyiapkannya, Anda memiliki dua pilihan provider:

1. WhatsApp Cloud API
2. Twilio

Kami akan menjelaskan semua prosedur di panduan ini.

## Prasyarat

1. Anda memerlukan Akun Developer Meta untuk menyiapkan WhatsApp API. Jika belum memiliki akun developer, klik di sini untuk membuatnya sebelum melanjutkan.
2. Nomor telepon yang valid

## Menggunakan WhatsApp Cloud API

WhatsApp Cloud API tersedia untuk semua bisnis dan developer individu. Karena di-host di infrastruktur cloud Meta, Anda tidak perlu lagi menggunakan provider pihak ketiga seperti Twilio, Zendesk, 360Dialog, atau MessageBird (Business Solution Providers) untuk meng-host WhatsApp Business API Anda.

### Menyiapkan Profil Bisnis Anda

Buat profil bisnis WhatsApp profesional dengan nama perusahaan, deskripsi, dan informasi kontak. Profil yang dibuat dengan baik membantu pelanggan mengenali dan mempercayai merek Anda saat berinteraksi dengan Anda.

Masuk ke https://business.facebook.com dan klik tombol create portfolio di menu dropdown di bawah Home.

Lengkapi semua kolom yang diperlukan untuk menyiapkan portfolio bisnis Anda.

Setelah Anda membuat portfolio bisnis, saatnya membuat aplikasi Facebook Anda.

### Menyiapkan Aplikasi Facebook Anda

Masuk ke https://developers.facebook.com/ dan klik tombol Create App.

Lengkapi kolom yang diperlukan.

Klik "Other" dari opsi yang tersedia.

Pilih "Business" sebagai jenis aplikasi Anda.

Masukkan alamat email kontak Anda dan pilih portfolio bisnis dari menu dropdown.

### Menambahkan WhatsApp ke Aplikasi Anda

Setelah membuat aplikasi, Anda akan diarahkan ke dashboard aplikasi. Dari sana, klik "Add Product" dan pilih WhatsApp dari daftar produk yang tersedia.

Klik tombol "Set up" untuk WhatsApp.

**Catatan:** Sebelum melanjutkan, verifikasi bisnis Anda dengan Meta. Anda perlu mengirimkan dokumentasi untuk verifikasi, yang diperlukan untuk akses API penuh.

### Menyiapkan Token Akses Permanen WhatsApp Cloud API

Anda perlu membuat System User dan menghasilkan token permanen untuk menjaga akses yang aman dan tidak terputus.

Masuk ke akun developer Facebook Anda, pilih aplikasi WhatsApp, dan navigasi ke halaman Business settings.

Klik "System Users" dan tambahkan system user baru dengan peran Admin.

Klik tombol "Add Assets", pilih nama aplikasi Anda, pilih opsi "Full Control", dan klik "Assign assets."

Kembali ke halaman system users, pilih system user yang baru dibuat dari daftar, dan klik tombol "Generate new token".

Pilih aplikasi Anda dari menu dropdown.

Pilih tiga level izin ini untuk token Anda:

- `whatsapp_business_manage_events`
- `whatsapp_business_management`
- `whatsapp_business_messaging`

Salin dan simpan token Anda.

### Menyiapkan WhatsApp Cloud API

Untuk membuat akun bisnis Meta baru, pilih "create a business account" dari menu dropdown. Jika sudah memiliki akun bisnis, Anda bisa memilihnya dari opsi yang ada. Klik tombol continue.

Tempel token permanen Anda di sini.

Tambahkan nomor telepon siap produksi Anda.

**Catatan:** Meta memerlukan nomor telepon yang diverifikasi untuk pengaturan WhatsApp API. Anda bisa memverifikasi nomor menggunakan OTP (one-time password).

Setelah menambahkan dan memverifikasi nomor telepon, langkah selanjutnya adalah mengonfigurasi webhook untuk menerima pesan masuk.

## Menghubungkan Akun Katalis Anda

Mari hubungkan akun Katalis Anda dengan WhatsApp Cloud API.

Salin WhatsApp Phone Number ID dan Business Account ID dari bagian ini.

Masuk ke akun Katalis Anda, buka Settings > Inbox, dan pilih channel WhatsApp.

Masukkan nomor telepon, phone number ID, dan business ID dari pengaturan WhatsApp API Anda.

Tambahkan anggota tim ke inbox WhatsApp Anda.

Salin webhook URL dan webhook verification token yang disediakan di sini.

### Menyiapkan Webhook Anda

Kita perlu menyiapkan webhook WhatsApp untuk menerima pesan pelanggan yang masuk ke nomor bisnis Anda.

Callback URL Anda harus dalam format `https://app.katalis.app/webhooks/whatsapp/{phone_number}`.

Masuk ke akun developer Facebook Anda dan navigasi ke WhatsApp > Configuration.

Tempel webhook URL dan verification token Katalis di sini, lalu klik "Verify and Save".

Atur izin webhook dengan berlangganan messages.

Selesai — Anda sudah selesai! Sekarang Anda bisa mulai mengirim pesan WhatsApp melalui Katalis.

## FAQ

### Bagaimana cara mengonfigurasi beberapa nomor di bawah satu aplikasi Facebook?

Aplikasi Facebook hanya mengizinkan konfigurasi satu endpoint Webhook. Jadi buat Inbox di Katalis untuk semua nomor yang diperlukan. Anda hanya perlu mengonfigurasi Webhook URL yang disediakan untuk salah satu inbox ini di aplikasi Facebook agar semua inbox lainnya berfungsi.

### Jenis template WhatsApp apa yang didukung oleh Katalis?

Silakan periksa dokumen untuk detail lebih lanjut tentang template.
