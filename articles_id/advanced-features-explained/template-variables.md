# Cara Menggunakan Variabel Template

Dengan variabel template, Anda bisa mempersonalisasi pesan dengan menyisipkan konten dinamis yang disesuaikan untuk setiap penerima. Dengan menambahkan placeholder dalam pesan, Anda bisa dengan mudah menyesuaikan komunikasi Anda dengan informasi seperti nama pelanggan, nomor pesanan, atau detail lainnya.

Contoh: Jika Anda mengirim pesan `Hey {{ contact.name }}, how may I help you?`, Katalis akan mengambil nama kontak dan mengirim pesan seperti `Hey John, how may I help you?`.

Anda juga bisa menggunakan variabel di canned response, makro, dan automasi.

## Membuat Variabel Template

Untuk menggunakan variabel, ketik dua kurung kurawal ganda `{{` saat menyusun pesan baru atau membuat canned response. Variabel akan muncul, dan Anda bisa memilih yang ingin digunakan.

Variabel template yang tersedia adalah:

- `conversation.id` — Untuk versi numerik dari ID percakapan.
- `contact.id` — Untuk versi numerik dari ID kontak.
- `contact.name` — Untuk nama lengkap kontak.
- `contact.first_name`
- `contact.last_name`
- `contact.phone_number`
- `agent.name`
- `agent.first_name`
- `agent.last_name`
- `agent.phone_number`

## Bagaimana Jika Saya Mengirim Variabel yang Tidak Ada?

Jika Anda mencoba mengirim variabel yang tidak terdefinisi, Katalis akan menampilkan peringatan.

## Cara Menambahkan Teks Fallback

Jika variabel yang didefinisikan tidak bisa diisi oleh sistem, teks fallback bisa digunakan untuk menggantikan nilai yang dimaksud. Contoh: jika variabel `contact.first_name` tidak bisa diisi, teks fallback yang sesuai bisa berupa 'there'.

Saat mendefinisikan teks fallback, pastikan Anda mengelilinginya dengan tanda kutip tunggal. Berikut contohnya: `{{ contact.first_name || 'there' }}`.
