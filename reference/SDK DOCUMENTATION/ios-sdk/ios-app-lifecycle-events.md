---
title: iOS App Lifecycle Events
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: App Lifecycle Events | Support
  description: Learn how to track app lifecycle events on iOS
  robots: index
next:
  description: ''
---
Starting from version 2.0.4 `Reteno` can track app lifecycle events such as instalation, updating, opening and backgrouding. This event will be tracked automatically but it can be managed.

```swift
let configuration: RetenoConfiguration = .init(isAutomaticAppLifecycleReportingEnabled: true)
Reteno.start(apiKey: "API_KEY", configuration: configuration)
```

When `isAutomaticAppLifecycleReportingEnabled` is enabled `Reteno` tracks the following events: 

| Event Name                | Properties                                     | Description                                                                                    |
| ------------------------- | ---------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ApplicationInstalled`    | version, build                                 | This event fires when a user opens the application for the first time right after installation |
| `ApplicationUpdated`      | version, build, previousVersion, previousBuild | This event fires when a user opens the application after updating the application              |
| `ApplicationOpened`       | fromBackground                                 | This event fires when a user launches or foregrounds the application after the first open      |
| `ApplicationBackgrounded` | applicationOpenedTime, secondsInForeground     | This event fires when a user backgrounds the application                                       |