---
title: Unity Troubleshooting & FAQ
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Unity Troubleshooting & FAQ | Yespo Guide
  description: >-
    This document provides solutions for common issues with the Reteno Unity
    Plugin, such as missing Firebase configuration files, push permission
    denial, and SDK initialization problems, and includes guidance on updating
    the SDK and compatibility with newer Unity versions.
  robots: index
next:
  description: ''
---
This section provides solutions to common issues encountered when integrating the Reteno Unity Plugin.

## Common Issues

### 1. Firebase Configuration Not Found

**Issue**: `GoogleService-Info.plist` or `google-services.json` not found.\
**Solution**:

* Ensure the file is located in the root directory of your Unity project.
* Verify the filenames and placement are correct.

### 2. Push Permission Denied

**Issue**: User denied push notification permissions.\
**Solution**:

* Check the device’s permission settings.
* Confirm that you are correctly invoking `RequestPushPermission` and handling the callbacks.

### 3. SDK Not Initializing

**Issue**: Reteno SDK does not initialize on app launch.\
**Solution**:

* Verify that `RetenoSDK.Initialize("your_access_key")` is called at the beginning of your app’s lifecycle.
* Ensure that the provided Access Key is valid.

## Additional Questions

### How to Update the Reteno SDK?

1. Open Unity and navigate to `Window > Package Manager`.
2. Locate `Reteno Unity SDK` in the list of installed packages.
3. Click the **Update** button next to the package.

### Does the Plugin Support Newer Versions of Unity?

Yes, the plugin supports Unity 2021.3 or newer. Ensure your project uses a compatible version.

### Where Can I Find Additional Support?

Visit the <a rel="nofollow" href="https://github.com/reteno-com/reteno-unity/tree/main/com.reteno.example" target="_blank">GitHub Repository</a> or refer to the <a rel="nofollow" href="https://github.com/reteno-com/reteno-mobile-documentation/blob/main/Unity/Introduction/Introduction.md" target="_blank">Introduction</a> for further information and assistance.
