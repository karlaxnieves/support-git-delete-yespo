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
## Customize Default Notification Channel

To customize default notification channel for new users use defaultNotificationChannelConfig builder parameter during sdk initialization

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
        }
        .build()
```

To customize channel parameters for existing users, use:

```kotlin
RetenoNotifications.updateDefaultNotificationChannel(
    name = "New name",
    description = "New description"
)
```
```java
RetenoNotifications.updateDefaultNotificationChannel(
        "New name",
        "New description"
);
```

## Deeplinks

[How to Create Deep Links and Universal Links | Support](https://yespo.io/support/how-create-deep-links-and-universal-links)

When the SDK receives a deeplink push notification, it creates an intent to open the application without triggering the web browser. This is not a default behavior, but it improves the user experience and allows skipping the app selection step after the URL resolution. If the application cannot handle the URL, the web browser opens the provided link.

For handling deeplinks on Android12+, keep in mind the recent changes as explained at [developer.android.com](https://developer.android.com/about/versions/12/behavior-changes-all#web-intent-resolution)

Also, make sure to set up the proper intent filter for your activity [developer.android.com](https://developer.android.com/training/app-links/deep-linking)

## Custom Data

You can pass your custom data in push notifications using the **"Custom data"** box at [Yespo admin panel](https://yespo.io/support/how-to-create-mobile-push-notifications). You can handle this custom data payload in the Launcher activity or the activity that handles deeplinks in the `onCreate` or `onNewIntent` methods. Custom data is delivered via intent extras.

```kotlin
override fun onNewIntent(intent: Intent?) {
       super.onNewIntent(intent)
       val customDataValue = intent?.extras?.getString("customDataKey")
   }
```
```java
@Override
   protected void onNewIntent(Intent intent) {
       super.onNewIntent(intent);
       String customDataValue = intent.getExtras().getString("customDataKey");
   }
```

> 📘 Note
> 
> If you send a push notification containing a link that your application cannot handle, the web browser will handle this link. In this case, the web browser handles the custom data payload. To retrieve custom data from such a push check the next section. You need a NotificationClicked broadcastReceiver then.

## Images Carousel in Notification

In Reteno admin dashboard you may select up to 10 images to be sent with push notification. On Android platform the notification will be shown as a DecoratedCustomViewStyle. Images will be scaled to **500x250px** in order to satisfy the Android OS limits. The carousel will flip images automatically with 2500ms interval.

## Notification Events (push received, notification clicked)

If you wish to handle the notification click events, you can create a BroadcastReceiver component object and declare it in your `AndroidManifest.xml` file:

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

Where `com.example.CustomReceiverPushReceived` and `com.example.CustomReceiverNotificationClicked` are your receivers.

It is important to add a <meta-data> tag containing the `com.reteno.Receiver.PushReceived` and `com.reteno.Receiver.NotificationClicked` names of your receivers so that the SDK will be able to trigger them. 

Your receivers will receive a bundle containing the data payload that you send from the Yespo admin panel using the `Custom data` box.

```kotlin
override fun onReceive(context: Context?, intent: Intent?) {
       val customDataValue = intent?.extras?.getString("customDataKey");
   }
```
```java
@Override
   public void onReceive(Context context, Intent intent) {
   String customDataValue = intent.getExtras().getString("customDataKey");
   }
```

The `intent.getExtras()` is the method, with the help of which we get the `Bundle` object. From the `Bundle` object, we get the string from the `{"data":{"custom_data":"text for test"}}` JSON payload by the `data` key.

> 📘 Note
> 
> The `data` key name is optional but recommended. You can use any other name.  
> We do not recommend using the `notification` key name to specify the name of the object in JSON and the `es_interaction_id` key name inside JSON.

## Custom Pushes

As an app developer you may want to send not only `Reteno`-marketing push notifications to your user, but your own pushes. These may be push notifications related to your app-specific functionality, like chat, calendar events, incoming call notification, etc. In this case just create a custom Broadcast receiver and register it in the `AndroidManifest.xml` with the following intent-filter:

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

Then just receive the notification's data payload in the Bundle under onReceive method of your BroadcastReceiver.

> 📘 Important
> 
> 1. Don't send custom push notifications with `notification` block in JSON body. Use  `data` only. This will guarantee that the BroadcastReceiver receives your data payload consistently.
> 
> **WRONG**
> 
> ```json
> {
>   "to": "FCM_token",
>   "notification":{
>       "title":"Title_here",
>       "body":"Body_here"
>     }
> }
> ```
> 
> ** RIGHT**
> 
> ```json
> {
>   "to": "FCM_token",
>   "data":{
>       "Name" : "John",
>       "Room" : 4,
>       "Building" : 3
>     }
> }
> ```
> 
> 2. Don't send the following key in your `data` payload `es_interaction_id`. 
> 
> ** WRONG**
> 
> ```json
> {
>   "to": "FCM_token",
>   "data":{
>       "Name" : "John",
>       "es_interaction_id" : 123
>     }
> }
> ```