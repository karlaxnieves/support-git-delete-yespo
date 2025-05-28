---
title: React Native User Behaviour
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

Reteno SDK provides ability to track custom events.

```typescript
import { logEvent } from "reteno-react-native-sdk";

const eventName = "EVENT_NAME";
const date = new Date().toISOString();
const parameters = [
  {
    name: "Additional parameter",
    value: "Additional value",
  },
];
const forcePush = false;

logEvent(eventName, date, parameters, forcePush);
```

The `parameters` list item structure:

```typescript
type CustomEventParameter = {
  name: string;
  value?: string;
};
```

> 📘 Note
>
> Set up [event-based segmentation](https://docs.yespo.io/docs/segmentation-by-events) to ensure custom events and their parameters are recorded in contact cards, enabling the creation of dynamic segments.

> 📘 Note
>
> `date`
>
> Date should be in <a rel="nofollow" href="https://en.wikipedia.org/wiki/ISO_8601"> ISO8601 </a> format
>
> `forcePush` is `iOS`-only feature; Please read more about it <a rel="nofollow" href="https://github.com/reteno-com/reteno-mobile-ios-sdk/blob/b8a9c60da9a41dc7cb22260b6ef8e5a842752b5e/Reteno/Sources/Core/Reteno.swift#L47"> here </a>

## Force Push Data

Reteno SDK caches all events (events, device data, user information, user behavior, screen tracking, push statuses, etc) locally into database. Call `forcePushData` function to send all accumulated events:

```typescript
function forcePushData(): Promise<void>;
```

## Log Screen View Events

You can send screen view events using `logScreenView` function:

```typescript
function logScreenView(screenName: string): Promise<void>;
```

There are a few ways to implement the navigation within React Native apps, therefore there is no "one fits all" , this function provides a basic mechanism for sending screen view events, and you can use it whatever way you want.

```typescript
const someRouteName = getSomeRouteName();
await logScreenView(someRouteName);
```

You can check an example provided by <a rel="nofollow" href="https://reactnavigation.org/"> React Navigation </a> library, which can give you an idea of the implementation. See <a rel="nofollow" href="https://reactnavigation.org/docs/screen-tracking/"> Screen tracking for analytics </a> documentation.

## Mobile Push Subscribes

### iOS usage

`Reteno SDK` uses the `pushSubscribed` parameter for tracking the status of the user’s subscription to push notifications. This covers the following cases:

* When a customer does not subscribe to receive push notifications (`pushSubscribed` is false), no token is created for that customer.
* When a customer subscribes to receive push notifications (`pushSubscribed` is true), a token is created for a new customer.
* When a customer unsubscribes from receiving push notifications (`pushSubscribed` is false), the existing customer token is deleted.\
  `Reteno` can track push notification subscription events. This event will be tracked automatically but it can be managed.

```swift
let configuration: RetenoConfiguration = .init(isAutomaticPushSubsriptionReportingEnabled: true)
Reteno.start(apiKey: "API_KEY", configuration: configuration)
```

When `isAutomaticPushSubsriptionReportingEnabled` is enabled `Reteno` tracks the following events:

| Event Name                      | Description                                                           |
| ------------------------------- | --------------------------------------------------------------------- |
| `PushNotificationsSubscribed`   | This event fires when a customer subscribes for push notifications    |
| `PushNotificationsUnsubscribed` | This event fires when a customer unsubscribes from push notifications |

### Android usage

Your end-user may prohibit receiving pushes by disabling `Reteno` notification channel or disabling notifications for your application in Android OS settings menu. In this case SDK will notify its servers to prevent sending push notifications to this specific device.\
SDK checks notifications enabled status in these cases:

* On App resume
* On push received event
* On settings changed in Android OS Settings menu (starting from Android 9.0, using system broadcast)\
  Once status `false` sent to the server, the backend won't send any push notifications to this device until the end-user re-enables channel/notifications. Once the end-user re-enables channel/notifications the server will be notified and will send push notifications again.

## Track Session Events

### iOS usage

`Reteno` can track start session and end session events. This event will be tracked automatically but it can be managed.

```swift
let configuration: RetenoConfiguration = .init(isAutomaticSessionReportingEnabled: true)
Reteno.start(apiKey: "API_KEY", configuration: configuration)
```

When `isAutomaticSessionReportingEnabled` is enabled `Reteno` tracks the following events:

| Event Name       | Properties                                                                                  | Description                                    |
| ---------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| `SessionStarted` | sessionId, startTime                                                                        | This event fires when a user's session started |
| `SessionEnded`   | sessionID, endTime, durationInSeconds, applicationOpenedCount, applicationBackgroundedCount | This event fires when a user's session ended   |
