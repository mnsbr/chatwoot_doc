# Cara Menyiapkan Channel WhatsApp

Anda bisa mengelola percakapan Akun Bisnis WhatsApp langsung dari Katalis. Untuk menghubungkan nomor WhatsApp Anda, Katalis mendukung dua metode onboarding:

- **Embedded Signup (disarankan)** – alur terpandu yang didukung oleh Meta yang mengonfigurasi nomor, webhook, dan token Anda secara otomatis.
- **Manual Setup** – opsi lanjutan untuk penyedia teknologi dan kasus di mana Embedded Signup tidak bisa digunakan.

Panduan ini memberi Anda gambaran umum tentang kedua metode, perbedaannya, dan tautan ke instruksi langkah demi langkah yang detail.

## Prasyarat

- Akun developer atau bisnis Meta (Facebook)
- Nomor telepon yang valid (belum terikat ke alur WhatsApp Embedded Signup lain, kecuali jika sedang migrasi)
- Workspace Katalis dengan fitur WhatsApp diaktifkan

## Langkah 1: Buka Inboxes

1. Masuk ke akun Katalis Anda.
2. Navigasi ke Settings › Inboxes › Add Inbox.
3. Pilih WhatsApp sebagai channel.

## Langkah 2: Pilih Metode Pengaturan Anda

Saat membuat Inbox WhatsApp, Anda akan melihat dua opsi:

### Connect with WhatsApp Business (Embedded Signup)

- Mengarahkan Anda ke alur Embedded Signup Meta.
- Anda masuk dengan akun Facebook, pilih atau buat WhatsApp Business Account (WABA), dan tambahkan nomor telepon Anda.
- Katalis secara otomatis menerima webhook, token, dan konfigurasi nomor telepon.

Gunakan opsi ini jika Anda:
- Menambahkan nomor WhatsApp baru
- Mencari pengaturan tercepat tanpa konfigurasi
- Bukan penyedia teknologi yang meng-onboard nomor sendiri

Baca panduan lengkap tentang WhatsApp Embedded Signup.

### Manual Setup

- Anda mengonfigurasi semuanya melalui Meta Developer Console.
- Memerlukan pembuatan token, membuat system user, menetapkan aset, dan menyiapkan webhook secara manual.
- Anda menyalin/menempel Phone Number ID, Business Account ID, dan API key ke Katalis.

Gunakan opsi ini jika Anda:
- Penyedia teknologi yang meng-onboard nomor sendiri
- Menggunakan kembali nomor yang sudah terhubung ke Embedded Signup
- Nyaman bekerja dengan dashboard Meta Developer
