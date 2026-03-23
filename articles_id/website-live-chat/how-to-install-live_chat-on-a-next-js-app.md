# Cara Menginstal Live Chat di Aplikasi Next.js# Cara Menginstal Live Chat di Aplikasi Next.js
































































Anda seharusnya bisa melihat widget Katalis di halaman sekarang.```export default Page)  </Fragment>    <Component {...}>    <KatalisWidget />  <Fragment>const Page = () => (import KatalisWidget from '../components/KatalisWidget'import React, { Fragment } from 'react'```javascriptImport komponen di halaman atau komponen layout Anda.**Langkah 2.** Import```export default KatalisWidget}  }    return null;  render () {  }    })(document,"script");      }        })          baseUrl: BASE_URL          websiteToken: '<token-website-anda>',        window.katalisSDK.run({      g.onload=function(){      g.async=!0;      s.parentNode.insertBefore(g,s);      g.src=BASE_URL+"/packs/js/sdk.js";      var g=d.createElement(t),s=d.getElementsByTagName(t)[0];      var BASE_URL="<url-instalasi-anda>";    (function(d,t) {    };      type: 'standard',      locale: 'id',      position: 'right',      hideMessageBubble: false,    window.katalisSettings = {  componentDidMount () {class KatalisWidget extends React.Component {import React from 'react';```javascriptSalin kode berikut dan buat file di folder komponen dengan nama KatalisWidget.js.**Langkah 1.** Salin dan Buat!Anda bisa melakukan ini dalam dua langkah cepat. Mari ilustrasikan dengan contoh di bawah ini. Contoh ini menunjukkan komponen React yang memuat skrip Katalis secara asinkron.Jika Anda memiliki aplikasi Next.js, Anda bisa menambahkan widget live chat Katalis dan berbicara dengan pengunjung secara real time. Untuk mengintegrasikan Katalis dengan aplikasi Next.js, Anda memerlukan komponen yang memuat skrip Katalis.
Jika Anda memiliki aplikasi Next.js, Anda bisa menambahkan widget live chat Katalis dan berbicara dengan pengunjung secara real time. Untuk mengintegrasikan Katalis dengan aplikasi Next.js, Anda memerlukan komponen yang memuat skrip Katalis.

Anda bisa melakukan ini dalam dua langkah cepat. Mari kita ilustrasikan dengan contoh di bawah. Contoh ini menunjukkan komponen React yang memuat skrip Katalis secara asinkron.

**Langkah 1.** Salin dan Buat!

Salin kode berikut dan buat file di folder komponen Anda dengan nama KatalisWidget.js.

```javascript
import React from 'react';

class KatalisWidget extends React.Component {
  componentDidMount () {
    window.katalisSettings = {
      hideMessageBubble: false,
      position: 'right',
      locale: 'id',
      type: 'standard',
    };

    (function(d,t) {
      var BASE_URL="<url-instalasi-anda>";
      var g=d.createElement(t),s=d.getElementsByTagName(t)[0];
      g.src=BASE_URL+"/packs/js/sdk.js";
      s.parentNode.insertBefore(g,s);
      g.async=!0;
      g.onload=function(){
        window.katalisSDK.run({
          websiteToken: '<token-website-anda>',
          baseUrl: BASE_URL
        })
      }
    })(document,"script");
  }

  render () {
    return null;
  }
}

export default KatalisWidget
```

**Langkah 2.** Import

Import komponen di halaman atau komponen layout Anda, seperti di bawah.

```javascript
import React, { Fragment } from 'react'
import KatalisWidget from '../components/KatalisWidget'

const Page = () => (
  <Fragment>
    <KatalisWidget />
    <Component {...}>
  </Fragment>
)

export default Page
```

Anda seharusnya bisa melihat widget Katalis di halaman sekarang.
