# Cara Menyiapkan Sertifikat SSL untuk Domain Kustom Help Center Anda

Menggunakan domain sendiri, seperti docs.perusahaan-anda.com, membuat help center Anda terasa lebih terpercaya dan sesuai merek. Katalis memungkinkan Anda menggunakan domain kustom dan akan membantu mengamankan situs Anda dengan sertifikat SSL sehingga aman bagi pengunjung.

Panduan ini memandu Anda menyiapkan domain kustom untuk portal Help Center di Katalis.

**Catatan:** Panduan ini untuk pengguna Katalis Cloud. Jika Anda menggunakan versi self-hosted, Anda perlu menyiapkan dan mengelola sertifikat SSL sendiri.

**Ringkasan:** Tambahkan domain kustom di pengaturan portal Katalis, perbarui DNS Anda dengan CNAME yang disediakan Katalis, dan kami akan menerbitkan sertifikat SSL. Setelah siap, Help Center Anda akan aktif dan bisa diakses pelanggan.

## Langkah 1: Siapkan Domain Kustom di Pengaturan Portal

Masuk ke dashboard Katalis dan buka Help Center yang ingin Anda hubungkan dengan domain kustom. Klik Settings, lalu gulir ke bagian Custom Domain. Klik tombol "Add custom domain" untuk memulai pengaturan.

Anda akan melihat prompt yang meminta domain kustom Anda. Masukkan domain tempat Anda ingin Help Center tersedia (misalnya, docs.domainanda.com). Ini adalah alamat website yang akan dikunjungi pelanggan untuk mengakses dokumentasi Anda.

Selanjutnya, Anda akan ditampilkan pengaturan DNS yang perlu ditambahkan agar kami bisa mengonfirmasi bahwa domain tersebut milik Anda dan menghubungkannya ke Help Center. Anda perlu menyalin informasi ini dan memperbarui penyedia DNS Anda sesuai kebutuhan.

Jika Anda tidak yakin cara melakukannya, Anda bisa menggunakan opsi di layar untuk mengirimkan detail tersebut melalui email ke developer Anda.

## Langkah 2: Perbarui DNS dengan CNAME Record

Anda harus mengarahkan domain kustom ke Katalis dengan membuat CNAME record.

- Host: docs
- Type: CNAME
- Value: katalis.help

Instruksi bervariasi tergantung penyedia DNS:

**Menggunakan Cloudflare:**

Anda bisa menemukan pengaturannya di tab "DNS".

**Catatan:** Pastikan mode enkripsi SSL diatur ke Full di Cloudflare (Anda bisa melihat ini di SSL/TLS → Overview).

**Menggunakan AWS Route 53:**

Anda bisa menemukan pengaturannya di layanan "Route53".

Jika Anda menggunakan penyedia DNS yang berbeda, langkah-langkahnya umumnya sama. Cari bagian pengaturan DNS dan tambahkan CNAME record seperti yang dijelaskan. Jika tidak yakin caranya, cukup cari instruksi spesifik untuk penyedia Anda menggunakan frasa seperti "How to add a CNAME record on [Penyedia DNS Anda]".

Langkah ini menautkan domain Anda ke server Katalis. Setelah selesai, kami akan memiliki semua yang diperlukan — detail portal dan konfigurasi domain — untuk menerbitkan sertifikat SSL dan membuat Help Center Anda aktif.

## Langkah 3: Mendapatkan Sertifikat SSL

Katalis menyediakan sertifikat SSL untuk semua pelanggan cloud pada paket berbayar yang menyiapkan domain kustom untuk portal Help Center mereka.

Langkah ini terjadi secara otomatis. Setelah Anda menambahkan CNAME record ke DNS, server kami akan memverifikasi domain dan mulai menerbitkan sertifikat SSL. Ini biasanya hanya memakan waktu beberapa menit, tetapi dalam beberapa kasus, tergantung penyedia DNS Anda dan berapa lama mereka memperbarui record, mungkin memakan waktu hingga 24–48 jam.

Anda bisa melacak status sertifikat SSL langsung dari dashboard Katalis. Awalnya, Anda akan melihat status "Awaiting Verification". Ini berarti kami masih mengonfirmasi pengaturan domain sebelum sertifikat diterbitkan.

Jika ada masalah selama proses verifikasi SSL seperti CNAME record yang salah atau keterlambatan propagasi DNS, Anda akan melihat pesan error di samping status pada dashboard. Arahkan kursor ke indikator status untuk melihat detail lebih lanjut tentang apa yang salah dan apa yang perlu diperbaiki.

Setelah verifikasi berhasil dan sertifikat SSL diterbitkan, status akan berubah menjadi 'Live' di dashboard Anda. Ini berarti Help Center Anda sekarang tersedia secara aman di domain kustom Anda. Pelanggan bisa mengunjungi URL dan menjelajahi konten.
