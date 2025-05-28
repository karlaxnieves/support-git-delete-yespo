---
title: React Native Action Buttons
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: React Native Action Buttons | Guide
  description: >-
    This guide provides instructions on how to enhance your mobile push
    notifications by adding action buttons for increased user interaction
  robots: index
next:
  description: ''
---
## Configuring Action Buttons

When creating mobile push notifications, you can add several action buttons for greater interactivity. When a receiver touches the screen for an extended period of time (long pressing), it displays the actions assigned to your push notification.

- iOS supports up to 4 buttons in a single notification.
- Android OS supports up to 3 buttons in a single notification.

### Adding Action Buttons

1. In your account, select _Messages → Messages → Mobile Push_.
2. Create a new mobile push notification or edit an existing one.
3. In the `Buttons` section, enter all the parameters as shown below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/734cb97-button.png",
        "",
        "Buttons"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click `+ Add Button` if you want to add more buttons.

**Note** You must enter the values in Action ID and Text for this button to work correctly. You have to use different Action IDs when you add multiple buttons.

| **Parameter** | **Notes**                                                                                                                                                     |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Action ID     | A unique identifier for your button action.                                                                                                                   |
| Text          | The text the button should display.                                                                                                                           |
| iOS icon path | The icon associated with the action. **Available in iOS 15 and later**. Provide name of an image located in your app’s bundle, preferably in an asset catalog |
| Launch URL    | The URL or deeplink to open when notification is clicked                                                                                                      |
| Custom data   | Additional parameters associated with button in JSON format                                                                                                   |

For more information about notification action icon visit <a rel="nofollow" href="https://developer.apple.com/documentation/usernotifications/unnotificationactionicon" target="_blank"> Apple documentation </a> 

### Handle the Action Button Click Event

#### iOS usage

For iOS there is a listener that is activated by pressing the button in the push - `setOnRetenoPushButtonClickedListener`

```ts
import React, { useCallback, useEffect } from "react";

import { Alert } from "react-native";
import { setOnRetenoPushButtonClickedListener } from "reteno-react-native-sdk";

const onRetenoPushButtonClicked = useCallback((event) => {
  Alert.alert(
    "onRetenoPushButtonClicked",
    event ? JSON.stringify(event) : event
  );
}, []);

useEffect(() => {
  const pushButtonClickListener = setOnRetenoPushButtonClickedListener(
    onRetenoPushButtonClicked
  );

  return () => pushButtonClickListener.remove();
}, [onRetenoPushButtonClicked]);
```

#### Android usage

For Android you can use `setOnRetenoPushClickedListener`. When the push button is pressed, the event `setOnRetenoPushClickedListener` will be triggered, and there will be additional data about the pressed button.

```ts
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