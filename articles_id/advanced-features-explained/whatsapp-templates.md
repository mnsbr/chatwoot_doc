
# Template WhatsApp

Template WhatsApp adalah format pesan yang telah disetujui sebelumnya yang memungkinkan Anda memulai percakapan dengan pelanggan. Template ini penting untuk mengirim pesan promosi, pembaruan pesanan, dan notifikasi dukungan melalui WhatsApp Business Platform.

**Catatan:** Template WhatsApp saat ini hanya didukung untuk inbox WhatsApp Cloud.

## Apa itu Template WhatsApp?

Template WhatsApp adalah pesan terstruktur yang harus disetujui oleh WhatsApp sebelum Anda bisa mengirimnya ke pelanggan. Template ini membantu memastikan kepatuhan dengan kebijakan pengiriman pesan WhatsApp sambil memungkinkan Anda mengirim komunikasi yang profesional dan konsisten.

Template bisa menyertakan:
- Pesan teks dengan variabel yang dipersonalisasi
- Gambar, video, atau dokumen sebagai header
- Tombol tindakan untuk respons cepat pelanggan
- Tombol call-to-action yang menautkan ke website atau nomor telepon

## Kategori Template

WhatsApp mengorganisir template ke dalam kategori berbeda berdasarkan tujuannya:

- **Utility** - Pesan transaksional seperti konfirmasi pesanan dan tanda terima
- **Marketing** - Konten promosi dan penawaran khusus
- **Shipping Update** - Pembaruan pengiriman dan status paket
- **Ticket Update** - Notifikasi kasus dukungan
- **Issue Resolution** - Tindak lanjut layanan pelanggan

## Yang Tidak Didukung

### Template autentikasi
- Template AUTHENTICATION dengan kode OTP dan pesan verifikasi
- Auto-population parameter tombol dengan nilai OTP

### Komponen interaktif
- Template LIST dengan opsi yang bisa dipilih
- Template PRODUCT dengan integrasi katalog
- Template CATALOG untuk penjelajahan produk

### Komponen lokasi
- Header LOCATION dengan koordinat peta
- Parameter alamat dengan latitude/longitude

### Fitur lanjutan
- Template carousel dengan beberapa kartu
- Komponen formulir untuk pengumpulan data
- Template integrasi pembayaran

## Template Legacy vs Enhanced

Katalis mendukung dua format template untuk memastikan kompatibilitas dengan semua template yang ada:

### Template Legacy

Template tradisional yang menggunakan variabel teks sederhana. Bekerja dengan:
- Pesan teks dasar
- Substitusi variabel sederhana (seperti menyisipkan nama pelanggan)
- Interaksi tombol sederhana

Contoh format legacy:
```json
{
  "parameters": ["John Doe", "12345", "2025-01-15"]
}
```

⚠️ **Penting:** Dukungan template legacy akan dihentikan di v4.7. Kami merekomendasikan migrasi ke template enhanced untuk memastikan fungsionalitas berkelanjutan.

### Template Enhanced

Format enhanced baru menyediakan fitur yang lebih canggih:
- **Dukungan media** - Kirim gambar, video, dan dokumen
- **Variabel lanjutan** - Personalisasi teks yang lebih fleksibel
- **Tombol interaktif** - Tombol URL dengan tautan dinamis, kode salin, dan quick reply
- **Validasi lebih baik** - Pemeriksaan real-time parameter template Anda

Contoh format enhanced:
```json
{
  "body": {
    "1": "John Doe",
    "2": "12345",
    "3": "2025-01-15"
  },
  "header": {
    "media_url": "https://example.com/image.jpg",
    "media_type": "image"
  },
  "buttons": [
    {
      "type": "url",
      "parameter": "track123"
    }
  ]
}
```

## Cara Membuat Template WhatsApp

Saat ini, template WhatsApp harus dibuat melalui WhatsApp Business Manager:

1. **Akses WhatsApp Business Manager** - Buka business.facebook.com
2. **Navigasi ke template** - Temukan bagian "Account tools" dan pilih "Message templates"
3. **Buat template baru** - Klik "Create template" dan pilih jenis template
4. **Desain template** - Tambahkan header, body, footer, dan tombol sesuai kebutuhan
5. **Kirim untuk persetujuan** - WhatsApp akan meninjau template (bisa memakan waktu hingga 24 jam)
6. **Sinkronkan ke Katalis** - Setelah disetujui, template akan otomatis muncul atau Anda bisa sinkronkan secara manual via inbox di Katalis

## Cara Mengirim Template WhatsApp

Template WhatsApp bisa dikirim dalam dua cara:
- **Percakapan individu** - Kirim template ke pelanggan tertentu selama percakapan
- **Campaign** - Kirim template ke beberapa pelanggan sekaligus menggunakan fitur campaign Katalis

### Mengirim Template di Percakapan

**Langkah 1: Akses opsi template** - Buka percakapan apa pun dengan kontak WhatsApp, klik ikon template di komposer pesan, pilih "WhatsApp Templates" dari menu dropdown.

**Langkah 2: Pilih template** - Telusuri template yang disetujui, gunakan bilah pencarian untuk menemukan template tertentu.

**Langkah 3: Sesuaikan pesan** - Tergantung jenis template:

Untuk template teks:
- Nama pelanggan, nomor pesanan, atau informasi personalisasi lainnya
- Kolom variabel yang ditandai {{1}}, {{2}}, dll.

Untuk template media:
- URL Gambar/Video - Berikan tautan langsung ke file media
- URL Dokumen - Tautan ke PDF, dokumen Word, atau file lainnya
- Media harus bisa diakses publik

Untuk template tombol:
- Parameter URL - Tautan dinamis untuk tombol call-to-action
- Kode salin - Kode diskon atau kode referral
- Nomor telepon - Untuk tombol click-to-call

**Langkah 4: Pratinjau dan kirim** - Tinjau pesan, periksa semua variabel terisi benar, verifikasi URL media berfungsi, klik "Send Template".

### Mengirim Template via Campaign

Buka WhatsApp Campaigns di dashboard Katalis, buat campaign baru dan pilih WhatsApp sebagai channel, pilih template dari opsi yang tersedia, dan konfigurasikan audiens serta parameter template.

## FAQ

### Mengapa saya tidak bisa melihat semua template WhatsApp di Katalis?
Hanya template yang disetujui WhatsApp dan didukung Katalis yang akan muncul. Jenis template yang tidak didukung (seperti template autentikasi dengan kode OTP) otomatis difilter.

### Bisakah saya mengedit template langsung di Katalis?
Tidak, template harus dibuat dan diedit di WhatsApp Business Manager. Katalis hanya digunakan untuk mengirim template yang disetujui.

### Template saya gagal terkirim. Apa yang harus diperiksa?
Masalah umum meliputi: variabel hilang, URL media rusak, ukuran file terlalu besar, atau template belum disetujui.

### Format file apa yang bisa digunakan dalam template?
- **Gambar**: JPEG, PNG (di bawah 5MB)
- **Video**: MP4, 3GPP (di bawah 16MB)
- **Dokumen**: PDF, DOC, DOCX, XLS, XLSX, PPT, PPTX, TXT (di bawah 100MB)
