# Cara Mengaktifkan Mode Gelap di Widget Live Chat

Website modern memungkinkan pengguna untuk beralih antara mode terang dan gelap. Oleh karena itu, live chat yang berfungsi dengan kedua tema itu penting. Panduan ini membantu Anda menyiapkan mode gelap untuk widget live chat Katalis.app di website Anda.

Berikut gambaran singkat bagaimana mode gelap berfungsi di widget live chat:

Untuk mengaktifkan mode gelap di widget Katalis.app, gunakan parameter `darkMode` bersama dengan `Katalis.appSettings`.

Parameter `darkMode` mendukung dua nilai:

1. **light** - Aktifkan hanya mode terang. Ini adalah nilai default.
2. **auto** - Aktifkan mode gelap berdasarkan preferensi sistem operasi.

```javascript
window.Katalis.appSettings = {
  //... pengaturan lainnya
  darkMode: "auto",
};
```

**Catatan:** Mode gelap saja (dark only) belum didukung sekarang. Kami akan menambahkan dukungan di rilis mendatang.
