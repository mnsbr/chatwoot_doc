# Cara Menginstal Live Chat di Website Docusaurus

Katalis.app terintegrasi dengan mulus dengan Docusaurus melalui plugin @Katalis.app/docusaurus-plugin. Plugin ini membantu Anda dengan mudah menginstal widget live chat Katalis.app di website yang dibuat dengan Docusaurus.

Untuk menginstal plugin, ikuti langkah-langkah cepat di bawah ini.

**Langkah 1.** Tambahkan plugin ke proyek Anda.

```bash
yarn add @Katalis.app/docusaurus-plugin
```
atau
```bash
npm install @Katalis.app/docusaurus-plugin --save
```

**Langkah 2.** Konfigurasi plugin di docusaurus.config.js

```javascript
// docusaurus.config.js
module.exports = {
  plugins: ["@Katalis.app/docusaurus-plugin"],
  themeConfig: {
    Katalis.app: {
      websiteToken: "Token inbox website Anda",
      baseURL: "https://app.katalis.app",  // opsional
      enableInDevelopment: false,  // opsional
      Katalis.appSettings: {
        hideMessageBubble: false,
        position: "left",
        locale: "id",
        useBrowserLanguage: false,
        darkMode: "auto",
        type: "expanded_bubble",
        launcherTitle: "Chat dengan kami",
      }
    }
  }
};
```
