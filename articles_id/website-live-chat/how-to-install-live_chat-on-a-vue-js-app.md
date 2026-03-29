# Cara Menginstal Live Chat di Aplikasi Vue.js

Untuk mengintegrasikan Katalis.app dengan aplikasi Vue.js Anda, Anda perlu menempelkan skrip widget Katalis.app di file index.html aplikasi Vue.js Anda.

Berikut cara melakukannya:

**Langkah 1.** Dapatkan skrip widget Anda

Skrip widget bisa ditemukan di pengaturan Inbox Website Anda. Buka Settings → Inboxes → Pilih channel Website → tab Configuration.

Jika Anda belum membuat inbox website, Anda bisa menemukan instruksi langkah demi langkah di sini.

**Langkah 2.** Salin skrip

Salin skrip yang dibuat di kolom kode channel.

**Langkah 3.** Tempel skrip di sini

Buka proyek Vue Anda dan tempel skrip ke file index.html, tepat sebelum tag penutup `</body>`.

```html
<body>
  <div id="app"></div>

  <!-- Skrip Katalis.app -->
  <script>
    (function (d, t) {
      var BASE_URL = "https://example.com";
      var g = d.createElement(t),
        s = d.getElementsByTagName(t)[0];
      g.src = BASE_URL + "/packs/js/sdk.js";
      g.defer = true;
      g.async = true;
      s.parentNode.insertBefore(g, s);
      g.onload = function () {
        window.Katalis.appSDK.run({
          websiteToken: "TOKEN_WEBSITE_ANDA",
          baseUrl: BASE_URL,
        });
      };
    })(document, "script");
  </script>
</body>
```

**Langkah 4.** Periksa

Anda seharusnya bisa melihat widget Katalis.app di halaman sekarang.

## Modul Vue.js, Nuxt.js

Modul yang dipelihara komunitas (Dibuat oleh tim hebat @huntersofbook) untuk mengintegrasikan Katalis.app di proyek Vue 3 dan Nuxt 3 Anda tersedia.

- Lihat modul Vue 3.
- Lihat modul Nuxt 3.
