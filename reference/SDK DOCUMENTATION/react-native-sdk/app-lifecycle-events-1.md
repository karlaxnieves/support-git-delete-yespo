---
title: React Native App Lifecycle Events
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: App Lifecycle Events | Support
  description: See how to track app lifecycle events
  robots: index
next:
  description: ''
---
Reteno SDK can automatically track application lifecycle and track events that described below.

## Track AppLifecycle Events

When `isAutomaticAppLifecycleReportingEnabled` (iOS) or `appLifecycleEnabled` (Android) is enabled `Reteno` tracks the following events:

| Event Name                | Properties                                     | Description                                                                                    |
| ------------------------- | ---------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ApplicationInstalled`    | version, build                                 | This event fires when a user opens the application for the first time right after installation |
| `ApplicationUpdated`      | version, build, previousVersion, previousBuild | This event fires when a user opens the application after updating the application              |
| `ApplicationOpened`       | fromBackground                                 | This event fires when a user launches or foregrounds the application after the first open      |
| `ApplicationBackgrounded` | applicationOpenedTime, secondsInForeground     | This event fires when a user backgrounds the application                                       |

## Track Push Subscription Events

When `isAutomaticPushSubscriptionReportingEnabled` (iOS) or `pushSubscriptionEnabled` (Android) is enabled `Reteno` tracks the following events:

| Event Name                      | Description                                                          |
| ------------------------------- | -------------------------------------------------------------------- |
| `PushNotificationsSubscribed`   | This event fires when a customer susbribes for push notifications    |
| `PushNotificationsUnsubscribed` | This event fires when a customer unsusbribes from push notifications |

## Track Session Events

When `isAutomaticSessionReportingEnabled` (iOS) or `sessionEventsEnabled` (Android) is enabled `Reteno` tracks the following events:

| Event Name       | Properties                                                                                  | Description                                    |
| ---------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| `SessionStarted` | sessionId, startTime                                                                        | This event fires when a user's session started |
| `SessionEnded`   | sessionID, endTime, durationInSeconds, applicationOpenedCount, applicationBackgroundedCount | This event fires when a user's session ended   |

## Configure Android initialization

To control or disable tracking of some events you must supply instance of LifecycleTrackingOptions.

```kotlin
data class LifecycleTrackingOptions(
    val appLifecycleEnabled: Boolean = true,
    val pushSubscriptionEnabled: Boolean = true,
    val sessionEventsEnabled: Boolean = true
)
```

Also there are 2 useful shortcuts:

* `LifecycleTrackingOptions.ALL` to all categories
* `LifecycleTrackingOptions.NONE` to disable all categories.

### During SDK initialization

```java
new RetenoImpl(
            /* application */ this,
            /* accessKey */ "your_access_key",
            /* config */ new RetenoConfig(
                /* isPausedInAppMessages */  false,
                /* userIdProvider */  createProvider(),
                /* lifecycleTrackingOptions */ new LifecycleTrackingOptions(
                    /* appLifecycleEnabled */ true,
                    /* pushSubscriptionEnabled */ false,
                    /* sessionEventsEnabled */ false
                )
            )
);
```
```kotlin
RetenoImpl(
        application = applicaiton,
        accessKey = "your_access_key",
        config = RetenoConfig(
            lifecycleTrackingOptions = LifecycleTrackingOptions(
                appLifecycleEnabled = true,
                pushSubscriptionEnabled = false,
                sessionEventsEnabled = false
            )
        )
)
```

## Configure iOS initialization

To control or disable tracking of some events you must init configuration.

```swift
let configuration: RetenoConfiguration = .init(
    isAutomaticAppLifecycleReportingEnabled: Bool = true,
    isAutomaticPushSubscriptionReportingEnabled: Bool = true,
    isAutomaticSessionReportingEnabled: Bool = true,
  )
Reteno.start(apiKey: "API_KEY", configuration: configuration)
```

**Note** Ensure that the init method parameters are passed in the correct order as specified. All available parameters for init method:

```swift
public init(
    isAutomaticScreenReportingEnabled: Bool = false,
    isAutomaticAppLifecycleReportingEnabled: Bool = true,
    isAutomaticPushSubscriptionReportingEnabled: Bool = true,
    isAutomaticSessionReportingEnabled: Bool = true,
    isPausedInAppMessages: Bool = false,
    inAppMessagesPauseBehaviour: PauseBehaviour = .postponeInApps,
    isDebugMode: Bool = false
  )
```
