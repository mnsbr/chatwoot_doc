# Cara Menggunakan Audit Log

Audit Log adalah fitur Enterprise. Ini menyimpan catatan aktivitas yang terjadi di akun Anda, yang bisa Anda lacak untuk mengaudit akun, tim, atau layanan Anda. Pada dasarnya, audit log menjawab empat W untuk Anda:

- Who (Siapa)
- What (Apa)
- When (Kapan)
- Where (Di mana)

Atau, siapa melakukan apa, kapan dan dari mana?

## Di Mana Menemukan Audit Log di Katalis.app?

**Langkah 1.** Jika fitur tersedia untuk Anda, Anda bisa menemukannya dengan membuka 'Settings' → 'Audit Logs'.

**Langkah 2.** Telusuri log Anda. Gulir ke bawah untuk menemukan entri yang diinginkan atau gunakan navigasi untuk berpindah halaman.

**Tips pro:** Gunakan cmd/ctrl + F untuk mencari entri yang diinginkan dengan cepat.

Anda akan menemukan entri di bawah tiga header: Activity, Time, dan IP Address.

## Aktivitas yang Dilacak Melalui Audit Log

Setiap kali salah satu aktivitas berikut terjadi di akun Anda, entri dibuat beserta tanggal dan timestamp, serta alamat IP. Lihat daftar lengkap di bawah.

### Log aktivitas pengguna

- <Nama | Email> mengubah status sendiri ke online, offline, busy
- <Nama | Email> masuk
- <Nama | Email> keluar
- <Nama | Email> mengubah status ketersediaan <Nama | Email> ke <online | offline | busy>
- <Nama | Email> mengundang pengguna sebagai <agent | admin>
- <Nama | Email> mengubah peran pengguna menjadi <agent | admin>

### Log aktivitas akun

- <Nama | Email> memperbarui konfigurasi akun.

### Log aturan automasi

- <Nama | Email> membuat aturan automasi baru (#rule-id)
- <Nama | Email> memperbarui aturan automasi (#rule-id)
- <Nama | Email> menghapus aturan automasi (#rule-id)

### Log makro

- <Nama | Email> membuat makro baru (#macro-id)
- <Nama | Email> memperbarui makro (#macro-id)
- <Nama | Email> menghapus makro (#macro-id)

### Log inbox

- <Nama | Email> membuat inbox baru (#inbox-id)
- <Nama | Email> memperbarui inbox (#inbox-id)
- <Nama | Email> menghapus inbox (#inbox-id)
- <Nama | Email> menambahkan <Nama1 | Email1>, <Nama2 | Email2> ke inbox (#inbox-id)
- <Nama | Email> menghapus <Nama1 | Email1>, <Nama2 | Email2> dari inbox (#inbox-id)

### Log webhook

- <Nama | Email> membuat webhook baru (#webhook-id)
- <Nama | Email> memperbarui webhook (#webhook-id)
- <Nama | Email> menghapus webhook (#webhook-id)

### Log tim

- <Nama | Email> membuat tim baru (#team-id)
- <Nama | Email> memperbarui tim (#team-id)
- <Nama | Email> menghapus tim (#team-id)
- <Nama | Email> menambahkan <Nama1 | Email1>, <Nama2 | Email2> ke tim (#team-id)
- <Nama | Email> menghapus <Nama1 | Email1>, <Nama2 | Email2> dari tim (#team-id)
