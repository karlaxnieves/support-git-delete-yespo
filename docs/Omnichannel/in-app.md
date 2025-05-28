---
title: In-App
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: In-App | Yespo Guide
  description: >-
    In-App messages enhance user experience and retention by appearing during
    active app sessions, and can be configured in Yespo by connecting your app,
    installing the necessary SDKs, and creating In-App campaigns with specific
    display methods.
  robots: index
next:
  description: ''
---
In-App messages appear directly in the mobile app during an active session. In-App notifications guide users, encourage them to take targeted actions, improve user experience, and ultimately increase retention and lifetime value (LTV).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db359a3e45f64bb436d98c6dc9d5f3f209ec369774a01b6dd6c12aaeb1922b49-eng.webp",
        "In-App",
        "In-App"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


To send In-App notifications via Yespo, please complete the following configuration steps.

## Step 1. Connect Your Mobile App to Yespo

Implement push notifications on Android and iOS devices using Google Firebase private key or certificate/token-based connection to APNs. [See documentation for details >](https://docs.yespo.io/docs/connecting-mobile-apps)

## Step 2. Install SDK

Integrate the required SDK versions into your mobile app:

- [iOS SDK](https://docs.yespo.io/reference/ios-sdk)
- [Android SDK](https://docs.yespo.io/reference/android-sdk-setup)
- [React Native SDK](https://docs.yespo.io/reference/react-native-sdk)
- [Flutter SDK](https://docs.yespo.io/reference/flutter-sdk)
- [Unity SDK](https://docs.yespo.io/reference/unity-sdk-setup)
- [Cordova SDK](https://docs.yespo.io/reference/cordova-sdk-setup)
- [Ionic SD](https://docs.yespo.io/reference/ionic-sdk)

## Step 3. Create the first In-App newsletter

1. [Prepare an In-App message](https://docs.yespo.io/docs/creating-in-app-message).
2. Select a display method:

- [by triggering rules](https://docs.yespo.io/docs/in-app-publishing-and-triggering-rules)
- [after tapping on mobile push](https://docs.yespo.io/docs/linking-app-mobile-push)