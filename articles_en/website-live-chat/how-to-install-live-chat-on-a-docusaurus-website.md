# How to install live chat on a Docusaurus website?Katalis.app integrates seamlessly with Docusaurus via the @Katalis.app/docusaurus-plugin. This plugin helps you easily install

the Katalis.app live-chat widget on a Docusaurus-powered website.

To install the plugin, follow the quick steps explained below.

Step 1. Add the plugin to your project.

yarn add @Katalis.app/docusaurus-plugin

or

npm install @Katalis.app/docusaurus-plugin --save

Step 2. Configure the plugin in docusaurus.config.js

// docusaurus.config.js
module.exports = {
  plugins: ["@Katalis.app/docusaurus-plugin"],
  themeConfig: {
    Katalis.app: {
      websiteToken: "Your website inbox token",
      baseURL: "https://app.katalis.app",  // optional
      enableInDevelopment: false,  // optional
      Katalis.appSettings: {
        hideMessageBubble: false,
        position: "left", // This can be left or right
        locale: "en", // Language to be set
        useBrowserLanguage: false, // Set widget language from user's browser
        darkMode: "auto", // [light, auto]
        type: "expanded_bubble",
        launcherTitle: "Chat with us",
      }
    }
  }
};Last updated on Apr 10, 2024