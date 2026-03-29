# Cara Menginstal Live Chat di Aplikasi Next.js# Cara Menginstal Live Chat di Aplikasi Next.js
































































Anda seharusnya bisa melihat widget Katalis.app di halaman sekarang.```export default Page)  </Fragment>    <Component {...}>    <Katalis.appWidget />  <Fragment>const Page = () => (import Katalis.appWidget from '../components/Katalis.appWidget'import React, { Fragment } from 'react'```javascriptImport komponen di halaman atau komponen layout Anda.**Langkah 2.** Import```export default Katalis.appWidget}  }    return null;  render () {  }    })(document,"script");      }        })          baseUrl: BASE_URL          websiteToken: '<token-website-anda>',        window.Katalis.appSDK.run({      g.onload=function(){      g.async=!0;      s.parentNode.insertBefore(g,s);      g.src=BASE_URL+"/packs/js/sdk.js";      var g=d.createElement(t),s=d.getElementsByTagName(t)[0];      var BASE_URL="<url-instalasi-anda>";    (function(d,t) {    };      type: 'standard',      locale: 'id',      position: 'right',      hideMessageBubble: false,    window.Katalis.appSettings = {  componentDidMount () {class Katalis.appWidget extends React.Component {import React from 'react';```javascriptSalin kode berikut dan buat file di folder komponen dengan nama Katalis.appWidget.js.**Langkah 1.** Salin dan Buat!Anda bisa melakukan ini dalam dua langkah cepat. Mari ilustrasikan dengan contoh di bawah ini. Contoh ini menunjukkan komponen React yang memuat skrip Katalis.app secara asinkron.Jika Anda memiliki aplikasi Next.js, Anda bisa menambahkan widget live chat Katalis.app dan berbicara dengan pengunjung secara real time. Untuk mengintegrasikan Katalis.app dengan aplikasi Next.js, Anda memerlukan komponen yang memuat skrip Katalis.app.
Jika Anda memiliki aplikasi Next.js, Anda bisa menambahkan widget live chat Katalis.app dan berbicara dengan pengunjung secara real time. Untuk mengintegrasikan Katalis.app dengan aplikasi Next.js, Anda memerlukan komponen yang memuat skrip Katalis.app.

Anda bisa melakukan ini dalam dua langkah cepat. Mari kita ilustrasikan dengan contoh di bawah. Contoh ini menunjukkan komponen React yang memuat skrip Katalis.app secara asinkron.

**Langkah 1.** Salin dan Buat!

Salin kode berikut dan buat file di folder komponen Anda dengan nama Katalis.appWidget.js.

```javascript
import React from 'react';

class Katalis.appWidget extends React.Component {
  componentDidMount () {
    window.Katalis.appSettings = {
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
        window.Katalis.appSDK.run({
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

export default Katalis.appWidget
```

**Langkah 2.** Import

Import komponen di halaman atau komponen layout Anda, seperti di bawah.

```javascript
import React, { Fragment } from 'react'
import Katalis.appWidget from '../components/Katalis.appWidget'

const Page = () => (
  <Fragment>
    <Katalis.appWidget />
    <Component {...}>
  </Fragment>
)

export default Page
```

Anda seharusnya bisa melihat widget Katalis.app di halaman sekarang.
