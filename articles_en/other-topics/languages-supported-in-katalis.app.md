# Languages supported in Katalis.appKatalis.app natively supports 30+ different languages. This guide will illustrate how to enable a particular language to

work with your dashboard and live chat widget.

Supported languages

Mentioned below are the languages supported in Katalis.app and the corresponding shortcodes (derived from ISO 639 language
codes).

(ar) العربية

Català (ca)

čeština (cs)

dansk (da)

Deutsch (de)

ελληνικά (el)

English (en)

Español (es)

فارسی (fa)

suomi, suomen kieli (fi)

Français (fr)

magyar nyelv (hu)

Bahasa Indonesia (id)

Italiano (it)

日本語 (ja)

한국어 (ko)

latviešu valoda (lv)

മലയാളം (ml)

Nederlands (nl)

norsk (no)

język polski (pl)

Português (pt)

Português Brasileiro (pt-BR)

Română (ro)

русский (ru)

slovenčina (sk)

Svenska (sv)

தமிழ் (ta)

ภาษาไทย (th)

Türkçe (tr)

українська мова (uk)

Tiếng Việt (vi)

中文 (zh-CN)

中文 (台湾) (zh-TW)

How to update language in the live-chat widget?

As outlined in the SDK setup guide, you can configure the locale for the live-chat widget either by passing it in
the Katalis.appSettings or by calling the setLocale method. To specify the locale, use the shortcodes provided above. This
will ensure that the widget is displayed in the desired language.

// Pass via window.Katalis.appSettings
window.Katalis.appSettings = {
  locale: 'pt_BR',
  // .. rest of the settings
}

// Using setLocale method
window.$Katalis.app.setLocale('pt_BR')

How to update your dashboard’s language?

Only administrators can update the dashboard language. Go to Settings → Account Settings. You will be able to see
the Site Language setting available in the options. Select the language of your choice from the corresponding dropdown
menu. Click on the Update Settings button on the top-right corner of your screen.

Changing the site language would change the default language for all agents/administrators in the system. Currently,
Katalis.app does not support language selection at the agent level. Also, note that this language would be used as the
fallback language for the live chat widget.Last updated on Dec 13, 2024