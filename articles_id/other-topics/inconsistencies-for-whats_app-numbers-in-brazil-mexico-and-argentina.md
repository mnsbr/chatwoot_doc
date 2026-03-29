# Inkonsistensi Nomor WhatsApp di Brasil dan Argentina

Selama beberapa tahun terakhir, beberapa negara telah mengubah sistem penomoran seluler mereka untuk mengakomodasi pertumbuhan. Perubahan ini menciptakan inkonsistensi antara nomor yang bisa Anda hubungi hari ini dan nomor yang disimpan WhatsApp untuk akun lama.

- **Brasil:** Angka "9" ditambahkan setelah kode area untuk semua nomor seluler, membuat format total 13 digit. Contoh: +55 11 9 8765-4321 alih-alih +55 11 8765-4321.

- **Argentina:** Nomor mungkin muncul dengan atau tanpa "9" setelah kode negara, tergantung kapan akun WhatsApp didaftarkan. Contoh: +54 9 11 1234-5678 vs +54 11 1234-5678.

Karena ini, saat Katalis.app memulai percakapan WhatsApp (menggunakan format yang "benar" yang bisa dihubungi), WhatsApp mungkin merespons dengan nomor terdaftar lama pengguna. Ini bisa membuat kontak duplikat dan mengganggu alur tiket di inbox Anda.

Sayangnya, masalah ini berasal dari WhatsApp sendiri. Tidak ada perbaikan di tingkat API, dan kemungkinan kecil WhatsApp akan memperbarui akun lama agar sesuai dengan aturan penomoran baru.

## Cara Katalis.app Mengatasi Ini

Kami telah menambahkan logika untuk secara otomatis mencegah kontak dan tiket duplikat saat ketidakcocokan ini terjadi:

- **Kasus 1:** Pesan masuk dengan nomor format baru (misalnya, kode negara +55 + kode area + 9 + nomor, total 13 digit) → Tidak perlu perubahan. Pesan ditautkan langsung ke kontak yang ada.

- **Kasus 2:** Pesan masuk dengan nomor format lama (misalnya, kode negara +55 + kode area + nomor, total 12 digit, digit tambahan hilang) → Katalis.app memeriksa apakah kontak sudah ada dalam format baru. → Jika ada, kami menautkan pesan ke kontak yang benar alih-alih membuat duplikat.

## Apa Artinya untuk Anda

- Anda mungkin masih melihat perbedaan tampilan nomor di WhatsApp vs tampilan di CRM Anda.
- Anda bisa terus mengirim pesan ke pelanggan secara normal — Katalis.app menangani ketidakcocokan di belakang layar.
- Katalis.app secara otomatis menormalisasi nomor telepon dari format lama dan baru di belakang layar untuk memastikan pencocokan kontak yang konsisten, terlepas dari format mana yang dikembalikan WhatsApp.
