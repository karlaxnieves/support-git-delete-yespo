---
title: React Native In-App Messages
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
## Pause In-App Messages

You can manage the display of In-App messages in your React Native application by pausing them when needed. Pausing In-App messages can be useful to prevent interruptions during critical user flows such as registration or payment processes.

All In-App messages that are supposed to be displayed during the pause period will be skipped and shown later when the display rules match.

You can pause or unpause In-App messages at any time during the application's lifecycle.

```ts
import { pauseInAppMessages } from "reteno-react-native-sdk";

/*
  isPaused: (boolean) Flag indicating whether to pause (true) or unpause (false) In-App messages.
*/

const handleInAppMessagesStatus = (isPaused: boolean) => {
  pauseInAppMessages(isPaused)
    .then(() => {
      Alert.alert("Success", "Pause state changed");
    })
    .catch((error) => {
      Alert.alert("Error", error);
    });
};
```

## In-App Message Lifecycle Events

Additionally, you can subscribe to various In-App lifecycle events to receive notifications when specific actions occur, such as before an in-app message is displayed, when it is displayed, before it is closed, after it is closed, or if an error occurs during its display.

Event Handlers:

- **beforeInAppDisplayHandler**
- **onInAppDisplayHandler**
- **beforeInAppCloseHandler**
- **afterInAppCloseHandler**
- **onInAppErrorHandler**

To subscribe on lifecycle events you can use `setInAppLifecycleCallback`. And only on Android - to unsubscribe you can use `removeInAppLifecycleCallback`.

```ts
import { useEffect } from "react";
import { Alert } from "react-native";
import {
  setInAppLifecycleCallback,
  beforeInAppDisplayHandler,
  onInAppDisplayHandler,
  beforeInAppCloseHandler,
  afterInAppCloseHandler,
  onInAppErrorHandler,
  removeInAppLifecycleCallback,
} from "reteno-react-native-sdk";

useEffect(() => {
  // Set the in-app lifecycle callback
  setInAppLifecycleCallback();

  const beforeInAppDisplayListener = beforeInAppDisplayHandler((data) =>
    Alert.alert(
      "Before In-App Display",
      data ? JSON.stringify(data) : "No data received"
    )
  );
  const onInAppDisplayListener = onInAppDisplayHandler((data) =>
    Alert.alert(
      "On In-App Display",
      data ? JSON.stringify(data) : "No data received"
    )
  );
  const beforeInAppCloseListener = beforeInAppCloseHandler((data) =>
    Alert.alert(
      "Before In-App Close",
      data ? JSON.stringify(data) : "No data received"
    )
  );
  const afterInAppCloseListener = afterInAppCloseHandler((data) =>
    Alert.alert(
      "After In-App Close",
      data ? JSON.stringify(data) : "No data received"
    )
  );
  const onInAppErrorListener = onInAppErrorHandler((data) =>
    Alert.alert(
      "On In-App Error",
      data ? JSON.stringify(data) : "No data received"
    )
  );

  // Remove listeners when component unmounts
  return () => {
    beforeInAppDisplayListener.remove();
    onInAppDisplayListener.remove();
    beforeInAppCloseListener.remove();
    afterInAppCloseListener.remove();
    onInAppErrorListener.remove();

    // Remove the in-app lifecycle callback if it exists (only for Android)
    removeInAppLifecycleCallback();
  };
}, []);
```

## Handling In-App Messages Custom Data

This method allows receiving custom data sent with In-App messages in a React Native app using the Reteno SDK.

**Note:** If you want to receive custom data from In-App messages you should be subscribed on In-App lifecycle events (see methods above).

```ts
import { useEffect } from "react";
import { Alert } from "react-native";
import { addInAppMessageCustomDataHandler } from "reteno-react-native-sdk";

useEffect(() => {
  const addInAppMessageCustomDataListener = addInAppMessageCustomDataHandler(
    (data) =>
      Alert.alert(
        "Custom Data Received",
        data ? JSON.stringify(data) : "No custom data received"
      )
  );

  return () => {
    addInAppMessageCustomDataListener.remove();
  };
}, []);
```