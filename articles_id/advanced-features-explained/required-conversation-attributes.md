
# Atribut Percakapan Wajib

Required Conversation Attributes memungkinkan admin mewajibkan agen mengisi atribut kustom tertentu sebelum menyelesaikan percakapan. Ini memastikan tim Anda menangkap data terstruktur secara konsisten — baik itu kategori resolusi, tingkat keparahan, atau kolom lain yang penting untuk pelaporan dan pelacakan kualitas.

## Cara Kerjanya

Ketika admin mengonfigurasi atribut wajib, agen akan diminta dengan modal setiap kali mencoba menyelesaikan percakapan yang kekurangan nilai tersebut. Percakapan tidak bisa diselesaikan sampai semua kolom wajib diisi.

Jika atribut sudah memiliki nilai (diatur sebelumnya selama percakapan), resolusi berjalan normal tanpa prompt apa pun.

## Menyiapkan Atribut Wajib

1. Navigasi ke Settings → Conversation Workflows.
2. Di bawah Attributes required on resolution, klik Add Attributes.
3. Pilih satu atau lebih atribut kustom level percakapan dari dropdown.
4. Atribut yang dipilih sekarang berlaku saat resolusi.
5. Untuk menghapus atribut dari daftar wajib, klik ikon hapus di sebelahnya.

## Pengalaman Agen

Ketika agen mengklik Resolve pada percakapan yang kekurangan atribut wajib:

1. Modal muncul yang mencantumkan semua atribut wajib yang belum diisi.
2. Agen mengisi nilai menggunakan input yang sesuai untuk setiap jenis — text, number, link, date, list, atau checkbox.
3. Setelah semua kolom diisi, agen mengklik Resolve conversation untuk menyimpan nilai dan menyelesaikan dalam satu langkah.

Jika agen belum siap untuk menyelesaikan, mereka bisa mengklik Cancel untuk kembali ke percakapan tanpa membuat perubahan.

## Jenis Atribut yang Didukung

Anda bisa menandai atribut kustom level percakapan apa pun sebagai wajib. Jenis yang didukung adalah:

- **Text** - Input teks bebas
- **Number** - Nilai numerik
- **Link** - URL (divalidasi untuk format yang benar)
- **Date** - Pemilih tanggal
- **List** - Pilihan dropdown dari opsi yang telah ditentukan
- **Checkbox** - Pilihan Ya/Tidak

## Tindakan Massal

Saat menyelesaikan percakapan secara massal, aturan yang sama berlaku. Percakapan yang kekurangan atribut wajib akan dilewati, dan notifikasi akan menginformasikan agen bahwa percakapan tersebut tidak bisa diselesaikan. Percakapan lain yang memenuhi persyaratan akan diselesaikan secara normal.

## Hal yang Perlu Diperhatikan

- Hanya admin yang bisa mengonfigurasi atribut mana yang wajib.
- Atribut wajib hanya berlaku pada resolusi manual (individu atau massal). Resolusi berbasis API tidak menegakkan pemeriksaan atribut.
- Jika definisi atribut kustom dihapus, atribut tersebut secara otomatis dihapus dari daftar wajib.

## Ketersediaan

Tersedia di:
- Cloud: Paket Business dan Enterprise
- Self-hosted: Tersedia di semua paket self-hosted berbayar
