---
title: Android Action Buttons
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

When creating mobile push notifications, you can add several action buttons for greater interactivity. When a receiver touches the screen for an extended period of time (long pressing), it displays the actions assigned to your push notification. Android OS supports up to 3 buttons in a single notification. 

### Adding Action Buttons

1. In your account, select Messages → Messages → Mobile Push.
2. Create a new mobile push notification or edit an existing one.
3. In the `Buttons` section, enter all the parameters as shown below.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a2fd99f-action_button.png",
        "action_button.png",
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
  "body": "You must enter the values in Action ID and Text for this button to work correctly. You have to use different Action IDs when you add multiple buttons.",
  "title": "Note"
}
[/block]
| **Parameter** | **Notes**                                                   |
| ------------- | ----------------------------------------------------------- |
| Action ID     | A unique identifier for the button action.             |
| Text          | The text that a button displays.                      |
| Launch URL    | The icon associated with the action. **Available in iOS 15 and later**. Enter the name of an image located in your app’s bundle, preferably in an asset catalog.    |
| Custom data   | Additional parameters associated with the button in JSON format. |

### Handle the Action Button Click Event

When a user clicks any button in push notification, RetenoSDK fires a broadcast with accompanied data bundled. Follow the instructions to implement the broadcast receiver.

See [Documentation](https://docs.reteno.com/reference/android-push-handling#notification-events-push-received-notification-clicked)