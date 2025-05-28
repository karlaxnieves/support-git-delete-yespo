---
title: iOS User Behaviour
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
## Track Custom Events

`Reteno SDK` provides ability to log custom events.

```swift
// Parameters:

public struct Parameter {
    let name: String
    let value: String?
}

date: Date - time when event occurred

forcePush: Bool - indicates if event should be send immediately or in the next scheduled batch

// Usage

Reteno.logEvent(eventTypeKey: "EVENT_TYPE_KEY", date: Date, parameters: [Reteno.Event.Parameter], forcePush: Bool = false)
```

> 📘 Note
> 
> Set up [event-based segmentation](https://yespo.io/support/how-to-use-event-segmentation) to ensure custom events and their parameters are recorded in contact cards, enabling the creation of dynamic segments.

## Track Screen View Events

`Reteno` tracks screen appearance and attaches information about the current screen to events. You can also manually log screenviews. Manually tracking screens is useful if your app does not use a separate UIViewController for each screen you may wish to track.

#### Automatically Track Screen Events

`Reteno` automatically tracks some information about screens in your application, such as the class name of the UIViewController that is currently in focus. When a screen transition occurs, Reteno logs a screen view event that identifies the new screen.

Automatic screen tracking can be turned off by providing `isAutomaticScreenReportingEnabled` flag as false during SDK initialization.

> 📘 Note
> 
> `Reteno` depends on method swizzling to automatically log screen views. SwiftUI apps must manually set class for views that should be logged, or log screen views manually (see below).

#### Manually Track Screen Events

You can manually log screen view events whether or not automatic tracking is enabled. You can log these events in the `onAppear` or `viewDidAppear` methods.

```swift
Reteno.logEvent(ScreenViewEvent, parameters: [ScreenClass: screenClass])
```

## Track Mob Push Subscribers

`Reteno SDK` uses the `pushSubscribed` parameter for tracking the status of the user’s subscription to push notifications. This covers the following cases:

- When a customer does not subscribe to receive push notifications (`pushSubscribed` is false), no token is created for that customer.
- When a customer subscribes to receive push notifications (`pushSubscribed` is true), a token is created for that customer.
- When a customer unsubscribes from receiving push notifications (`pushSubscribed` is false), the existing customer token is deleted.

Starting from version 2.0.4 `Reteno` can track push notification subscription events. This event will be tracked automatically but it can be managed.

```swift
let configuration: RetenoConfiguration = .init(isAutomaticPushSubsriptionReportingEnabled: true)
Reteno.start(apiKey: "API_KEY", configuration: configuration)
```

When `isAutomaticPushSubsriptionReportingEnabled` is enabled `Reteno` tracks the following events: 

| Event Name                      | Description                                                           |
| ------------------------------- | --------------------------------------------------------------------- |
| `PushNotificationsSubscribed`   | This event fires when a customer susbribes for push notifications     |
| `PushNotificationsUnsubscribed` | This event fires when a customer unsubscribes from push notifications |

## Track Session Events

Starting from version 2.0.4 `Reteno` can track start session and end session events. This event will be tracked automatically but it can be managed.

```swift
let configuration: RetenoConfiguration = .init(isAutomaticSessionReportingEnabled: true)
Reteno.start(apiKey: "API_KEY", configuration: configuration)
```

When `isAutomaticSessionReportingEnabled` is enabled `Reteno` tracks the following events: 

| Event Name       | Properties                                                                                  | Description                                    |
| ---------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| `SessionStarted` | sessionId, startTime                                                                        | This event fires when a user's session started |
| `SessionEnded`   | sessionID, endTime, durationInSeconds, applicationOpenedCount, applicationBackgroundedCount | This event fires when a user's session ended   |