# Cara Melanjutkan Percakapan Melalui Email

Pelanggan Anda bisa melanjutkan percakapan chat mereka dengan agen melalui thread email. Ini mungkin diperlukan dalam keadaan berikut:

- Tidak ada agen yang tersedia, dan pelanggan meninggalkan pesan di chat.
- Pelanggan meninggalkan chat sebelum agen membalas.

Agar ini berfungsi, kontak harus memiliki alamat email di CRM Katalis.app.

## Mendapatkan Alamat Email Kontak

Anda bisa meminta/memperbarui email pelanggan ke Katalis.app melalui cara berikut:

### 1. Dari SDK Katalis.app
Jika email pelanggan diketahui, Anda bisa memasukkannya ke Katalis.app melalui metode `setUser` di SDK kami.

### 2. Dari formulir pre-chat
Jika Anda mengaktifkan formulir pre-chat wajib, percakapan dimulai dengan layar seperti yang ditunjukkan di bawah:

### 3. Dari Prompt Pengumpulan Email
Ketika formulir pre-chat dinonaktifkan, dan email pelanggan tidak diketahui, Katalis.app memulai percakapan dengan prompt pengumpulan email.

**Catatan:** Ketika Captain diaktifkan di inbox, prompt pengumpulan email otomatis ditekan. Captain akan menangani percakapan secara langsung, bahkan di luar jam kerja. Prompt pengumpulan email hanya akan dikirim jika Captain menyerahkan percakapan ke agen manusia atau jika Captain tidak dikonfigurasi untuk inbox tersebut.

## Kontinuitas Percakapan

**Catatan:** Aktifkan kontinuitas percakapan di instalasi self-hosted dengan bantuan panduan ini.

Jika alamat email pelanggan diperbarui melalui salah satu opsi yang disebutkan di atas dan mereka meninggalkan chat sementara agen telah membalas, hal berikut terjadi:

- Pelanggan menerima thread email dengan ringkasan percakapan. Mereka bisa membalas email tersebut dan melanjutkan percakapan.
- Agen menerima balasan pelanggan dari email di dashboard Katalis.app mereka, dilanjutkan melalui thread percakapan yang sudah ada.

Ikon email di gelembung chat menunjukkan bahwa pelanggan telah membalas melalui email.
