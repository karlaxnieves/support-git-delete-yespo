---
title: Unity Android SDK Setup
excerpt: Getting started with Reteno Plugin for Android
deprecated: false
hidden: false
metadata:
  title: Unity Android SDK Setup
  description: >-
    This document provides instructions on how to install a package via Package
    Manager in Unity, set up the SDK, and request permission for receiving
    notifications on Android.
  robots: index
next:
  description: ''
---
## Setting up SDK

Follow our setup guide to integrate the Reteno SDK with your app.

1. From the Unity Editor, navigate to `Edit` > `Project Settings` > `Player` and click the `Android` settings tab.
2. Expand `Publishing Settings` and enable:

- Custom Main Gradle Template
- Custom Gradle Properties Template

3. Navigate to `Assets` > `External Dependency Manager` > `Android Resolver` > `Force Resolve` and resolve your Android dependencies.

It is done, most of the Android setup was already handled during installation!

If you want to ask a permission without using RetenoSDK function, you can do it. But after receiving a permission result, you have to notify RetenoSDK that status of permission might have changed. To do this, you have to call `UpdatePushPermissionStatus` function from RetenoSDK:

```C#
RetenoSDK.UpdatePushPermissionStatus();
```

<br />

> 📘 Note
> 
> [Android Debug Mode](https://docs.yespo.io/reference/android-debug-mode) enables you to ensure that all events and user properties are logged correctly.