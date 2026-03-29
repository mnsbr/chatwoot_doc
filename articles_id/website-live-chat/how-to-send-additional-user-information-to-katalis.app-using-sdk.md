# Cara Mengirim Informasi Pengguna Tambahan ke Katalis.app Menggunakan SDK

SDK website Katalis.app memungkinkan Anda mengirim informasi pengguna tambahan ke Katalis.app.

Jika Anda telah menginstal kode kami di website, SDK akan mengekspos objek `window.$Katalis.app`. Untuk memastikan SDK telah dimuat sepenuhnya, pastikan Anda mendengarkan event `Katalis.app:ready` sebagai berikut:

```javascript
window.addEventListener("Katalis.app:ready", function () {
  // Gunakan window.$Katalis.app di sini
});
```

Jika Anda ingin mendengarkan pesan di widget, Anda bisa menggunakan event berikut:

```javascript
window.addEventListener('Katalis.app:on-message', function(e) {
  console.log('Katalis.app:on-message', e.detail)
})
```

## Pengaturan SDK

Untuk menyembunyikan bubble, Anda bisa menggunakan pengaturan di bawah.

**Catatan:** Jika menggunakan ini, Anda juga harus memicu widget.

```javascript
window.Katalis.appSettings = {
  hideMessageBubble: false,
  showUnreadMessagesDialog: false,
  position: "left",
  locale: "id",
  useBrowserLanguage: false,
  type: "standard",
  darkMode: "auto",
};
```

### Gunakan bahasa browser secara otomatis

Untuk menampilkan widget live chat dalam lokal browser pengguna, atur `useBrowserLanguage` ke `true`.

**Catatan:** Jika `useBrowserLanguage` diatur ke `true`, lokal yang disebutkan akan diabaikan.

### Mode Gelap

Widget live chat Katalis.app mendukung mode gelap dari v2.4.0 ke atas.

### Desain Widget

Katalis.app mendukung dua desain untuk widget:
1. **Standard** (default)
2. **Expanded bubble**

```javascript
window.Katalis.appSettings = {
  type: "expanded_bubble",
  launcherTitle: "Chat dengan kami",
};
```

### Aktifkan Jendela Popout

```javascript
window.Katalis.appSettings = {
  showPopoutButton: true,
}
```

### Pesan Kustom

```javascript
window.Katalis.appSettings = {
  welcomeTitle: "Butuh bantuan?",
  welcomeDescription: "Kami di sini untuk mendukung Anda.",
  availableMessage: "Kami online dan siap chat!",
  unavailableMessage: "Kami sedang offline."
};
```

### Toggle Fitur

```javascript
window.Katalis.appSettings = {
  enableFileUpload: true,
  enableEmojiPicker: true,
  enableEndConversation: true
};
```

## Buka Jendela Popout Secara Programatis

```javascript
window.$Katalis.app.popoutChatWindow();
```

## Toggle Visibilitas Bubble Widget

```javascript
window.$Katalis.app.toggleBubbleVisibility("show"); // tampilkan bubble
window.$Katalis.app.toggleBubbleVisibility("hide"); // sembunyikan bubble
```

## Memicu Widget Secara Programatis

```javascript
window.$Katalis.app.toggle();
window.$Katalis.app.toggle("open");  // Buka widget
window.$Katalis.app.toggle("close"); // Tutup widget
```

## Mengatur Pengguna di Widget

```javascript
window.$Katalis.app.setUser("<kunci-pengenal-unik-pengguna>", {
  email: "<email@contoh.com>",
  name: "<nama-pengguna>",
  avatar_url: "<url-avatar-pengguna>",
  phone_number: "<nomor-telepon-pengguna>",
});
```

`setUser` menerima pengenal yang bisa berupa user_id di database Anda atau parameter unik yang mewakili pengguna.

Pastikan Anda mereset sesi ketika pengguna logout dari aplikasi Anda.

## Validasi Identitas Menggunakan HMAC

Untuk mencegah peniruan identitas dan menjaga percakapan dengan pelanggan tetap pribadi, kami merekomendasikan menyiapkan validasi identitas. Validasi identitas diaktifkan dengan menghasilkan HMAC berdasarkan atribut identifier, menggunakan SHA256.

```javascript
window.$Katalis.app.setUser(`<kunci-pengenal-unik>`, {
  name: "",
  avatar_url: "",
  email: "",
  identifier_hash: "",
  phone_number: "",
  description: "",
  country_code: "",
  city: "",
  company_name: "",
  social_profiles: {
    twitter: "",
    linkedin: "",
    facebook: "",
    github: "",
  },
});
```

**Catatan:** Mengimplementasikan autentikasi HMAC akan memungkinkan riwayat chat bertahan di seluruh sesi.

## Mengatur Atribut Kustom

```javascript
window.$Katalis.app.setCustomAttributes({
  accountId: 1,
  pricingPlan: "paid",
});
```

Untuk menghapus atribut kustom:
```javascript
window.$Katalis.app.deleteCustomAttribute("attribute-key");
```

## Mengatur Bahasa Secara Manual

```javascript
window.$Katalis.app.setLocale("id");
```

## Mengatur Label pada Percakapan

```javascript
window.$Katalis.app.setLabel("support-ticket");
window.$Katalis.app.removeLabel("support-ticket");
```

## Refresh Sesi (gunakan saat logout pengguna)

```javascript
window.$Katalis.app.reset();
```

## Error Widget

```javascript
window.addEventListener("Katalis.app:error", function () {
  // ...
});
```

**Catatan:** Fitur ini tersedia di v2.3.0 dan yang lebih baru.
