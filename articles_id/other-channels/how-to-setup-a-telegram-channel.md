# Cara Menyiapkan Channel Telegram

**Langkah 1.** Buka Settings → Inboxes → "Add Inbox".

**Langkah 2.** Klik ikon "Telegram".

**Langkah 3.** Buat bot telegram baru menggunakan Telegram BotFather.

**Langkah 4.** Masukkan API token dari bot Telegram dan klik "Create Telegram Channel".

**Langkah 5.** "Add agents" ke inbox Telegram Anda.

Pengaturan inbox selesai.

**Langkah 6.** Buka halaman pengaturan Inbox dan verifikasi bahwa nama inbox cocok dengan username bot yang dibuat menggunakan BotFather.

**Langkah 7.** Kirim pesan ke bot Telegram. Periksa inbox Telegram Katalis.app untuk pesan baru.

## FAQ

### Apakah Katalis.app mendukung akun Telegram Business Bot?

Ya — dukungan untuk bot mode Telegram Business ditambahkan di Katalis.app v4.3.0 (18 Jun 2025).

### Cara mengaktifkan Business Bot?

1. Di @BotFather jalankan `/business_mode`, pilih bot Anda, dan konfirmasi.
2. Buat inbox Telegram baru di Katalis.app (Settings → Inboxes → Add Inbox → Telegram) dan tempel token bot yang sama.
3. Katalis.app otomatis mendeteksi Business Mode dan mendaftarkan webhook yang benar.
4. Untuk hasil terbaik, simpan Business bot ini di inbox tersendiri, terpisah dari bot standar yang sudah Anda gunakan.

### Masalah yang diketahui dengan Business Bot

- **Jendela balasan 24 jam** – Telegram hanya mengizinkan bot (dan Katalis.app) untuk membalas dalam 24 jam dari pesan terakhir pelanggan.
- Jika pengguna sebelumnya sudah pernah chat dengan bot yang sama di luar Business Mode, balasan mungkin tampak berasal dari bot daripada akun Business; membuat bot & inbox Business khusus menghindari kebingungan ini.
- API Telegram Business saat ini kurang kaya fitur dibandingkan Bot API reguler (misalnya, tidak ada typing indicators, terbatas).
