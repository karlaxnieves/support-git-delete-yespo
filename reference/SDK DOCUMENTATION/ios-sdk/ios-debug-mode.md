---
title: iOS Debug Mode
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
## Debug Mode

`DebugMode` enables you to see the event data logged by your app in near real-time. This is very useful for validation purposes during the instrumentation phase of development and can help you discover errors and mistakes in your Analytics implementation and confirm that all events and user properties are logged correctly.

In DebugMode events are logged every 10 seconds and are stored in offline mode up to 1 hour.

To enable `DebugMode` provide `isDebugMode: true` to `Reteno.start()` method:

```swift
Reteno.start(apiKey: "API_KEY", isDebugMode: true)
```

From Reteno SDK 2.0.4 onwards, you can use: 

```swift
let configuration: RetenoConfiguration = .init(isDebugMode: true)
Reteno.start(apiKey: "API_KEY", configuration: configuration)
```

To view events from your app in debug mode specify _X-Reteno-Debug:true_ in the request’s headers. 

Then go to settings -> _Mob Push_ -> and click _Debug_ next to the app name.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f69cd48-Debug.png",
        "",
        "App list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[Go to my app list >](https://my.yespo.io/settings-ui/#/mobile-push/apps-list)

You will see:

- notifications with recommendations for checking settings and verification statuses,
- _Test Mobile Push_ and _Test App Inbox_ buttons,
- valid and invalid events with error descriptions,
- event parameters,
- contact information (full name, email, phone, device ID),
- filter by devices.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a7721a4-ios.gif",
        null,
        "iOS debug"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The system keeps events for 8 hours.

These requests also will be visible in the Event history (as shown below).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ea12c35-Event_history.png",
        "Event history.png",
        1742
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]


**Troubleshooting Steps:**

- **The notification service is not configured:** Configure [APNs](https://docs.yespo.io/docs/connect-your-mobile-app#apn).
- **Push tokens/device data are absent:** Check that you have allowed notifications on the device and configured the token transfer. [Details >](https://docs.yespo.io/reference/using-updateuserattributes-method)
- **The _Delivered_ message statuses are absent:** Check your message delivery data settings. [Details >](https://docs.yespo.io/docs/setting-up-delivery-and-clicks-analytics)
- **The _Clicked_ message statuses are absent:** Click the notification, or check click tracking in the code. [Details >](https://docs.yespo.io/docs/setting-up-delivery-and-clicks-analytics)
- **User profile updates are absent:** Ensure you send user data when you identify them. For example, when they sign in to the app. [Details >](https://docs.yespo.io/reference/using-updateuserattributes-method)

[More on debugging in Yespo account >](https://yespo.io/support/sending-test-messages-from-the-event-debug-view)