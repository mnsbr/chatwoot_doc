
# Menyematkan Video di Help Center

Help Center Katalis.app mendukung penyematan video otomatis dari berbagai platform. Saat Anda menempelkan URL video yang didukung pada barisnya sendiri (dikelilingi oleh baris kosong), URL tersebut akan secara otomatis dikonversi menjadi pemutar video yang disematkan.

## Platform Video yang Didukung

| Platform | Format URL | Cara Mendapatkan URL |
|----------|------------|----------------------|
| YouTube | https://www.youtube.com/watch?v=VIDEO_ID atau https://youtu.be/VIDEO_ID | Salin URL dari address bar browser atau gunakan tombol "Share" |
| Vimeo | https://vimeo.com/VIDEO_ID | Salin URL dari address bar browser atau gunakan tombol "Share" |
| Loom | https://loom.com/share/VIDEO_ID | Gunakan tombol "Share" setelah merekam atau dari pustaka video |
| Wistia | https://SUBDOMAIN.wistia.com/medias/VIDEO_ID | Salin URL dari browser atau gunakan opsi "Share & Embed" |
| Arcade | https://app.arcade.software/share/VIDEO_ID | Gunakan tombol "Share" dari pustaka demo Anda |
| Bunny CDN | https://iframe.mediadelivery.net/play/LIBRARY_ID/VIDEO_ID | Dapatkan URL iframe dari dashboard Bunny CDN |
| Direct MP4 | URL apa pun yang berakhiran .mp4 | Gunakan link langsung ke file MP4 dari layanan hosting apa pun |

## Persyaratan Penting

1. **Baris Kosong:** URL video harus dikelilingi oleh baris kosong (baris kosong di atas dan di bawah)
2. **Link Berdiri Sendiri:** URL harus berada pada barisnya sendiri, tidak disematkan dalam teks lain
3. **Harus Berupa Link:** URL harus diformat sebagai link yang bisa diklik dalam markdown (bukan teks biasa)
4. **Format Tepat:** URL harus sesuai dengan pola yang ditunjukkan di atas

Sistem penyematan video secara otomatis mendeteksi pola-pola ini dan mengganti URL dengan pemutar video responsif yang berfungsi di semua perangkat.
