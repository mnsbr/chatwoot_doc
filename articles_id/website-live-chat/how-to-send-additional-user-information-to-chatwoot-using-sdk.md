# Cara Mengirim Informasi Pengguna Tambahan ke Katalis Menggunakan SDK

SDK website Katalis memungkinkan Anda mengirim informasi pengguna tambahan ke Katalis.

Jika Anda telah menginstal kode kami di website, SDK akan mengekspos objek `window.$katalis`. Untuk memastikan SDK telah dimuat sepenuhnya, pastikan Anda mendengarkan event `katalis:ready` sebagai berikut:

```javascript
window.addEventListener("katalis:ready", function () {
  // Gunakan window.$katalis di sini
});
```

Jika Anda ingin mendengarkan pesan di widget, Anda bisa menggunakan event berikut:

```javascript
window.addEventListener('katalis:on-message', function(e) {
  console.log('katalis:on-message', e.detail)
})
```

## Pengaturan SDK

Untuk menyembunyikan bubble, Anda bisa menggunakan pengaturan di bawah.

**Catatan:** Jika menggunakan ini, Anda juga harus memicu widget.

```javascript
window.katalisSettings = {
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

Widget live chat Katalis mendukung mode gelap dari v2.4.0 ke atas.

### Desain Widget

Katalis mendukung dua desain untuk widget:
1. **Standard** (default)
2. **Expanded bubble**

```javascript
window.katalisSettings = {
  type: "expanded_bubble",
  launcherTitle: "Chat dengan kami",
};
```

### Aktifkan Jendela Popout

```javascript
window.katalisSettings = {
  showPopoutButton: true,
}
```

### Pesan Kustom

```javascript
window.katalisSettings = {
  welcomeTitle: "Butuh bantuan?",
  welcomeDescription: "Kami di sini untuk mendukung Anda.",
  availableMessage: "Kami online dan siap chat!",
  unavailableMessage: "Kami sedang offline."
};
```

### Toggle Fitur

```javascript
window.katalisSettings = {
  enableFileUpload: true,
  enableEmojiPicker: true,
  enableEndConversation: true
};
```

## Buka Jendela Popout Secara Programatis

```javascript
window.$katalis.popoutChatWindow();
```

## Toggle Visibilitas Bubble Widget

```javascript
window.$katalis.toggleBubbleVisibility("show"); // tampilkan bubble
window.$katalis.toggleBubbleVisibility("hide"); // sembunyikan bubble
```

## Memicu Widget Secara Programatis

```javascript
window.$katalis.toggle();
window.$katalis.toggle("open");  // Buka widget
window.$katalis.toggle("close"); // Tutup widget
```

## Mengatur Pengguna di Widget

```javascript
window.$katalis.setUser("<kunci-pengenal-unik-pengguna>", {
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
window.$katalis.setUser(`<kunci-pengenal-unik>`, {
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
window.$katalis.setCustomAttributes({
  accountId: 1,
  pricingPlan: "paid",
});
```

Untuk menghapus atribut kustom:
```javascript
window.$katalis.deleteCustomAttribute("attribute-key");
```

## Mengatur Bahasa Secara Manual

```javascript
window.$katalis.setLocale("id");
```

## Mengatur Label pada Percakapan

```javascript
window.$katalis.setLabel("support-ticket");
window.$katalis.removeLabel("support-ticket");
```

## Refresh Sesi (gunakan saat logout pengguna)

```javascript
window.$katalis.reset();
```

## Error Widget

```javascript
window.addEventListener("katalis:error", function () {
  // ...
});
```

**Catatan:** Fitur ini tersedia di v2.3.0 dan yang lebih baru.
