
# Cara Kerja AI Credits di Captain

Panduan ini menjelaskan bagaimana AI credits dikonsumsi, bagaimana credits diperbarui saat top up, kapan pembaruan bulanan terjadi, apa yang terjadi saat Anda mengganti paket, dan bagaimana notifikasi bekerja jika credits Anda habis.

## Bagaimana AI Credits Dikonsumsi?

AI credits dipotong setiap kali tindakan AI dilakukan. Contohnya termasuk:

- Respons Captain assistant
- Pencarian Copilot
- Tindakan editor (rephrase, summarise, suggest a reply)
- Saran Label
- Workflow atau automation apa pun yang memicu pemanggilan model
- Transkripsi audio

Model yang berbeda mengonsumsi credits dengan tingkat yang berbeda. Saat ini, semua tindakan mengonsumsi 1 credit per pesan, karena hanya konfigurasi model tetap yang didukung.

Ini akan berubah di masa depan saat lebih banyak opsi model didukung, di mana model yang berbeda mungkin mengonsumsi jumlah credit yang berbeda per tindakan.

Jika tindakan tidak bisa diselesaikan karena credits tidak cukup, terjadi kegagalan credit (dijelaskan di bawah).

## Kapan Penggunaan Direset?

Penggunaan direset ke 0 hanya saat pembaruan bulanan.

Penggunaan TIDAK direset saat:

- Top up credits
- Mengganti paket
- Mengubah jumlah seat

Artinya Anda bisa top up credits kapan saja tanpa kehilangan pelacakan siklus penggunaan saat ini.

## Bagaimana AI Credits Diperbarui?

### 1. Top Up Credits

Saat Anda membeli credits tambahan, credits tersebut ditambahkan ke saldo yang ada.

**Contoh:**
- Credits sebelumnya: 1500
- Top-up: 1000
- Total credits baru: 2500

Tidak ada nilai lain yang berubah.

### 2. Pembaruan Bulanan

Setiap paket menyertakan jatah credit gratis bulanan. Saat pembaruan, kami menyesuaikan penggunaan dan credits berdasarkan berapa banyak yang Anda konsumsi di bulan sebelumnya.

**Kasus A: Tidak ada penggunaan**

Penggunaan: 0 → Total credits Anda tidak berubah.

**Kasus B: Penggunaan kurang dari credit gratis bulanan**

- Credits sebelumnya: 1500
- Penggunaan: 200
- Credit gratis bulanan: 300

→ Tidak ada pemotongan yang diterapkan.
→ Total credits tetap 1500.
→ Penggunaan direset ke 0.

**Kasus C: Penggunaan melebihi credit gratis bulanan**

- Credits sebelumnya: 1500
- Penggunaan: 600
- Credit gratis bulanan: 500

Kelebihan = 600 − 500 = 100

→ Potong kelebihan dari total credits.
→ Total credits baru: 1400
→ Penggunaan direset ke 0.

### 3. Mengganti Paket

Saat Anda berganti paket, credit gratis bulanan Anda mungkin bertambah atau berkurang.

**Contoh:**
- Paket Startup: 300 credit gratis
- Paket Business: 500 credit gratis
- Paket Enterprise: 800 credit gratis

Jika Anda beralih dari Startups ke Business, total credits Anda akan bertambah 200. Demikian juga jika Anda downgrade dari Business ke Startups, total credits akan berkurang 200.

Penggunaan Anda tetap tidak berubah.

## Kegagalan Credit (Penanganan Credit Tidak Cukup)

Kegagalan credit terjadi saat tindakan AI dipicu tetapi tidak ada cukup credits untuk melakukannya.

### Apa yang Terjadi Saat Kegagalan Credit

- Tindakan tidak dieksekusi. Fallback yang tersedia akan dijalankan — misalnya, jika assistant tidak bisa merespons, percakapan ditransfer langsung ke agen.
- Kami mencatat tindakan yang gagal secara internal untuk audit.
