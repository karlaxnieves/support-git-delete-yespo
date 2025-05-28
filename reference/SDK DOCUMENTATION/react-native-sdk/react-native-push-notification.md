---
title: React Native Push Notification
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
## Get Initial Notification

When your app is instantiated by clicking on push notification, you may need its payload;  
In order to get it, use `getInitialNotification` function

```typescript
import React, { useEffect } from "react";
import { Alert } from "react-native";
import { getInitialNotification } from "reteno-react-native-sdk";
useEffect(() => {
  getInitialNotification().then((data) => {
    Alert.alert("getInitialNotification", data ? JSON.stringify(data) : data);
  });
}, []);
```

## Listen for New Push Notifications while App is Active

While app is open, you may need to track, if there is new push;  
To do so, set listener using `setOnRetenoPushReceivedListener` function;

```typescript
import React, { useCallback, useEffect } from "react";
import { Alert } from "react-native";
import { setOnRetenoPushReceivedListener } from "reteno-react-native-sdk";
const onRetenoPushReceived = useCallback((event) => {
  Alert.alert("onRetenoPushReceived", event ? JSON.stringify(event) : event);
}, []);
useEffect(() => {
  const pushListener = setOnRetenoPushReceivedListener(onRetenoPushReceived);
  return () => pushListener.remove();
}, [onRetenoPushReceived]);
```

## Listen for Push Notification Clicks

To handle push notification clicks, you can set up a listener using the `setOnRetenoPushClickedListener` function provided by the `reteno-react-native-sdk`.

```typescript
import React, { useCallback, useEffect } from "react";

import { Alert } from "react-native";
import { setOnRetenoPushClickedListener } from "reteno-react-native-sdk";

const onRetenoPushClicked = useCallback((event) => {
  Alert.alert("onRetenoPushClicked", event ? JSON.stringify(event) : event);
}, []);

useEffect(() => {
  const pushClickListener = setOnRetenoPushClickedListener(onRetenoPushClicked);
  return () => pushClickListener.remove();
}, [onRetenoPushClicked]);
```

## Updating Notification Permission Status on Android

When dealing with notifications on Android 13 and later versions, it's important to handle permissions properly at runtime. After obtaining permission from the user, you need to notify the Reteno SDK by calling the `updatePushPermissionStatusAndroid()` function from the Reteno interface.

```typescript
import React, { useEffect } from "react";

import { updatePushPermissionStatusAndroid } from "reteno-react-native-sdk";

useEffect(() => {
  PermissionsAndroid.request(
    PermissionsAndroid.PERMISSIONS.POST_NOTIFICATIONS!
  ).then((result) => {
    if (result === "granted") {
      updatePushPermissionStatusAndroid().then((status) => {
        console.log("Update status:", status);
      });
    }
  });
}, []);
```