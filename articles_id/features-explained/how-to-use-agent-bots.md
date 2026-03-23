# Cara Menggunakan Agent Bot

AgentBot dapat terintegrasi dengan mulus ke inbox Katalis Anda sebagai bot penanganan pertanyaan pelanggan. Dengan Katalis, Anda bisa dengan mudah menghubungkan logika bot kustom ke penanganan percakapan melalui API AgentBot.

Dengan menghubungkan AgentBot ke inbox Anda, semua percakapan baru akan secara otomatis diberi status 'bot'. Katalis akan mengirim event percakapan ke URL bot Anda sebagai event webhook, memungkinkan AgentBot merespons melalui API Katalis secara real-time.

## Bagaimana AgentBot Bekerja?

Dijelaskan di bawah dalam alur kerja tipikal AgentBot.

1. AgentBot menerima event seperti `widget_triggered`, `message_created`, dan `message_updated` berdasarkan interaksi pelanggan.
2. AgentBot memproses informasi yang diterima untuk menghasilkan respons yang sesuai.
3. AgentBot juga bisa memanfaatkan API sistem eksternal untuk mengumpulkan informasi pelanggan tambahan, seperti status pesanan atau pemicu pemesanan.
4. AgentBot bisa memanfaatkan layanan seperti Rasa, Dialogflow, atau Lex untuk deteksi intent.
5. AgentBot bisa memposting respons yang dihasilkan kembali ke widget dengan memanfaatkan API Katalis seperti `message_create`.
6. AgentBot bisa mengubah status percakapan ke open untuk menyerahkan percakapan ke agen manusia.
7. Bot terus memantau percakapan terbuka untuk menyediakan informasi kontekstual kepada agen dukungan.

## Bagaimana Cara Kerja Penyerahan ke Agen Manusia?

Ketika agent bot terhubung ke inbox, percakapan dibuat dengan status "pending", memungkinkan bot melakukan triase percakapan sebelum menyerahkannya ke agen manusia. Jika bot menentukan bahwa bantuan agen manusia diperlukan, bot bisa menggunakan API pembaruan percakapan untuk mengubah status ke "open".

Terkadang agen ingin mengembalikan percakapan yang sudah diserahkan, kembali ke antrian bot. Agen bisa mengembalikan percakapan yang diserahkan ke antrian bot dengan mengubah status kembali ke "pending".

## Bagaimana Saya Bisa Menggunakan AgentBot?

Berikut beberapa contoh penggunaan:

1. Bisnis dengan volume pertanyaan dukungan pelanggan tinggi bisa menggunakan AgentBot untuk mengautentikasi dan memfilter pertanyaan, mengurangi beban kerja agen manusia dan meningkatkan efisiensi dukungan pelanggan.
2. Website e-commerce bisa mengintegrasikan AgentBot dengan database yang ada, memberikan pelanggan pembaruan real-time tentang status pesanan dan pengiriman.
3. Website berita dan konten bisa menggunakan AgentBot untuk mengirim rekomendasi kepada pengguna melalui pesan kartu.
4. Website pemesanan hotel dan film bisa menggunakan AgentBot untuk menangani pemesanan, reservasi, dan menjawab pertanyaan terkait.

## Membuat Agent Bot

### Cara membuat agent bot di akun Katalis Anda?

Anda bisa membuat agent bot dari pengaturan akun. Buka Settings → Bots. Anda akan melihat opsi seperti di bawah ini.

Klik "Add Bot" untuk membuat bot baru. Anda akan melihat opsi untuk memberikan nama, avatar, dan URL webhook.

### Cara menghubungkan inbox ke bot?

Buka inbox di mana Anda ingin menghubungkan bot. Di Konfigurasi Bot, pilih bot yang harus mengelola percakapan. Setelah Anda klik Save, Anda akan mulai menerima event webhook setiap kali percakapan atau pesan baru dibuat.

Untuk detail lebih lanjut tentang event yang didukung di webhook, silakan kunjungi dokumentasi Webhook di sini.
