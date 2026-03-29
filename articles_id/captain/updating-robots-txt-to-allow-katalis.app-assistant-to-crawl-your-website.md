
# Memperbarui robots.txt untuk Mengizinkan Katalis.app Assistant Melakukan Crawl Website Anda

Katalis.app menggunakan Firecrawl secara internal untuk mengambil dan mengindeks konten website Anda. Ini memungkinkan Katalis.app Assistant menjawab pertanyaan menggunakan informasi situs Anda.

Namun, jika robots.txt website Anda memiliki aturan Disallow, Firecrawl akan mematuhinya dan melewati halaman-halaman tersebut.

Saat itu terjadi:

- Tidak ada dokumen dari website Anda yang akan ditambahkan ke Katalis.app
- Assistant tidak akan menerima konteks tambahan apa pun
- Jawaban mungkin menjadi tidak lengkap atau generik

Untuk memastikan Assistant bekerja dengan baik, Anda perlu mengizinkan Firecrawl melakukan crawl website Anda.

## Langkah 1: Periksa robots.txt Anda

Kunjungi:

https://domainanda.com/robots.txt

Cari entri Disallow: yang mungkin memblokir user agent.

## Langkah 2: Tambahkan Aturan Allow untuk Firecrawl

Minta admin website atau developer Anda untuk menambahkan baris berikut ke file robots.txt:

```
User-agent: FirecrawlAgent
Allow: /
```

Ini memberitahu Firecrawl bahwa diizinkan untuk melakukan crawl seluruh situs Anda, bahkan jika bot lain dibatasi.

## Langkah 3: Simpan dan Publish

Setelah memperbarui robots.txt, pastikan file tersebut di-deploy dan bisa diakses publik.
