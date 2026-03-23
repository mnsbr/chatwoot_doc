
# Template Konten Twilio

Twilio Content Templates memungkinkan Anda mengirim template pesan WhatsApp yang telah disetujui melalui channel WhatsApp Business Twilio Anda di Katalis. Template ini memungkinkan Anda memulai percakapan dan mengirim pesan terstruktur yang sesuai dengan kebijakan pengiriman pesan WhatsApp.

## Jenis Template yang Didukung

### Template Teks
- Pesan teks sederhana dengan variabel opsional
- Dukungan hingga 100 variabel per template menggunakan format {{1}}, {{2}}
- Dukungan multi-bahasa

### Template Media
- **Template Gambar**: Teks dengan header gambar (JPEG/PNG, maks 5MB)
- **Template Video**: Teks dengan header video (MP4/3GPP, maks 16MB)
- **Template Dokumen**: Teks dengan lampiran dokumen (format PDF/Office, maks 100MB)
- Dukungan untuk URL media dinamis dengan variabel

### Template Quick Reply
- Respons tombol interaktif yang ditangani oleh WhatsApp
- Tindakan tombol sederhana untuk respons umum
- Dukungan untuk beberapa varian bahasa

### Template Call-to-Action
- **Template Tombol URL**: Kirim pesan dengan tombol tindakan yang bisa diklik
- **Dukungan Variabel**: Baik teks pesan maupun parameter tombol bisa menyertakan variabel
- **Jenis Tindakan**: Tombol URL untuk pembayaran, pemesanan, website, dll.

## Prasyarat

Sebelum menggunakan Twilio Content Templates:

1. **Akun Twilio**: Akun Twilio aktif dengan akses WhatsApp Business API
2. **Template yang Disetujui**: Template dibuat dan disetujui di Twilio Console
3. **Integrasi Katalis**: Channel WhatsApp Twilio dikonfigurasi di Katalis
4. **Akun WhatsApp Business**: Profil WhatsApp Business yang terverifikasi

## Menyiapkan Template

1. Masuk ke Twilio Console Anda
2. Navigasi ke Messaging → Content Template Builder
3. Klik Create new template
4. Pilih jenis template Anda: Text, Media, atau Quick Reply
5. Konfigurasikan template sesuai tujuan
6. Kirim template untuk persetujuan WhatsApp
7. Tunggu persetujuan (5 menit hingga 24 jam)
8. Template yang disetujui menerima ContentSid
9. Template sekarang siap digunakan di Katalis

## Menyinkronkan Template ke Katalis

### Sinkronisasi Otomatis via API
Template secara otomatis disinkronkan saat Anda:
1. Membuka modal content templates di percakapan
2. Membuat percakapan baru dengan channel WhatsApp Twilio

### Sinkronisasi Manual
Untuk administrator inbox:
1. Buka Settings → Inboxes
2. Pilih inbox WhatsApp Twilio Anda
3. Klik tombol Sync Templates
4. Tunggu notifikasi penyelesaian sinkronisasi

## Menggunakan Template dalam Percakapan

**Langkah 1: Akses opsi template** - Buka percakapan apa pun dengan kontak WhatsApp, klik ikon template di komposer pesan, pilih "WhatsApp Templates" dari menu dropdown.

**Langkah 2: Pilih template** - Telusuri template yang disetujui, gunakan bilah pencarian untuk menemukan template tertentu dengan cepat.

**Langkah 3: Sesuaikan pesan** - Tergantung jenis template, Anda mungkin perlu mengisi variabel, URL media, atau parameter tombol.

## Praktik Terbaik

### Desain Template
- Buat pesan singkat dan jelas
- Gunakan variabel untuk personalisasi
- Pastikan file media dioptimalkan dan bisa diakses
- Uji template sebelum mengirim untuk persetujuan

### Penggunaan Variabel
- Gunakan nama variabel deskriptif di Twilio Console
- Berikan contoh yang jelas untuk persetujuan
- Jaga jumlah variabel tetap wajar (di bawah 10 untuk UX terbaik)

### Panduan Media
- Host file media di server yang andal dan cepat
- Gunakan URL HTTPS untuk semua media
- Optimalkan ukuran file untuk pengiriman lebih cepat
- Sertakan teks fallback untuk template media

### Kepatuhan
- Ikuti pedoman WhatsApp Business Policy
- Pastikan template melayani tujuan bisnis yang sah
- Hormati privasi dan persetujuan pengguna
- Monitor kinerja template dan status persetujuan

## Pemecahan Masalah

### Template Tidak Muncul
- **Penyebab**: Template belum disetujui WhatsApp
- **Solusi**: Periksa status persetujuan di Twilio Console

### Sinkronisasi Template Gagal
- **Penyebab**: Masalah koneksi API atau kredensial tidak valid
- **Solusi**: Verifikasi kredensial Twilio dan coba sinkronisasi ulang

### Media Tidak Dimuat
- **Penyebab**: URL media tidak bisa diakses atau format salah
- **Solusi**: Verifikasi URL bisa diakses publik, periksa format dan batas ukuran file, pastikan protokol HTTPS

### Variabel Tidak Berfungsi
- **Penyebab**: Format variabel salah atau nilai hilang
- **Solusi**: Gunakan format {{1}}, {{2}} yang benar di Twilio, isi semua variabel wajib di Katalis

## Batasan

- Template tidak didukung di campaign (akan hadir di pembaruan mendatang)
- Template list picker
- Template catalog
- Template carousel
- Maksimum 100 variabel per template
- File media harus bisa diakses publik
- Template memerlukan persetujuan WhatsApp
