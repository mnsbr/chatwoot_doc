
# Masalah WhatsApp Umum dan Cara Memperbaikinya

## Pesan WhatsApp Tidak Diterima Meskipun Semuanya Terlihat Terhubung

### Gejala

- Channel WhatsApp berhasil terhubung
- Status nomor telepon menunjukkan Connected
- Rating kualitas Green
- Tidak ada error yang ditampilkan di Katalis.app
- Pesan keluar mungkin berfungsi, tetapi pesan masuk tidak diterima

### Mengapa Ini Terjadi

Dalam beberapa kasus, Meta mengharuskan nomor telepon WhatsApp didaftarkan ulang, meskipun masih tampak terhubung dan sehat.

Ini biasanya terjadi setelah:

- Perubahan nama tampilan
- Pembaruan profil bisnis
- Masalah sinkronisasi internal tertentu di sisi Meta

Ketika ini terjadi, pesan WhatsApp mungkin berhenti terkirim secara diam-diam tanpa menunjukkan error yang terlihat. Ini adalah perilaku Meta yang diketahui.

### Cara Memperbaiki

Mendaftarkan ulang nomor telepon WhatsApp menyelesaikan masalah segera (Silakan hubungi kami di dukungan dan kami akan menyelesaikannya untuk Anda).

- Tidak diperlukan perubahan paket
- Tidak diperlukan perubahan webhook
- Dalam kebanyakan kasus, tidak diperlukan kode verifikasi baru

Setelah nomor didaftarkan ulang, pengiriman pesan kembali normal.

## Masalah Status Nama Tampilan (Pending / Rejected / Not Approved)

### Apa Itu Nama Tampilan?

Nama tampilan adalah nama bisnis yang ditampilkan ke pelanggan di WhatsApp. Meta meninjau dan menyetujui nama ini sebelum menjadi aktif.

### Status Nama Tampilan Umum

- **Approved** – Semuanya baik, tidak perlu tindakan
- **Pending** – Meta sedang meninjau nama
- **Rejected** – Nama tidak memenuhi pedoman Meta

### Mengapa Masalah Nama Tampilan Penting

- Nama tampilan yang ditolak atau tertunda dapat menunda onboarding
- Mengubah nama tampilan mungkin memerlukan pendaftaran ulang nomor telepon
- Pesan mungkin gagal atau berhenti berfungsi jika pendaftaran tidak diselesaikan setelah persetujuan

### Alasan Umum Penolakan

- Nama tidak cocok dengan nama bisnis di Meta Business Manager
- Penggunaan kata umum (misalnya "Support", "Official", "Service")
- Penggunaan emoji, simbol, atau huruf kapital semua
- Ketidakcocokan antara nama merek dan website/domain

### Praktik Terbaik untuk Nama Tampilan

- Gunakan nama bisnis atau merek resmi Anda
- Cocokkan nama yang digunakan di website dan Meta Business Manager Anda
- Hindari emoji, slogan, atau deskriptor tambahan
- Buat sederhana dan konsisten dengan merek

### Catatan Penting

Setelah nama tampilan disetujui, Meta mungkin masih mengharuskan nomor telepon didaftarkan ulang agar perubahan berlaku sepenuhnya.

Jika pesan WhatsApp berhenti berfungsi setelah pembaruan nama tampilan, mendaftarkan ulang nomor biasanya memperbaiki masalah.

## WhatsApp Error 131049 – Pengguna Belum Menerima Ketentuan Layanan WhatsApp

### Apa Itu Error 131049?

Error 131049 berarti penerima belum menerima Ketentuan Layanan WhatsApp terbaru.

Error ini dikembalikan oleh WhatsApp, bukan Katalis.app, dan khusus untuk nomor telepon pelanggan, bukan pengaturan bisnis Anda.

### Kapan Error Ini Terjadi?

Anda mungkin melihat error 131049 saat:

- Mengirim pesan ke pengguna yang belum membuka WhatsApp baru-baru ini
- WhatsApp telah merilis Ketentuan Layanan yang diperbarui
- Pengguna belum menerima ketentuan baru di aplikasi WhatsApp mereka

Dalam keadaan ini, WhatsApp memblokir pengiriman pesan ke pengguna tersebut sampai mereka menerima ketentuan.

### Mengapa Ini Terjadi

WhatsApp mengharuskan semua pengguna untuk secara eksplisit menerima Ketentuan Layanan yang diperbarui sebelum mereka dapat:

- Menerima pesan dari bisnis
- Berpartisipasi dalam percakapan bisnis

Sampai pengguna menerima ketentuan, WhatsApp akan menolak pesan dengan error 131049.

### Cara Memperbaiki Error 131049

Masalah ini tidak dapat diperbaiki dari Katalis.app atau akun WhatsApp Business Anda.

Pengguna akhir harus:

1. Membuka aplikasi WhatsApp mereka
2. Menerima prompt Ketentuan Layanan terbaru

Setelah pengguna menerima ketentuan, pesan akan mulai terkirim secara otomatis — tidak perlu coba ulang atau perubahan konfigurasi.
