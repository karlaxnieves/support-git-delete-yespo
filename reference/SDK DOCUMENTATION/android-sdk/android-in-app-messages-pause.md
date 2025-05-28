---
title: Android In-App Messages Pause
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Android In-App Messages Pause | Yespo Guide
  description: Follow our manual to pause the display of In-App messages
  robots: index
next:
  description: ''
---
Since Reteno SDK 2.0.1, you can show users In-App messages when they open an app.

You can also pause showing In-App messages to prevent interrupting some important flows like registration or payment.

All In-App messages that had to be shown during pause will be skipped and shown next time when display rules match.

If you want to pause In-App messages on application startup, you can do this by setting `isPausedInAppMessages` to false in `RetenoConfig` during Reteno SDK initialization in the application's `onCreate`:

```kotlin
override fun onCreate() {
    super.onCreate()
    retenoInstance = RetenoImpl(this, "your_access_key_here", RetenoConfig(isPausedInAppMessages = false))
}
```
```java
override fun onCreate() {
    super.onCreate()
    retenoInstance = new RetenoImpl(this, "your_access_key_here", new RetenoConfig(false))
}
```

After initialization, you can pause or unpause In-App messages anytime by calling given the function:

```kotlin
 reteno.pauseInAppMessages(isPaused: Boolean)
```
```java
 reteno.pauseInAppMessages(boolean isPaused)
```

## In-App Pause Strategy

From Reteno 2.0.3 onwards, you can set pause behaviour.

```kotlin
reteno.setInAppMessagesPauseBehaviour(behaviour: InAppPauseBehaviour)
```
```java
 reteno.setInAppMessagesPauseBehaviour(InAppPauseBehaviour behaviour);
```

"InAppPauseBehaviour" provides two possible strategies:

* `SKIP_IN_APPS` - Skip all In-App messages until pause will be enabled.
* `POSTPONE_IN_APPS` - Skip all In-App messages until pause will be enabled and show the first In-App (if it exists) when pause will be disabled.
