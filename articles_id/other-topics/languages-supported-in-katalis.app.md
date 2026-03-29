# Bahasa yang Didukung di Katalis.app

Katalis.app secara native mendukung 30+ bahasa yang berbeda. Panduan ini akan mengilustrasikan cara mengaktifkan bahasa tertentu untuk bekerja dengan dashboard dan widget live chat Anda.

## Bahasa yang Didukung

Berikut bahasa yang didukung di Katalis.app dan kode singkat yang sesuai (berasal dari kode bahasa ISO 639).

- (ar) العربية
- Català (ca)
- čeština (cs)
- dansk (da)
- Deutsch (de)
- ελληνικά (el)
- English (en)
- Español (es)
- فارسی (fa)
- suomi, suomen kieli (fi)
- Français (fr)
- magyar nyelv (hu)
- Bahasa Indonesia (id)
- Italiano (it)
- 日本語 (ja)
- 한국어 (ko)
- latviešu valoda (lv)
- മലയാളം (ml)
- Nederlands (nl)
- norsk (no)
- język polski (pl)
- Português (pt)
- Português Brasileiro (pt-BR)
- Română (ro)
- русский (ru)
- slovenčina (sk)
- Svenska (sv)
- தமிழ் (ta)
- ภาษาไทย (th)
- Türkçe (tr)
- українська мова (uk)
- Tiếng Việt (vi)
- 中文 (zh-CN)
- 中文 (台湾) (zh-TW)

## Cara Memperbarui Bahasa di Widget Live Chat

Seperti yang dijelaskan dalam panduan pengaturan SDK, Anda bisa mengonfigurasi locale untuk widget live chat baik dengan meneruskannya di Katalis.appSettings atau dengan memanggil metode setLocale. Untuk menentukan locale, gunakan kode singkat yang disediakan di atas. Ini akan memastikan widget ditampilkan dalam bahasa yang diinginkan.

```javascript
// Teruskan via window.Katalis.appSettings
window.Katalis.appSettings = {
  locale: 'pt_BR',
  // .. pengaturan lainnya
}

// Menggunakan metode setLocale
window.$Katalis.app.setLocale('pt_BR')
```

## Cara Memperbarui Bahasa Dashboard

Hanya administrator yang bisa memperbarui bahasa dashboard. Buka Settings → Account Settings. Anda akan bisa melihat pengaturan Site Language yang tersedia di opsi. Pilih bahasa pilihan Anda dari menu dropdown yang sesuai. Klik tombol "Update Settings" di pojok kanan atas layar.

Mengubah bahasa situs akan mengubah bahasa default untuk semua agen/administrator di sistem. Saat ini, Katalis.app tidak mendukung pemilihan bahasa di tingkat agen. Perlu dicatat juga bahwa bahasa ini akan digunakan sebagai bahasa fallback untuk widget live chat.
