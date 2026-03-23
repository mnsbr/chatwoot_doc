# How to install live-chat on a React Native app?If you have a React Native app, you can add Katalis live chat widget and talk to your visitors in real-time. This can

be done in 3 simple steps using the Katalis plugin.

Step 1. Create a website inbox in Katalis​

Please refer to this guide for detailed instructions on setting a website inbox in Katalis.

Step 2. Add the plugin to your project​

Add one of the following plugins to your project.

yarn add @katalis/react-native-widget

or

npm install --save @katalis/react-native-widget --save

This library depends on react-native-webview and async-storage. Please follow the instructions provided in the docs.

iOS Installation​

If you're using React Native versions > 60.0, it's relatively straightforward.

cd ios && pod install

Step 3. Use it like this​

Replace websiteToken and baseUrl with appropriate values.

import React, { useState } from 'react';
import { StyleSheet, View, SafeAreaView, TouchableOpacity, Text } from 'react-native';
import ChatWootWidget from '@katalis/react-native-widget';

const App = () => {
  const [showWidget, toggleWidget] = useState(false);
  const user = {
    identifier: '[email protected]',
    name: 'John Samuel',
    avatar_url: '',
    email: '[email protected]',
    identifier_hash: '',
  };
  const customAttributes = { accountId: 1, pricingPlan: 'paid', status: 'active' };
  const websiteToken = 'WEBSITE_TOKEN';
  const baseUrl = 'CHATWOOT_INSTALLATION_URL';
  const locale = 'en';

  return (
    <SafeAreaView style={styles.container}>
      <View>
        <TouchableOpacity style={styles.button} onPress={() => toggleWidget(true)}>
          <Text style={styles.buttonText}>Open widget</Text>
        </TouchableOpacity>
      </View>
      {
        showWidget&&
          <ChatWootWidget
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

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },

  button: {
    height: 48,
    marginTop: 32,
    paddingTop: 8,
    paddingBottom: 8,
    backgroundColor: '#1F93FF',
    borderRadius: 8,
    borderWidth: 1,
    borderColor: '#fff',
    justifyContent: 'center',
  },
  buttonText: {
    color: '#fff',
    textAlign: 'center',
    paddingLeft: 10,
    fontWeight: '600',
    fontSize: 16,
    paddingRight: 10,
  },
});

export default App;

And...you're done. Check out the complete example here.Last updated on Apr 10, 2024