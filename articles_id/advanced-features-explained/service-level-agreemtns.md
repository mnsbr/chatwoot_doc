# Service Level Agreement (SLA)

Sebagai penyedia layanan, Service Level Agreement (SLA) Anda adalah pengaturan kontraktual antara Anda dan pelanggan yang mendefinisikan tingkat layanan yang Anda berkomitmen untuk berikan. SLA Anda menentukan metrik kinerja yang diharapkan, seperti waktu respons, ketersediaan, dan waktu resolusi, yang telah Anda setujui untuk disediakan. SLA ini membuat Anda bertanggung jawab atas kualitas layanan yang diberikan, memastikan tingkat dukungan yang konsisten dan andal untuk pelanggan Anda.

Katalis.app memungkinkan Anda melacak metrik berikut:

- **FRT (First Response Time)**: Metrik ini mengacu pada waktu yang dibutuhkan agen untuk merespons pertanyaan atau permintaan awal pelanggan. Ini adalah ukuran penting dari responsivitas, karena pelanggan mengharapkan perhatian cepat terhadap masalah atau pertanyaan mereka.

- **NRT (Next Response Time)**: Metrik ini berfokus pada waktu antara pesan tindak lanjut pelanggan dan respons berikutnya dari agen. Ini memastikan bahwa penyedia mempertahankan tingkat keterlibatan yang konsisten dan menjaga percakapan tetap berjalan.

- **RT (Resolution Time)**: Metrik ini menangkap total waktu yang dibutuhkan agen untuk sepenuhnya menyelesaikan masalah atau pertanyaan pelanggan, dari kontak awal hingga resolusi akhir. Ini adalah indikator utama efisiensi dan efektivitas penyedia dalam menangani kebutuhan pelanggan.

## Membuat SLA

Anda bisa mengonfigurasi SLA dari halaman settings, admin diizinkan untuk membuat dan menghapus SLA. Perlu diperhatikan bahwa Anda tidak bisa mengubah atau memodifikasi SLA setelah dibuat. Untuk membuat SLA, Anda perlu menambahkan setidaknya satu metrik untuk dilacak.

## Menerapkan SLA

Anda bisa menggunakan aturan automasi untuk menetapkan SLA saat event percakapan dipicu. Berikut contoh menetapkan SLA "Enterprise P0" saat percakapan dibuat oleh alamat email tertentu dan prioritas diatur ke Urgent.

Setelah percakapan cocok dengan kondisi dan event SLA, kebijakan SLA otomatis diterapkan. Setelah SLA diterapkan, SLA tidak bisa dihapus dari percakapan.

Percakapan dengan SLA aktif yang mendekati batas waktu akan muncul di UI seperti berikut.
