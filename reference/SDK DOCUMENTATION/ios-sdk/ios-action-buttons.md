---
title: iOS Action Buttons
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
## Configuring Action Buttons

When creating mobile push notifications, you can add several action buttons for greater interactivity. When a receiver touches the screen for an extended period of time (long pressing), it displays the actions assigned to your push notification. iOS supports up to 4 buttons in a single notification.

### Adding Action Buttons

1. In your account, select Messages → Messages → Mobile Push.
2. Create a new mobile push notification or edit an existing one.
3. In the `Buttons` section, enter all the parameters as shown below. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e057218-action_button_setup.png",
        "action_button_setup.png",
        2386,
        954,
        "#000000"
      ],
      "sizing": "80"
    }
  ]
}
[/block]
4. Click `+ Add Button` if you want to add more buttons.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You must enter the values in Action ID and Text for this button to work correctly. You have to use different Action IDs when you add multiple buttons."
}
[/block]
| **Parameter** | **Notes** |
| --------- | ----- |
| Action ID | A unique identifier for the button action. |
| Text | The text that a button displays. |
| iOS icon path | The icon associated with the action. **Available in iOS 15 and later**. Enter the name of an image located in your app’s bundle, preferably in an asset catalog. |
| Launch URL | An URL or a deeplink that opens when the notification is selected. |
| Custom data | Additional parameters associated with the button in JSON format. |

To learn more about notification action icons, see [Apple documentation](https://developer.apple.com/documentation/usernotifications/unnotificationactionicon).

### Handling the Action Button Click Events

When an action button is selected, the Reteno SDK fires a notification click handler `Reteno.userNotificationService.notificationActionHandler`. This click handler contains the `RetenoUserNotificationAction` actionId, customData and the link that you set when creating the Action Buttons.
[block:code]
{
  "codes": [
    {
      "code": "Reteno.userNotificationService.notificationActionHandler = { userInfo, action in\n    let actionId = action.actionId\n    let customData = action.customData\n    let actionLink = action.link\n}",
      "language": "swift"
    }
  ]
}
[/block]