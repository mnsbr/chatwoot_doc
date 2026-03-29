# Cara Menginstal Live Chat di Aplikasi React Native

Jika Anda memiliki aplikasi React Native, Anda bisa menambahkan widget live chat Katalis.app dan berbicara dengan pengunjung secara real-time. Ini bisa dilakukan dalam 3 langkah sederhana menggunakan plugin Katalis.app.

**Langkah 1.** Buat inbox website di Katalis.app

Silakan lihat panduan ini untuk instruksi detail tentang menyiapkan inbox website di Katalis.app.

**Langkah 2.** Tambahkan plugin ke proyek Anda

```bash
yarn add @Katalis.app/react-native-widget
```
atau
```bash
npm install --save @Katalis.app/react-native-widget --save
```

Library ini bergantung pada react-native-webview dan async-storage. Silakan ikuti instruksi yang disediakan di dokumentasi.

### Instalasi iOS
Jika menggunakan React Native versi > 60.0, cukup mudah.
```bash
cd ios && pod install
```

**Langkah 3.** Gunakan seperti ini

Ganti `websiteToken` dan `baseUrl` dengan nilai yang sesuai.

```javascript
import React, { useState } from 'react';
import { StyleSheet, View, SafeAreaView, TouchableOpacity, Text } from 'react-native';
import Katalis.appWidget from '@Katalis.app/react-native-widget';

const App = () => {
  const [showWidget, toggleWidget] = useState(false);
  const user = {
    identifier: 'john@katalis.app',
    name: 'John Samuel',
    avatar_url: '',
    email: 'john@katalis.app',
    identifier_hash: '',
  };
  const customAttributes = { accountId: 1, pricingPlan: 'paid', status: 'active' };
  const websiteToken = 'WEBSITE_TOKEN';
  const baseUrl = 'URL_INSTALASI_Katalis.app';
  const locale = 'id';

  return (
    <SafeAreaView style={styles.container}>
      <View>
        <TouchableOpacity style={styles.button} onPress={() => toggleWidget(true)}>
          <Text style={styles.buttonText}>Buka widget</Text>
        </TouchableOpacity>
      </View>
      {showWidget &&
        <Katalis.appWidget
          websiteToken={websiteToken}
          locale={locale}
          baseUrl={baseUrl}
          closeModal={() => toggleWidget(false)}
          isModalVisible={showWidget}
          user={user}
          customAttributes={customAttributes}
        />
      }
    </SafeAreaView>
  );
};
```

Dan... selesai. Lihat contoh lengkap di sini.
