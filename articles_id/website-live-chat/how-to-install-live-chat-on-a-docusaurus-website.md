# Cara Menginstal Live Chat di Website Docusaurus

Katalis terintegrasi dengan mulus dengan Docusaurus melalui plugin @katalis/docusaurus-plugin. Plugin ini membantu Anda dengan mudah menginstal widget live chat Katalis di website yang dibuat dengan Docusaurus.

Untuk menginstal plugin, ikuti langkah-langkah cepat di bawah ini.

**Langkah 1.** Tambahkan plugin ke proyek Anda.

```bash
yarn add @katalis/docusaurus-plugin
```
atau
```bash
npm install @katalis/docusaurus-plugin --save
```

**Langkah 2.** Konfigurasi plugin di docusaurus.config.js

```javascript
// docusaurus.config.js
module.exports = {
  plugins: ["@katalis/docusaurus-plugin"],
  themeConfig: {
    katalis: {
      websiteToken: "Token inbox website Anda",
      baseURL: "https://app.katalis.app",  // opsional
      enableInDevelopment: false,  // opsional
      katalisSettings: {
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
