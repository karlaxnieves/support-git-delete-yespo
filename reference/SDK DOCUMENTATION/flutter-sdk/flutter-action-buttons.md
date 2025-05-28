---
title: Flutter Action Buttons
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
        "https://files.readme.io/a3f4b08-action_button_setup.png",
        "",
        "Action buttons"
      ],
      "align": "center"
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

For more information about notification action icon visit [Apple documentation](https://developer.apple.com/documentation/usernotifications/unnotificationactionicon).

### Handle the Action Button Click Event

```dart Dart
import 'package:reteno_plugin/reteno.dart';
Reteno.onUserNotificationAction.listen((event) {
  print('onUserNotificationAction: ${event.toString()}');
});
```

where event is `RetenoUserNotificationAction` model.

```dart Dart
RetenoUserNotificationAction({
  this.actionId, // Unique identifier for your button action
  this.customData, // Additional parameters associated with button in key-value pairs
  this.link, // The URL or deeplink to open when notification is clicked
});
```