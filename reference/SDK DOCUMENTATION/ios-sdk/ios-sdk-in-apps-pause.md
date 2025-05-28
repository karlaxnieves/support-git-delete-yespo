---
title: iOS SDK In-Apps Pause
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: iOS SDK In-Apps Pause | Yespo Guide
  description: Follow our manual to pause the display of In-App messages on iOS devices
  robots: index
next:
  description: ''
---
From Reteno SDK version 2.0.0 onwards, you can pause on startup using:

```swift
Reteno.start(apiKey: "SDK_ACCESS_KEY", isPausedInAppMessages: true)
```

One more method for controlling pause is:

```swift
 Reteno.pauseInAppMessages(isPaused: <Bool>)
```

To enable Pause provide `isPaused: true` to `Reteno.pauseInAppMessages()`, to disable provide `isPaused: false`.

From Reteno 2.0.3 onwards, you can chose pause behavior.

```swift
Reteno.setInAppMessagesPauseBehaviour(pauseBehaviour: <PauseBehaviour>)
```

`PauseBehaviour` provides two possible cases: `.skipInApps`, `.postponeInApps`

* `.skipInApps` - Skipped all In-App messages until pause enabled.
* `.postponeInApps` - Skipped all In-App messages until pause is enabled and show the first one (if it existed) when pause is disabled.
