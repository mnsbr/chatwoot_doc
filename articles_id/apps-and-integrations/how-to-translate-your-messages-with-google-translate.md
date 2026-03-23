# Cara Menerjemahkan Pesan dengan Google Translate

Jika Anda sering menerima pertanyaan dalam bahasa yang tidak Anda/anggota tim pahami, Anda bisa menggunakan integrasi Google Translate di Katalis. Saat diaktifkan, Anda bisa langsung menerjemahkan pesan masuk menggunakan menu klik kanan. Dengan cara ini, Anda bisa dengan mudah berkomunikasi dengan pelanggan dalam bahasa asli mereka, bahkan jika Anda tidak menguasainya.

## Cara Mengaktifkan Google Translate di Katalis

**Langkah 1.** Buka Settings → Applications → Google Translate. Klik tombol "Configure" yang sesuai.

**Langkah 2.** Anda akan melihat halaman aplikasi Google Translate. Klik tombol "Connect".

**Langkah 3.** Masukkan Google Cloud Project ID dan Project Key File Anda. Jika Anda memerlukan bantuan untuk mendapatkan nilai-nilai ini, lihat dokumen dari Google ini.

Setelah Anda memasukkan nilai, klik tombol "Create".

Sekarang, integrasi Google Translate Anda selesai.

## Cara Mengubah Bahasa Terjemahan

Pesan Anda diterjemahkan ke bahasa situs Anda. Untuk memilih bahasa situs, kunjungi halaman "Account Settings".

**Langkah 1.** Buka Settings → Account Settings → Site Language. Buka dropdown dan pilih bahasa pilihan Anda.

**Langkah 2.** Klik tombol "Update Settings" di pojok kanan atas halaman. Ini akan menerjemahkan seluruh dashboard Anda ke bahasa yang dipilih.

**Catatan:** Agen bisa memilih bahasa pilihan individual mereka juga.

## Cara Menerjemahkan Pesan Masuk

Setiap kali Anda menerima pesan dalam bahasa yang Anda perlukan bantuan, klik 3 titik di samping pesan untuk membuka menu dan pilih "Translate".

Temukan konten terjemahan secara inline.

## Cara Membuat Service Account di Google Cloud Console

Untuk membuat service account untuk Google Translate API, mulai dengan masuk ke Google Cloud Console dan pilih atau buat proyek baru. Setelah proyek siap, aktifkan Cloud Translation API dengan navigasi ke "APIs & Services" > "Library" dan mencari "Cloud Translation API." Klik "Enable" untuk mengaktifkannya. Mengaktifkan billing juga diperlukan jika Anda belum melakukannya.

Selanjutnya, buka "IAM & Admin" > "Service Accounts" dan klik "Create Service Account." Berikan nama (misalnya translate-api-user) dan lanjutkan untuk menetapkan peran "Cloud Translation API User".

Setelah membuat service account, navigasi ke bagian "Keys", klik "Add Key," dan pilih "Create New Key" dalam format JSON. Unduh dan simpan file JSON ini dengan aman.
