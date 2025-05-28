---
title: Using updateUserAttributes Method
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
An external ID is a unique user identifier generated in your system to avoid duplicating user profiles.

Send your user ID to Yespo when creating, updating, or matching user data. This way, Yespo can find the user's profile and update their data.

Using `updateUserAttributes` method is a must in such cases:

1. The user logged in and then updated the application with the SDK for the first time.
2. The user signed up.
3. The user logged in.
4. The user profile has been updated.

Sending the user ID will ensure the correct matching and up-to-dateness of the user data.

Each SDK type has a particular way of sending user ID; see instructions below:

- [iOS >](https://docs.yespo.io/reference/ios-user-information#external-user-id)
- [Android >](https://docs.yespo.io/reference/android-user-information#external-user-id)
- [React Native >](https://docs.yespo.io/reference/react-native-user-information#external-user-id)
- [Flutter >](https://docs.yespo.io/reference/flutter-user-information#adding-external-user-id)
- [Unity >](https://docs.yespo.io/reference/unity-user-information#adding-external-user-id)
- [Cordova >](https://docs.yespo.io/reference/cordova-sdk-setup)
- [Ionic >](https://docs.yespo.io/reference/ionic-sdk)