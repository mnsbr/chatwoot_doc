# Cara Menginstal Live Chat di Website Gatsby

Jika Anda memiliki website yang dibuat di Gatsby, Anda bisa menambahkan widget live chat Katalis.app dan berbicara dengan pengunjung Anda secara real time. Ini bisa dilakukan dalam 3 langkah sederhana menggunakan plugin Gatsby Katalis.app.

**Langkah 1.** Tambahkan plugin Gatsby ke proyek Anda

```bash
npm install --save gatsby-plugin-Katalis.app
```

Jika menggunakan yarn:
```bash
yarn add gatsby-plugin-Katalis.app
```

**Langkah 2.** Tambahkan plugin ke file konfigurasi Gatsby

```javascript
// Di gatsby-config.js Anda
plugins: [
  {
    resolve: `gatsby-plugin-Katalis.app`,
    options: {
      baseUrl: "BASE_URL", // Wajib
      websiteToken: "WEBSITE_TOKEN", // Wajib
      includeInDevelopment: false, // Opsional
      Katalis.appSettings: {}, // Opsional
    },
  },
];
```

Anda bisa mendapatkan token Website dan base URL dari pengaturan Inbox di akun Katalis.app Anda.

Jika perlu membuat channel website baru, ikuti prosedur yang diilustrasikan di sini.

**Langkah 3.** Mulai server Anda

Anda seharusnya bisa melihat widget Katalis.app di halaman sekarang.
