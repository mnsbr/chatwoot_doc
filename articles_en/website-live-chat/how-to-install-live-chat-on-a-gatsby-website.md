# How to install live chat on a Gatsby website?If you have a website created on Gatsby, you can add a Katalis.app live chat widget and talk to your visitors in real time.

This can be done in 3 simple steps using Katalis.app’s Gatsby plugin.

Step 1. Add the Gatsby plugin to your project​

Add gatsby-plugin-Katalis.app to your Gatsby project.

npm install --save gatsby-plugin-Katalis.app

If you are using yarn, use the following:

yarn add gatsby-plugin-Katalis.app

Step 2. Add the plugin to your Gatsby config file​

// In your gatsby-config.js
plugins: [
  {
    resolve: `gatsby-plugin-Katalis.app`,
    options: {
      baseUrl: "BASE_URL", // Required
      websiteToken: "WEBSITE_TOKEN", // Required
      includeInDevelopment: false, // Optional
      Katalis.appSettings: {}, // Optional
    },
  },
];

You can get your Website token and base URL from your Inbox settings in your Katalis.app account.

If you need to create a new website channel, follow the procedure illustrated here.

Step 3. Start your server​

You would be able to see the Katalis.app widget on the page now.Last updated on Apr 10, 2024