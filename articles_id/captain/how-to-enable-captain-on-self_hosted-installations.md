
# Cara Mengaktifkan Captain di Instalasi Self-Hosted

Captain adalah asisten AI yang membantu Anda merespons lebih cepat dan lebih akurat. Dengan Bring Your Own Key (BYOK), Anda bisa menggunakan API key sendiri dari OpenAI atau layanan AI yang kompatibel. Anda mengontrol data, biaya, dan model mana yang digunakan. Dalam pengaturan self-hosted, Captain hanya mengirim data ke model AI yang Anda pilih.

Panduan ini akan menunjukkan cara mengaktifkan Captain di Enterprise Edition self-hosted Anda, menambahkan API key, dan mengatur model kustom jika diinginkan.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- Katalis.app Enterprise Edition dengan paket berbayar.
- Akses Admin ke Super Admin Console.
- API key OpenAI yang valid.
- (Opsional) Endpoint API yang kompatibel dengan OpenAI untuk self-hosted.
- (Opsional) API key Firecrawl untuk crawling dokumentasi yang lebih baik.

## Mengaktifkan Captain di Super Admin Console

Untuk mengaktifkan Captain di tingkat instalasi:

Masuk ke Super Admin Console. Navigasi ke Settings → Captain.

Isi field konfigurasi:

1. **OpenAI API Key** (Wajib) – Key untuk mengautentikasi permintaan ke OpenAI atau layanan yang kompatibel.
2. **OpenAI Model** (Wajib) – Default adalah gpt-4o-mini. Anda bisa memilih model yang didukung lainnya seperti gpt-5.
3. **OpenAI API Endpoint** (Opsional) – Masukkan endpoint API kustom Anda jika menggunakan model self-hosted.
4. **Firecrawl API Key** (Opsional) – Direkomendasikan untuk crawling website dan dokumentasi yang lebih baik.

Klik Submit untuk menyimpan konfigurasi Anda.

## Mengaktifkan Captain untuk Akun

Setelah mengaktifkan Captain secara global, aktifkan untuk akun individual:

1. Di Super Admin Console, buka Accounts.
2. Pilih akun yang ingin Anda aktifkan Captain dan klik Edit.
3. Di bawah bagian Premium Features, aktifkan Captain.
4. Simpan perubahan.

## Troubleshooting

Jika Captain tidak merespons sesuai harapan:

- Verifikasi bahwa API key OpenAI benar dan aktif.
- Periksa bahwa nama model sesuai dengan model yang didukung.
- Pastikan API key Firecrawl Anda valid jika menggunakan crawling.
- Konfirmasi bahwa Captain diaktifkan baik di tingkat instalasi maupun tingkat akun.

Jika Captain masih tidak merespons, tinjau log server Katalis.app untuk proses web dan worker untuk mengidentifikasi error apa pun, dan bagikan detail error tersebut dengan tim dukungan untuk bantuan lebih lanjut.
