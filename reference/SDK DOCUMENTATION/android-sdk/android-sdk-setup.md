---
title: Android SDK Setup
excerpt: The Reteno Android SDK for Mobile Customer Engagement and Analytics solutions.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
See the video manual on Android SDK setup:

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FNt3y549XbeE%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DNt3y549XbeE&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FNt3y549XbeE%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=Nt3y549XbeE",
  "title": "Android SDK Setup",
  "favicon": "http://www.google.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/Nt3y549XbeE/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=Nt3y549XbeE",
  "typeOfEmbed": "youtube"
}
[/block]


## Overview

`Reteno` is a lightweight SDK for Android that helps mobile teams integrate Reteno into their mobile apps. The server-side library makes it easy to call the `Reteno API`.

You can check the latest SDK version on this <a rel="nofollow" href="https://github.com/reteno-com/reteno-mobile-android-sdk/releases" target="_blank"> page. </a>

**The SDK supports**

- Native Android applications written in **Java**/**Kotlin** 

- Android 8.0 or later (minSdk = 26)

### Getting Started with Reteno SDK for Android

1. Add the mavenCentral repository in your project level `build.gradle`:

```groovy
buildscript {
    repositories {
        mavenCentral()
    }
    ...
}
```

2. Add `reteno` and `firebase` dependencies in your `build.gradle`application level:

```groovy
dependencies {
    implementation 'com.reteno:fcm:(SDK_latest_version_here)'
    ...
    implementation "com.google.firebase:firebase-messaging:23.1.0"
    implementation "com.google.firebase:firebase-messaging-ktx:23.1.0"
}
```

| <div style="width:250px">**Library**</div> | **Description**                                                       |
| ------------------------------------------ | --------------------------------------------------------------------- |
| com.reteno:fcm                             | FCM enables push notifications and all core functionality through SDK |
| firebase:firebase-messaging                | Firebase cloud messaging                                              |
| firebase:firebase-messaging-ktx            | Firebase cloud messaging Kotlin extensions                            |

License​ :

`Reteno Android SDK` is released under the MIT license. See [LICENSE](https://github.com/reteno-com/reteno-mobile-android-sdk/blob/master/LICENSE) for details.

***

## Setting Up SDK

Follow our setup guide to integrate the Reteno SDK with your app.

### Step 1. Enable AndroidX and Jetifier in Your `gradle.properties` File.

```groovy
android.useAndroidX=true
```

### Step 2. Determine Compiler for Java Code

Add `com.reteno:fcm` and `firebase` dependencies in `build.gradle`.

> 📘 Note
> 
> Java 1.8 compiler is required. In `build.gradle` app level

```groovy
android {
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
```

> 📘 Note
> 
> If your app is running on Android 13 or later (which you should) make sure to handle <a rel="nofollow" href="<https://developer.android.com/develop/ui/views/notifications/notification-permission>"> Notification runtime permissions </a>

### Step 3. Declare a Notification Permission in Your Manifest

```xml
<manifest ...>
    <uses-permission android:name="android.permission.POST_NOTIFICATIONS"/>
    <application ...>
        ...
    </application>
</manifest>
```

Next steps depend on Android SDK version you use:

- [From 2nd SDK Version](https://docs.yespo.io/reference/android-sdk-setup#from-2nd-sdk-version)
- [From 2.5.0 SDK Version](https://docs.yespo.io/reference/android-sdk-setup#from-250-sdk-version)

## From 2nd SDK Version

### Step 4. Initialize the Reteno SDK

Edit your custom `Application` class and provider API Access-Key at SDK initialization.

> 📘 Note
> 
> To set up SDK you need an SDK_ACCESS_KEY, visit [Managing Mobile SDK Access Keys](https://docs.yespo.io/reference/managing-mobile-sdk-access-keys) to get it.

Below is a sample code you can add to your application class, which gets you started with `RetenoSDK`. You may need to create a new class that extends the `Application` in this step. Don't forget to edit your manifest file to use the custom Application class. Also, make sure to provide the access-key in the constructor. You may store **Reteno access key** the way you wish based on your preferences:

```kotlin
package [com.YOUR_PACKAGE];

import android.app.Application
import com.reteno.core.Reteno
import com.reteno.core.RetenoConfig

class CustomApplication: Application() {

    override fun onCreate() {
        super.onCreate()
        Reteno.initWith(
            RetenoConfig(
                accessKey = BuildConfig.API_ACCESS_KEY
            )
        )
    }
}
```
```java
package [com.YOUR_PACKAGE];

import android.app.Application;

import androidx.annotation.NonNull;

import com.reteno.core.Reteno;
import com.reteno.core.RetenoApplication;
import com.reteno.core.RetenoImpl;

public class CustomApplication extends Application implements RetenoApplication {

    private Reteno retenoInstance;

    @Override
    public void onCreate() {
        super.onCreate();
        retenoInstance = new RetenoImpl(this, "your_access_key_here");
    }

    @NonNull
    @Override
    public Reteno getRetenoInstance() {
        return retenoInstance;
    }
}
```

**Manifest.xml**

```xml
<application
        android:name=".CustomApplication"
        ...
        >
...
</application>
```

> 📘 Important
> 
> Initialization settings are crucial for correct SDK functioning

### Step 5. Use SDK via `Reteno` Interface

Do not use `RetenoImpl` directly, access Reteno SDK across your application via `Singleton` instance:

```kotlin
val reteno = (application as CustomApplication).getRetenoInstance()
```
```java
Reteno reteno = Reteno.getInstance();
```

### Step 6. Handle Runtime Permissions

Since Android 13 was released you have to make sure you are handling <a rel="nofollow" href="https://developer.android.com/develop/ui/views/notifications/notification-permission" target="_blank"> Notification runtime permissions </a>

When user accepts permission, you have to call `updatePushPermissionStatus()` function from Reteno interface to notify the Reteno SDK that user has granted the permission.

```kotlin
val requestPermissionLauncher = registerForActivityResult(RequestPermission()) { isGranted: Boolean ->
        if (isGranted) {
            (getApplicationContext() as RetenoApplication).getRetenoInstance().updatePushPermissionStatus()
            Toast.makeText(this, "Permission granted", Toast.LENGTH_SHORT).show()
        } else {                    
            Toast.makeText(this, "Permission not granted", Toast.LENGTH_SHORT).show()
        }
    }
    
private fun checkPermissions() {
    if (ContextCompat.checkSelfPermission(this, permission.POST_NOTIFICATIONS) == PackageManager.PERMISSION_GRANTED) {
        return
    } else if (shouldShowRequestPermissionRationale(permission.POST_NOTIFICATIONS)) {
        AlertDialog.Builder(this)
            .setTitle("Notifications blocked")
            .setMessage("Please allow receiving notifications from this app in your device settings")
            .setNegativeButton("Cancel", null)
            .setPositiveButton("Go to Settings") { dialog, which ->
                    val intent = Intent(Settings.ACTION_APPLICATION_DETAILS_SETTINGS)
                    intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK)
                    val uri = Uri.fromParts("package", getPackageName(), null)
                    intent.data = uri
                    startActivity(intent)
                }.show()
    } else {
        requestPermissionLauncher.launch(permission.POST_NOTIFICATIONS)
    }
}
```
```java
private final ActivityResultLauncher<String> requestPermissionLauncher = registerForActivityResult(new ActivityResultContracts.RequestPermission(), isGranted -> {
        if (isGranted) {
            ((RetenoApplication) getApplicationContext()).getRetenoInstance().updatePushPermissionStatus();
            Toast.makeText(this, "Permission granted", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(this, "Permission not granted", Toast.LENGTH_SHORT).show();
        }
    });
private void checkPermissions() {
        if (ContextCompat.checkSelfPermission(this, POST_NOTIFICATIONS) == PackageManager.PERMISSION_GRANTED) {
            return;
        } else if (shouldShowRequestPermissionRationale(POST_NOTIFICATIONS)) {
            new AlertDialog.Builder(this)
                .setTitle("Notifications blocked")
                .setMessage("Please allow receiving notifications from this app in your device settings")
                .setNegativeButton("Cancel", null)
                .setPositiveButton("Go to Settings", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                        Intent intent = new Intent(Settings.ACTION_APPLICATION_DETAILS_SETTINGS);
                        intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
                        Uri uri = Uri.fromParts("package", getPackageName(), null);
                        intent.setData(uri);
                        startActivity(intent);
                    }
                })
            .show();
        } else {
            requestPermissionLauncher.launch(POST_NOTIFICATIONS);
        }
    }
```

### Please Check Optional Items Below

Now you are ready to run your app and send a marketing push notification to your application.

Run your app on a physical Android device to make sure it builds correctly.

> 📘 Optional
> 
> If you use own FCM pushes along with Reteno.

If you use your custom FCM service extended from `FirebaseMessagingService` don't extend it directly. Extend `RetenoFirebaseMessagingService` instead and call super methods for `onCreate`, `onNewToken`, `onMessageReceived`.

E.g.:

```kotlin
class CustomFcmService: RetenoFirebaseMessagingService() {

    override fun onCreate() {
        super.onCreate()
        // Your code here
    }

    override fun onNewToken(token: String) {
        super.onNewToken(token)
        // Your code here
    }

    override fun onMessageReceived(message: RemoteMessage) {
        super.onMessageReceived(message)
        // Your code here
    }
}
```
```java
public class CustomFcmService extends RetenoFirebaseMessagingService {

    @Override
    public void onCreate() {
        super.onCreate();
        // Your code here
    }

    @Override
    public void onNewToken(@NonNull String token) {
        super.onNewToken(token);
        // Your code here
    }

    @Override
    public void onMessageReceived(@NonNull RemoteMessage message) {
        super.onMessageReceived(message);
        // Your code here
    }
}
```

> 📘 Optional
> 
> You may add your default icon and color for all Reteno notifications via AndroidManifest.xml

```xml
<meta-data
            android:name="@string/notification_icon"
            android:resource="@drawable/ic_notification" />

<meta-data
            android:name="@string/notification_icon_color"
            android:resource="@color/red_dark" />
```

> 📘 Optional
> 
> Additionally, you can further configure the handling of [Deeplinks](https://docs.yespo.io/reference/android-push-handling#deeplinks), [Custom Data](https://docs.yespo.io/reference/android-push-handling#custom-data), and/or [Notification Events (Push Received, Notification Clicked)](https://docs.yespo.io/reference/android-push-handling#notification-events-push-received-notification-clicked).  
> To learn more, please visit the [Android Push Handling](https://docs.yespo.io/reference/android-push-handling) page.

### Using Reteno Config for Initialization

Optionally, you can provide RetenoConfig in the constructor to setup SDK on initialization

```kotlin
RetenoConfig.Builder()
    .pauseInAppMessages(false)
    .customDeviceIdProvider(createProvider())
    .lifecycleTrackingOptions(ALL)
    .accessKey(BuildConfig.API_ACCESS_KEY)
    .pausePushInAppMessages()
    .defaultNotificationChannelConfig { 
        it.setName("Custom name")
        it.setDescription("Custom description")
    }
    .build()
```

- `pauseInAppMessages(Bool)` - indicates paused/resumed state for in-app messages
- `customDeviceIdProvider(DeviceIdProvider)` -  Provider that will return custom userId. In case if id provided with a delay from external source. For example, if you have your own system for user identification, you can setup provider here that will wait until provider is going to return first non-null value and will use it for current user identification.
- `lifecycleTrackingOptions(LifecycleTrackingOptions)` - behavior of automatic app lifecycle event tracking, see [Android Lifecycle Tracking](https://docs.yespo.io/reference/app-lifecycle-events) to learn more
- `accessKey(String)` - your access key, can be provided directly in the SDK constructor or here. Key from config has higher priority. Two ways to provide access key maintained for backwards compatibility.
- `pausePushInAppMessages(Bool)` - stop/resume receiving in app messages from push notifications
- `defaultNotificationChannelConfig((NotificationChannelCompat.Builder) -> Unit)` - allows you to customize default notification channel for the app, note that this method sets up channel only for NEW users. For existing users please use `RetenoNotifications.updateDefaultNotificationChannel`

## From 2.5.0 SDK Version

### Step 4. Initialize Reteno SDK with your API Access-Key

Edit your custom `Application` class and provider API Access-Key at SDK initialization.

> 📘 Note
> 
> To set up SDK you need an SDK_ACCESS_KEY, visit [Managing Mobile SDK Access Keys](https://docs.yespo.io/reference/managing-mobile-sdk-access-keys) to get it.

Below is sample code you can add to your application class which gets you started with `RetenoSDK`. You may need to create a new class that extends the `Application` on this step. Don't forget to edit your manifest file to use the custom Application class. Also make sure to provide the **access-key** in configuration class. You may store Reteno access key the way you wish based on your preferences:

```kotlin
import android.app.Application
import com.reteno.core.Reteno
import com.reteno.core.RetenoConfig

class CustomApplication: Application() {

    override fun onCreate() {
        super.onCreate()
        Reteno.initWithConfig(
            RetenoConfig.Builder()
                .accessKey("your_access_key_here")
                .build()
        )
    }
}
```
```java
package [com.YOUR_PACKAGE];

import android.app.Application;

import androidx.annotation.NonNull;

import com.reteno.core.Reteno;
import com.reteno.core.RetenoApplication;
import com.reteno.core.RetenoImpl;

public class CustomApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();
        Reteno.initWithConfig(
                new RetenoConfig.Builder()
                        .accessKey("your_access_key_here")
                        .build()
        );
    }
}
```

**Manifest.xml**

```xml
<application
        android:name=".CustomApplication"
        ...
        >
...
</application>
```

> 📘 Important
> 
> Initialization settings are crucial for correct SDK functioning

### Step 5. Use SDK via `Reteno` Interface

Do not use `RetenoImpl` directly, access Reteno SDK across your application via your app instance. E.g. in Activity:

```kotlin
val reteno = Reteno.instance
```
```java
Reteno reteno = ((CustomApplication)getApplication()).getRetenoInstance();
```

### Step 6. Handle Runtime Permissions

Since Android 13 was released you have to make sure you are handling <a rel="nofollow" href="https://developer.android.com/develop/ui/views/notifications/notification-permission" target="_blank"> Notification runtime permissions </a>

When user accepts permission, you have to call `updatePushPermissionStatus()` function from Reteno interface to notify the Reteno SDK that user has granted the permission.

```kotlin
val requestPermissionLauncher = registerForActivityResult(RequestPermission()) { isGranted: Boolean ->
    if (isGranted) {
        Reteno.instance.updatePushPermissionStatus()
        Toast.makeText(this, "Permission granted", Toast.LENGTH_SHORT).show()
    } else {
        Toast.makeText(this, "Permission not granted", Toast.LENGTH_SHORT).show()
    }
}
private fun checkPermissions() {
    if (ContextCompat.checkSelfPermission(this, permission.POST_NOTIFICATIONS) == PackageManager.PERMISSION_GRANTED) {
        return
    } else if (shouldShowRequestPermissionRationale(permission.POST_NOTIFICATIONS)) {
        AlertDialog.Builder(this)
            .setTitle("Notifications blocked")
            .setMessage("Please allow receiving notifications from this app in your device settings")
            .setNegativeButton("Cancel", null)
            .setPositiveButton("Go to Settings") { dialog, which ->
                val intent = Intent(Settings.ACTION_APPLICATION_DETAILS_SETTINGS)
                intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK)
                val uri = Uri.fromParts("package", getPackageName(), null)
                intent.data = uri
                startActivity(intent)
            }.show()
    } else {
        requestPermissionLauncher.launch(permission.POST_NOTIFICATIONS)
    }
}
```
```java
private final ActivityResultLauncher<String> requestPermissionLauncher = registerForActivityResult(new ActivityResultContracts.RequestPermission(), isGranted -> {
        if (isGranted) {
            Reteno.getInstance().updatePushPermissionStatus();
            Toast.makeText(this, "Permission granted", Toast.LENGTH_SHORT).show();
        } else {
            Toast.makeText(this, "Permission not granted", Toast.LENGTH_SHORT).show();
        }
    });
private void checkPermissions() {
        if (ContextCompat.checkSelfPermission(this, POST_NOTIFICATIONS) == PackageManager.PERMISSION_GRANTED) {
            return;
        } else if (shouldShowRequestPermissionRationale(POST_NOTIFICATIONS)) {
            new AlertDialog.Builder(this)
                .setTitle("Notifications blocked")
                .setMessage("Please allow receiving notifications from this app in your device settings")
                .setNegativeButton("Cancel", null)
                .setPositiveButton("Go to Settings", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialog, int which) {
                        Intent intent = new Intent(Settings.ACTION_APPLICATION_DETAILS_SETTINGS);
                        intent.addFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
                        Uri uri = Uri.fromParts("package", getPackageName(), null);
                        intent.setData(uri);
                        startActivity(intent);
                    }
                })
            .show();
        } else {
            requestPermissionLauncher.launch(POST_NOTIFICATIONS);
        }
    }
```

### Please Check Optional Items Below

Now you are ready to run your app and send a marketing push notification to your application.

Run your app on a physical Android device to make sure it builds correctly.

> 📘 Optional
> 
> If you use own FCM pushes along with Reteno.

If you use your custom FCM service extended from `FirebaseMessagingService` don't extend it directly. Extend `RetenoFirebaseMessagingService` instead and call super methods for `onCreate`, `onNewToken`, `onMessageReceived`.

E.g.:

```kotlin
class CustomFcmService: RetenoFirebaseMessagingService() {

    override fun onCreate() {
        super.onCreate()
        // Your code here
    }

    override fun onNewToken(token: String) {
        super.onNewToken(token)
        // Your code here
    }

    override fun onMessageReceived(message: RemoteMessage) {
        super.onMessageReceived(message)
        // Your code here
    }
}
```
```java
public class CustomFcmService extends RetenoFirebaseMessagingService {

    @Override
    public void onCreate() {
        super.onCreate();
        // Your code here
    }

    @Override
    public void onNewToken(@NonNull String token) {
        super.onNewToken(token);
        // Your code here
    }

    @Override
    public void onMessageReceived(@NonNull RemoteMessage message) {
        super.onMessageReceived(message);
        // Your code here
    }
}
```

> 📘 Optional
> 
> You may add your default icon and color for all Reteno notifications via AndroidManifest.xml

```xml
<meta-data
            android:name="@string/notification_icon"
            android:resource="@drawable/ic_notification" />

<meta-data
            android:name="@string/notification_icon_color"
            android:resource="@color/red_dark" />
```

> 📘 Optional
> 
> Additionally, you can further configure the handling of [Deeplinks](https://docs.yespo.io/reference/android-push-handling#deeplinks), [Custom Data](https://docs.yespo.io/reference/android-push-handling#custom-data), and/or [Notification Events (Push Received, Notification Clicked)](https://docs.yespo.io/reference/android-push-handling#notification-events-push-received-notification-clicked).  
> To learn more, please visit the [Android Push Handling](https://docs.yespo.io/reference/android-push-handling) page.

### Using Reteno Config for Initialization

Optionally, you can provide RetenoConfig in the constructor to setup SDK on initialization

```kotlin
RetenoConfig.Builder()
    .pauseInAppMessages(false)
    .customDeviceIdProvider(createProvider())
    .lifecycleTrackingOptions(ALL)
    .accessKey(BuildConfig.API_ACCESS_KEY)
    .pausePushInAppMessages()
    .defaultNotificationChannelConfig { 
        it.setName("Custom name")
        it.setDescription("Custom description")
    }
    .build()
```

- `pauseInAppMessages(Bool)` - indicates paused/resumed state for in-app messages
- `customDeviceIdProvider(DeviceIdProvider)` -  Provider that will return custom userId. In case if id provided with a delay from external source. For example, if you have your own system for user identification, you can setup provider here that will wait until provider is going to return first non-null value and will use it for current user identification.
- `lifecycleTrackingOptions(LifecycleTrackingOptions)` - behavior of automatic app lifecycle event tracking, see [Android Lifecycle Tracking](https://docs.yespo.io/reference/app-lifecycle-events) to learn more
- `accessKey(String)` - your access key, can be provided directly in the SDK constructor or here. Key from config has higher priority. Two ways to provide access key maintained for backwards compatibility.
- `pausePushInAppMessages(Bool)` - stop/resume receiving in app messages from push notifications
- `defaultNotificationChannelConfig((NotificationChannelCompat.Builder) -> Unit)` - allows you to customize default notification channel for the app, note that this method sets up channel only for NEW users. For existing users please use `RetenoNotifications.updateDefaultNotificationChannel`