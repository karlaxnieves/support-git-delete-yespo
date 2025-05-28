---
title: Managing Mobile SDK Access Keys
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
After you [connect your mobile app to Yespo](https://docs.yespo.io/docs/connecting-mobile-apps), you have to create the access key.

This access key authorizes all the requests sent from the mobile app through the SDK ([iOS](https://docs.yespo.io/reference/ios-sdk), [Android](https://docs.yespo.io/reference/android-sdk), [React Native](https://docs.yespo.io/reference/react-native-sdk), [Flutter](https://docs.yespo.io/reference/flutter-sdk), [Unity](https://docs.yespo.io/reference/unity-sdk-setup), [Cordova](https://docs.yespo.io/reference/cordova-sdk-setup), [Ionic](https://docs.yespo.io/reference/ionic-sdk)) to Reteno.

## Creating and Enabling the Access Key

##

To create the access key:

1. Go to *your profile* → *Settings* (1) → *Mob Push* (2).

<Image align="center" width="80% " src="https://files.readme.io/a8d02ad-Settings.png" />

2. Click on the name of your app. 

<Image align="center" width="80% " src="https://files.readme.io/99e9704-edit_app.webp" />

3. Select the *Access Keys* tab and click *Add access key*.

<Image align="center" width="80%" src="https://files.readme.io/73c8efe-Access_Key_1.png" />

4. In the *Create access key* dialog box, enter the key description in the *Description* field and click *Create*.

<Image align="center" width="80%" src="https://files.readme.io/d728f9c-key_description_and_create_eng.png" />

> 📘 Note
>
> Assigning the description for each mobile access key allows you to identify it and understand which integration it is associated with.

5. To enable the access key, click the slide button on the left-hand side.

> 📘 Note
>
> If you do not need to use the access key, disable it by clicking its slide button.

## Using the Key to Access Reteno SDK

To use the access key to authenticate access to your Reteno mobile SDK:

1. Go to *your profile* → *Settings* → *Mob Push* and select your mobile app connected to Reteno.
2. Select the *Access Keys* tab and click the *Copy* icon beside your key.

<Image align="center" width="80%" src="https://files.readme.io/67844bb-Access_Key_3.png" />

3. Send your API key in X-Reteno-Access-Key HTTP header in every request.
