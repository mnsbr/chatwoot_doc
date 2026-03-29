# How to send additional user information to Katalis.app using SDK?The Katalis.app website SDK enables you to send additional user information to Katalis.app.

If you have installed our code on your website, the SDK would expose window.$Katalis.app object. To make sure that the SDK
has been loaded completely, please make sure that you listen to Katalis.app:ready event as follows:

window.addEventListener("Katalis.app:ready", function () {
  // Use window.$Katalis.app here
  // ...
});

If you would like to listen to the messages in the widget you can use the following event.

window.addEventListener('Katalis.app:on-message', function(e) {
  console.log('Katalis.app:on-message', e.detail)
})

SDK settings​

To hide the bubble, you can use the setting mentioned below.

Note: If you use this, you must also trigger the widget.

window.Katalis.appSettings = {
  hideMessageBubble: false,
  showUnreadMessagesDialog: false, // Disable the unread message dialog
  position: "left", // This can be left or right
  locale: "en", // Language to be set
  useBrowserLanguage: false, // Set widget language from user's browser
  type: "standard", // [standard, expanded_bubble]
  darkMode: "auto", // [light, auto]
  // baseDomain: "yourdomain.com" // configure if you want to track users across subdomains
};

Use browser language in your live chat widget automatically

To show the live chat widget in the user's browser locale, set the useBrowserLanguage to true in
the window.Katalis.appSettings mentioned above.

Note: If useBrowserLanguage is set to true, The locale mentioned will be ignored. If the browser language is not
supported by Katalis.app, the locale mentioned under locale will be used. If that's also missing, the widget will fall back
to the locale of the agent dashboard.

Dark Mode​

Katalis.app live-chat widget supports dark mode v2.4.0 onwards. To enable the dark mode, follow the steps mentioned here.

Widget designs​

Katalis.app supports two designs for the widget.

1.  Standard (default)

2.  Expanded bubble

If you are using expanded bubble, you can customize the text used in the bubble by setting launcherTitle parameter on
Katalis.appSettings as described below.

window.Katalis.appSettings = {
  type: "expanded_bubble",
  launcherTitle: "Chat with us",
};

Enable popout window​

In order to enable the popout window, add the following configuration to Katalis.appSettings. This option is disabled by
default.

window.Katalis.appSettings = {
  // ...Other Config
  showPopoutButton: true,
}

You can also popout the chat window programatically with the `popoutChatWindow()` method.

Custom messages​

Customize the welcome and availability messages shown in the widget header and team status indicators.

window.Katalis.appSettings = {
  // ...Other Config

  welcomeTitle: "Need help?", // Custom widget header
  welcomeDescription: "We’re here to support you.", // Header subtitle
  availableMessage: "We’re online and ready to chat!", // When team is online
  unavailableMessage: "We’re currently offline." // When team is unavailable
};

Feature toggles

Enable or disable optional UI features inside the widget:

window.Katalis.appSettings = {
  // ...Other Config

  enableFileUpload: true, // Show file attachment button
  enableEmojiPicker: true, // Enable emoji picker in the chat input
  enableEndConversation: true // Let users end the conversation
};

Programatically open the popout window​

You can open the popout window programatically with the popoutChatWindow() method.

To initiate this, call the method like below.

window.$Katalis.app.popoutChatWindow();

Toggle the widget bubble visibility​

If you want to hide/show the Katalis.app widget bubble, you can do so with toggleBubbleVisibility('show/hide')

Example

window.$Katalis.app.toggleBubbleVisibility("show"); // to display the bubble
window.$Katalis.app.toggleBubbleVisibility("hide"); // to hide the bubble

Trigger widget programmatically

If you want to open the chat window by clicking a link on the website, follow the method below. In your action, call the
Katalis.app SDK as described below.

window.$Katalis.app.toggle();

// Toggle widget by passing state
window.$Katalis.app.toggle("open"); // To open widget
window.$Katalis.app.toggle("close"); // To close widget

Set the user in the widget​

window.$Katalis.app.setUser("<unique-identifier-key-of-the-user>", {
  email: "<[email protected]>",
  name: "<name-of-the-user>",
  avatar_url: "<avatar-url-of-the-user>",
  phone_number: "<phone-number-of-the-user>",
});

setUser accepts an identifier which can be a user_id in your database or any unique parameter which represents a user.
You can pass email, name, avatar_url, phone_number as params. Support for additional parameters is in progress.

Ensure you reset the session when the user logs out of your app.

Identity validation using HMAC​

To disallow impersonation and to keep the conversation with your customers private, we recommend setting up the identity
validation in Katalis.app. Identity validation is enabled by generating an HMAC(hash based message authentication code)
based on the identifier attribute, using SHA256. Along with the identifier you can pass identifier_hash also as shown
below to make sure that the user is correct one.

window.$Katalis.app.setUser(`<unique-identifier-key-of-the-user>`, {
  name: "", // Name of the user
  avatar_url: "", // Avatar URL
  email: "", // Email of the user
  identifier_hash: "", // Identifier Hash generated based on the webwidget hmac_token
  phone_number: "", // Phone Number of the user
  description: "", // description about the user
  country_code: "", // Two letter country code
  city: "", // City of the user
  company_name: "", // company name
  social_profiles: {
    twitter: "", // Twitter user name
    linkedin: "", // LinkedIn user name
    facebook: "", // Facebook user name
    github: "", // Github user name
  },
});

To generate HMAC, read identity validation. Note that implementing HMAC authentication will allow chat history to
persist across sessions.

Set custom attributes​

To set additional information about the customer, you can use customer custom attributes field. Read more about custom
attributes here.

To set a custom attribute, call setCustomAttributes as follows

window.$Katalis.app.setCustomAttributes({
  accountId: 1,
  pricingPlan: "paid",

  // Here the key which is already defined in custom attribute
  // Value should be based on type (Currently support Number, Date, String and Number)
});

You can view these information in the sidepanel of a conversation.

To delete a custom attribute, use deleteCustomAttribute as follows

window.$Katalis.app.deleteCustomAttribute("attribute-key");

Set language manually​

window.$Katalis.app.setLocale("en");

To set the language manually, use the setLocale function.

Set labels on the conversation​

Please note that the labels will be set on a conversation if the user has not started a conversation. In that case, the
following items will not have any effect:

window.$Katalis.app.setLabel("support-ticket");

window.$Katalis.app.removeLabel("support-ticket");

Refresh the session (use this while you logout the user from your app)​

window.$Katalis.app.reset();

Widget errors​

To see any errors in the widget, please make sure that you listen to Katalis.app:event event as follows:

window.addEventListener("Katalis.app:error", function () {
  // ...
});

Note: This feature is available in v2.3.0 and later.

Customize the welcome header, description

You can change:

  - The welcome title and description

  - Messages shown when your team is online or offline

  - Selectively enable UI features like file upload, emoji picker, and end conversation button

window.Katalis.appSettings = {
  welcomeTitle: 'Need help?',
  welcomeDescription: 'We’re here to support you.',
  availableMessage: 'We’re online and ready to chat!',
  unavailableMessage: 'We’re currently offline.',

  enableFileUpload: true,
  enableEmojiPicker: true,
  enableEndConversation: true
 };Last updated on Jul 24, 2025