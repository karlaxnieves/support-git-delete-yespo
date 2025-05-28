---
title: Flutter SDK Release Notes
fullscreen: false
hidden: false
metadata:
  title: ''
  description: ''
---
We are constantly working to improve our SDK. Here you’ll find the change log for the Flutter SDK and related details.

* [Flutter 1.7.5 Release](#1-7-5)
* [Flutter 1.7.3 Release](#1-7-3)
* [Flutter 1.7.1 Release](#1-7-1)
* [Flutter 1.7.0 Release](#1-7-0)
* [Flutter 1.5.3 Release](#1-5-3)
* [Flutter 1.5.2 Release](#1-5-2)
* [Flutter 1.5.1 Release](#1-5-1)
* [Flutter 1.4.2 Release](#1-4-2)
* [Flutter 1.4.1 Release](#1-4-1)
* [Flutter 1.4.0 Release](#1-4-0)
* [Flutter 1.3.2 Release](#1-3-2)
* [Flutter 1.3.1 Release](#1-3-1)
* [Flutter 1.3.0 Release](#1-3-0)

***

<h2 id="1-7-5">
Flutter 1.7.5 Release
</h2>

:rocket:**Added**

* Ecommerce Activity Tracking `Reteno().logEcommerceEvent()`

:high_brightness: **Improved**

* Bump Android SDK to 2.6.2
* Bump iOS SDK to 2.5.4

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v.1.7.5" target="_blank"> Read more </a>

***

<h2 id="1-7-3">
Flutter 1.7.3 Release
</h2>

:high_brightness: **Improved**

* Bump Android SDK to 2.5.1
* Bump iOS SDK to 2.5.0
* AppInbox add `customData` property. Fix `createdDate` on iOS

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v.1.7.3" target="_blank"> Read more </a>

***

<h2 id="1-7-1">
Flutter 1.7.1 Release
</h2>

 :rocket:**Added**

* `Reteno.onUserNotificationAction` for listening on mobile push notifications actions

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v.1.7.1" target="_blank"> Read more </a>

***

<h2 id="1-7-0">
Flutter 1.7.0 Release
</h2>

:high_brightness: **Improved**

* Bump Android SDK to 2.0.12
* Bump iOS SDK to 2.0.11
* Update `initWith` method signature for Reteno initialization (Android only)
  * add device ID provider parameter

```
 await Reteno.initWith(
 	accessKey: 'access_key',
 	customDeviceId: () async {
 		return await Amplitude.getInstance().getDeviceId();
 	},
 );
```

* Add `Reteno.appInbox` to get App Inbox messages

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v.1.7.0" target="_blank"> Read more </a>

***

<h2 id="1-5-3">
Flutter 1.5.3 Release
</h2>

:high_brightness: **Improved**

* Support AGP 8
* Bump Android SDK to 2.0.10
* Bump iOS SDK to 2.0.9

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v1.5.3" target="_blank"> Read more </a>

***

<h2 id="1-5-2">
Flutter 1.5.2 Release
</h2>

:high_brightness: **Improved**

* Bumped Android SDK to 2.0.7
* Bumped iOS SDK to 2.0.6

:rocket: **Added**

* Added `Reteno.getrecommendations` to get recommendations
* Added `Reteno.logRecommendationsEvent` to log recommendation events

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v.1.5.2" target="_blank"> Read more </a>

***

<h2 id="1-5-1">
Flutter 1.5.1 Release
</h2>

:high_brightness: **Improved**

* Bumped Android SDK to 2.0.2
* Bumped iOS SDK to 2.0.2

:rocket: **Added**

* Added `Reteno.onInAppMessageStatusChanged` to get in-app message status changed events
* Added `Reteno.pauseInAppMessages` to pause or resume in-app messages

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v1.5.1" target="_blank"> Read more </a>

***

<h2 id="1-4-2">
Flutter 1.4.2 Release
</h2>

:white_check_mark: **Fixed**

Fixed lateinit property methodChannel has not been initialized on Android

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v1.4.2" target="_blank"> Read more </a>

***

<h2 id="1-4-1">
Flutter 1.4.1 Release
</h2>

:rocket: **Added**

* Added support for new Android SDK version with new `updatePushPermissionStatus` function

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v1.4.1" target="_blank"> Read more </a>

***

<h2 id="1-4-0">
Flutter 1.4.0 Release
</h2>

:high_brightness: **Improved**

* Bump Android SDK to 1.7.0
* Bump iOS SDK to 1.7.1

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v1.4.0" target="_blank"> Read more </a>

***

<h2 id="1-3-2">
Flutter 1.3.2 Release
</h2>

:white_check_mark: **Fixed**

* Fixed method channels initialization not properly working in pair with Firebase messaging plugin

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v1.3.2" target="_blank"> Read more </a>

***

<h2 id="1-3-1">
Flutter 1.3.1 Release
</h2>

:high_brightness: **Improved**

* Updated handling of config changes in Android plugin

:white_check_mark: **Fixed**

* Fixed plugin not working when adding FirebaseMessaging.onBackgroundMessage handler due to spawning background isolate

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v1.3.1" target="_blank"> Read more </a>

***

<h2 id="1-3-0">
Flutter 1.3.0 Release
</h2>

:rocket: **Added**

* Added Reteno.onRetenoNotificationClicked to get push data on clicked events

<a rel="nofollow" href="https://github.com/reteno-com/reteno-flutter/releases/tag/v1.3.0" target="_blank"> Read more </a>

***
