---
title: Android Push Handling
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
```kotlin
    Reteno.initWithConfig(
        RetenoConfig.Builder()
            .accessKey(...)
            .defaultNotificationChannelConfig { builder ->
                builder
                    .setName("Custom name")
                    .setDescription("Custom description")
                    .setImportance(NotificationManagerCompat.IMPORTANCE_HIGH)
                    .setLightColor(Color.RED)
                    .setLightsEnabled(true)
                    .setShowBadge(true)
                    .setVibrationEnabled(true)
                    .setVibrationPattern(longArrayOf())
                    .setSound(...)
            }
    )
    .build()
```
```java
    Reteno.initWithConfig(
        new RetenoConfig.Builder()
        .accessKey(...)
        .defaultNotificationChannelConfig((builder) -> {
            builder
                .setName("Custom name")
                .setDescription("Custom description")
                .setImportance(NotificationManagerCompat.IMPORTANCE_HIGH)
                .setLightColor(Color.RED)
                .setLightsEnabled(true)
                .setShowBadge(true)
                .setVibrationEnabled(true)
                .setVibrationPattern(longArrayOf())
                .setSound(...);
            return Unit.INSTANCE;
        })
        .build()
```

```xml
<!-- Add this Receiver to listen to PushReceived events -->
<receiver
    android:name="com.example.CustomReceiverPushReceived"
    android:enabled="true"
    android:exported="true"/>
<meta-data
    android:name="com.reteno.Receiver.PushReceived"
    android:value="com.example.CustomReceiverPushReceived" />

<!-- Add this Receiver to listen to NotificationClicked events -->
<receiver
    android:name="com.example.CustomReceiverNotificationClicked"
    android:enabled="true"
    android:exported="true"/>
<meta-data
    android:name="com.reteno.Receiver.NotificationClicked"
    android:value="com.example.CustomReceiverNotificationClicked" />
```

It is important to add a `<meta-data>` tag containing the `com.reteno.Receiver.PushReceived` and `com.reteno.Receiver.NotificationClicked` names of your receivers so that the SDK will be able to trigger them.

```xml
<receiver
    android:name="com.reteno.sample.CustomPushReceiver"
    android:enabled="true"
    android:exported="false" >
    <intent-filter>
        <action android:name="com.reteno.custom-push" />
    </intent-filter>
</receiver>
```
```json
{
  "to": "FCM_token",
  "notification":{
      "title":"Title_here",
      "body":"Body_here"
    }
}
```
```json
{
  "to": "FCM_token",
  "data":{
      "Name" : "John",
      "Room" : 4,
      "Building" : 3
    }
}
```
```json
{
  "to": "FCM_token",
  "data":{
      "Name" : "John",
      "es_interaction_id" : 123
    }
}
```