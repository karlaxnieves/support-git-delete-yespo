---
title: Android User Behaviour
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

`Reteno SDK` provides ability to track custom events

```kotlin
Reteno.logEvent(event: Event)
```
```java
Reteno.logEvent(Event event);
```

###### Custom Event model:

```kotlin
data class Custom(
    val typeKey: String,
    val dateOccurred: ZonedDateTime,
    val parameters: List<Parameter>? = null
)
```

- `typeKey`- key qualifier of the event (provided by appDeveloper, confirmed by marketing team).

- `dateOccurred` - time when event occurred

- `parameters` - list of parameters, which describe the event

###### Parameter model containt key/value fields to describe the parameter:

```kotlin
data class Parameter(
    val name: String,
    val value: String?
)
```

###### Example of usage:

```kotlin
val params: List<Parameter> = listOf(Parameter("key1", "value1"), Parameter("key2", null))
reteno.logEvent(Event.Custom("eventTypeKey", ZonedDateTime.now(), params))
```
```java
List<Parameter> params = new ArrayList<>();
params.add(new Parameter("key1", "value1"));
params.add(new Parameter("key2", null));

Reteno.logEvent(new Event.Custom("eventTypeKey", ZonedDateTime.now(), params));
```

## Track Screen View Events

`Reteno` tracks `screen appeared` events and attaches information about the current screen to events. 

#### Automatically Track Screen Events

Under the hood Reteno observes FragmentTransactions and tracks Fragment class name as screen name. If your application doesn't use Fragments you should use manual screen tracking.

Automatic screen tracking can be enabled/disabled using the following method:

```kotlin
Reteno.autoScreenTracking(config: ScreenTrackingConfig)
```
```java
Reteno.autoScreenTracking(ScreenTrackingConfig config);
```

Where `ScreenTrackingConfig` is the configuration class for automatic tracking:

```julia
data class ScreenTrackingConfig @JvmOverloads constructor(
    val enable: Boolean,
    val excludeScreens: List<String> = listOf(),
    val trigger: ScreenTrackingTrigger = ScreenTrackingTrigger.ON_START
)
```

###### Arguments:

- `enable` → true/false. Enable/Disable automatic screen tracking

- `excludeScreens` → you may provide a blackList of Fragment names which should not be tracked. Default argument is emptyList

- `trigger` → Fragment Lifecycle callback to trigger screenView event tracking. You may either choose ON_RESUME or ON_START. By default it is ON_START

If you just want to enable/disable automatic screen tracking with the default params you may use overloaded constructor of the data class

```kotlin
Reteno.autoScreenTracking(ScreenTrackingConfig(false))
```
```java
Reteno.autoScreenTracking(new ScreenTrackingConfig(false));
```

#### Manually Track Screen Events

You can manually track screen view events whether automatic tracking is enabled or disabled. You can track these events according to you needs and based on your screen lifecycle:

```kotlin
Reteno.logScreenView(screenName: String)
```
```java
Reteno.logScreenView(String screenName);
```

> 📘 Note
> 
> Set up [event-based segmentation](https://yespo.io/support/how-to-use-event-segmentation) to ensure custom events and their parameters are recorded in contact cards, enabling the creation of dynamic segments.

## Track Mob Push Subscribers

Your end-user may prohibit receiving pushes by disabling `Reteno` notification channel or disabling notifications for your application in Android OS settings menu. In this case SDK will notify its servers to prevent sending push notifications to this specific device.

###### SDK checks notifications enabled status in these cases:

- On App resume
- On push received event
- On settings changed in Android OS Settings menu (starting from Android 9.0, using system broadcast)

Once status `false` sent to the server, the backend won't send any push notifications to this device until the end-user re-enables channel/notifications. Once the end-user re-enables channel/notifications the server will be notified and will send push notifications again.

## Force Push Locally Cached Data

`Reteno` caches all events (events, device data, user information, user behavior, screen tracking, push statuses, etc) locally into database to save battery minimize API calls. Each n seconds (default = 30sec) SDK sends cached data to `Reteno` server in batches. The scheme is as follows:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1efc636-Frame_4.png",
        "Frame_4.png",
        1600
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]


If you need some of your events to be sent to the `Reteno` server instantly just call the following method:

```kotlin
Reteno.forcePushData()
```
```java
Reteno.forcePushData();
```

It will flush all the currently accumulated data in cache (events, device data, user information, push statuses) and uploads it to `Reteno` server.