# Cara Membuat dan Menggunakan Atribut Kustom

Katalis.app memungkinkan Anda melacak informasi tambahan tentang percakapan dan kontak di luar atribut data standar seperti nama, email, dan lokasi. Informasi tambahan ini disebut atribut kustom dan bisa berupa apa saja yang ingin Anda lacak. Berikut beberapa contoh atribut kustom:

- Paket langganan
- Tanggal berlangganan
- Tanggal pendaftaran
- Item paling sering dipesan
- Link produk yang dipesan
- Tanggal transaksi terakhir

Atribut data kustom memungkinkan Anda melampirkan informasi tambahan ke percakapan atau pelanggan, seperti riwayat pembelian atau status akun. Informasi ini bisa digunakan untuk lebih memahami dan mengelompokkan basis pelanggan Anda.

Satu-satunya perbedaan antara atribut kustom dan standar adalah atribut data standar diperbarui secara otomatis.

## Cara Membuat Atribut Kustom?

**Langkah 1.** Buka Settings → Custom Attributes. Klik tombol "Add Custom Attribute".

**Langkah 2.** Modal akan terbuka, meminta detail tentang atribut kustom baru. Isi detail ini. Berikut contohnya:

Input yang diperlukan untuk membuat atribut kustom:

1. **Applies to** - Jenis atribut (Conversation/Contact).
2. **Display name** - Berfungsi sebagai label saat menampilkan atribut kustom.
3. **Key** - Pengenal unik yang dilampirkan ke atribut kustom.
4. **Description** - Deskripsi atribut kustom.
5. **Type** - Text, Number, Link, Date, List, dan Checkbox.

**Catatan:** Anda tidak bisa membuat atribut kustom dengan key yang sama dua kali dalam akun.

**Langkah 3.** Setelah memasukkan detail, klik tombol "Create". Jika berhasil, pesan "Custom attribute added successfully" akan ditampilkan.

## Cara Menggunakan Atribut Kustom Percakapan?

Anda bisa menambahkan atribut kustom percakapan dari sidebar percakapan. Ikuti langkah-langkah di bawah.

**Langkah 1.** Di dashboard, saat membuka percakapan tertentu, Anda akan menemukan bagian bertuliskan "Conversation Information". Klik tanda + untuk memperluasnya.

**Langkah 2.** Anda akan melihat opsi bertuliskan "Add Attributes" diikuti dropdown semua Atribut Kustom di akun Anda. Gunakan bilah pencarian untuk mempersempit pencarian. Atau klik salah satu untuk memilihnya. Jika perlu membuat yang baru, gunakan tombol "Create new attribute" dari dropdown yang sama.

**Langkah 3.** Berdasarkan jenis atribut yang ditambahkan (list, checkbox, text, dll.), isi sesuai keinginan.

Untuk mengedit/menghapus/menyalin atribut, arahkan kursor ke atribut tersebut untuk melihat opsi.

## Cara Menggunakan Atribut Kustom Kontak?

Ada dua cara untuk mengatur atribut kustom untuk kontak.

### Mengatur atribut melalui metode SDK

Untuk mengatur atribut kustom kontak, panggil metode `setCustomAttributes` sebagai berikut:

```javascript
window.$Katalis.app.setCustomAttributes({
  key: value,
  // Key adalah pengenal unik yang sudah ditentukan saat membuat atribut kustom
  // Value harus berdasarkan jenis (Saat ini mendukung Number, Date, String dan Number)
  // Pastikan key Anda selalu memiliki nilai yang valid dalam JSON
  // Anda perlu meratakan struktur JSON bersarang saat menggunakan fungsi ini
});
```

Anda bisa melihat atribut ini di sidepanel kontak/percakapan.

Untuk menghapus atribut kustom, gunakan `deleteCustomAttribute` sebagai berikut:

```javascript
window.$Katalis.app.deleteCustomAttribute("attribute-key");
```

**Catatan:** Sebelum versi v1.22, semua atribut ditampilkan sebagai teks. Mohon buat definisi baru untuk menampilkan nilai dengan benar.

### Mengatur atribut melalui panel samping kontak

Untuk menambahkan Atribut Kontak, ikuti prosedur yang sama seperti yang dijelaskan di atas untuk atribut kustom percakapan, tetapi gunakan bagian Atribut Kontak di sidebar chat Anda. Berdasarkan jenis atribut yang ditambahkan (list, checkbox, text, dll.), isi sesuai keinginan.
