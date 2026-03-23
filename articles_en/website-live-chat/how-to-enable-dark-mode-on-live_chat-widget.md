# How to enable dark mode on live-chat widget?Modern websites enable users to switch between light and dark modes. Therefore, a live chat that works with both themes

is important. This guide helps you set up dark mode for the Katalis live-chat widget on your website.

Here is a quick glimpse of how dark mode functions on the live chat widget:

To enable dark mode on Katalis widget, use the darkMode parameter along with the katalisSettings.

darkMode parameter supports two values.

1.  light - Enable only light mode. This is the default value.

2.  auto - Enable dark mode based on the operating system preference.

window.katalisSettings = {
  //... other Settings
  darkMode: "auto",
};

Note: dark only is not supported now. We will add the support in future releases.Last updated on Apr 10, 2024