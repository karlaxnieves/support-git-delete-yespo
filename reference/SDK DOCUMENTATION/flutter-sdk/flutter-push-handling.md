---
title: Flutter Push Handling
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Flutter Push Handling | Guide
  description: >-
    This guide covers retrieving the initial notification payload, listening for
    new notifications, and handling user interaction with the notifications.
  robots: index
next:
  description: ''
---
## Updating Notification Permission Status on Android

When dealing with notifications on Android 13 and later versions, it's important to handle permissions properly at runtime. After obtaining permission from the user, you need to notify the Reteno SDK by calling the `updatePushPermissionStatus()` function from the Reteno.

```dart Dart
Reteno.updatePushPermissionStatus();
```

## Getting Initial Notification

When you instantiate the app by clicking on a push notification, you may need to get its payload.\
To do it, use the `getInitialNotification` method:

```text Dart
import 'package:reteno_plugin/reteno.dart';

final Reteno reteno = Reteno();

reteno.getInitialNotification().then((Map<String, dynamic>? payload) {
      // Process payload...
});
```

## Listening for New Push Notifications in an Open App

When the app is open, you may need to track for new push notifications.\
For that, the plugin provides the `onRetenoNotificationReceived` stream you can listen to:

```text Dart
import 'package:reteno_plugin/reteno.dart';

Reteno.onRetenoNotificationReceived.listen((Map<String, dynamic> payload) {
      // Process payload...
});
```

## Handle Interaction with Notification

When notification is pressed you may need to handle that and receive notification's data.\
For that, the plugin provides the `onRetenoNotificationClicked` stream you can listen to:

```dart Dart
import 'package:reteno_plugin/reteno.dart';

Reteno.onRetenoNotificationClicked.listen((Map<String, dynamic> payload) {
      // Process payload...
}); 
```
