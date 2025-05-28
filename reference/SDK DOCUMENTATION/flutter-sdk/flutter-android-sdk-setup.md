---
title: Flutter Android SDK Setup
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Flutter Android SDK Setup | Guide
  description: >-
    Follow along to enable push notifications and core functionalities in your
    app using Reteno SDK and Firebase.
  robots: index
next:
  description: ''
---
## Getting Started With Reteno SDK for Android

1. Install reteno\_flutter\_sdk using flutter pub command:

```shell
flutter pub add reteno_plugin
```

This will add entry in your project's pubspec.yaml (and run flutter pub get):

```yaml
dependencies:
  reteno_plugin: (latest_version_here)
```

2. Add mavenCentral repository in your project level `build.gradle`:

```groovy
buildscript { 
    repositories { 
    mavenCentral() 
    } 
... 
}
```

3. Add `reteno` and `firebase` dependencies in application level `build.gradle`:

```groovy
dependencies {
    implementation 'com.reteno:fcm:(latest_version_here)'
    ...
    implementation "com.google.firebase:firebase-messaging:23.1.0"
    implementation "com.google.firebase:firebase-messaging-ktx:23.1.0"
}
```

| **Library**                     | **Description**                                                       |
| ------------------------------- | --------------------------------------------------------------------- |
| com.reteno:fcm                  | FCM enables push notifications through SDK and all core functionality |
| firebase:firebase-messaging     | Firebase cloud messaging                                              |
| firebase:firebase-messaging-ktx | Firebase cloud messaging Kotlin extensions                            |

## Setting Up SDK

Follow our setup guide to integrate the Reteno SDK with your app.

### Step 1: Enable Androidx in Your gradle.properties file

```groovy
android.useAndroidX=true
android.enableJetifier=true
```

### Step 2: Add ‘com.reteno:fcm’ and Firebase Dependencies in build.gradle

> 📘 Note
>
> Java 1.8 compiler is required. In app level `build.gradle:`

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
> If you are using `minSdkVersion<26` please add desugaring dependency in you app level build.gradle as follows

```groovy
compileOptions {
    coreLibraryDesugaringEnabled true
    ...
}
...
dependencies {
    coreLibraryDesugaring 'com.android.tools:desugar_jdk_libs:1.2.2'
    ...
}
```

### Step 3: Edit Your MainApplication Class and Provider API Access-Key at SDK Initialization.

Below is sample code you can add to your application class which gets you started with `RetenoSDK`.

```kotlin
package [com.YOUR_PACKAGE];
import com.reteno.core.Reteno
import com.reteno.core.RetenoApplication
import com.reteno.core.RetenoImpl
import io.flutter.app.FlutterApplication

class CustomApplication : FlutterApplication(), RetenoApplication {
    private lateinit var retenoInstance: Reteno
    
    override fun onCreate() {
        super.onCreate()
        retenoInstance = RetenoImpl(this, "your_access_key_here")
    }
    
    override fun getRetenoInstance(): Reteno {
        return retenoInstance
    }
}
```

### Step3 Alternative: Use Lazy Initialization of Reteno

```kotlin
package [com.YOUR_PACKAGE];
import com.reteno.core.Reteno
import com.reteno.core.RetenoApplication
import com.reteno.core.RetenoImpl
import io.flutter.app.FlutterApplication

class CustomApplication : FlutterApplication(), RetenoApplication {
    private lateinit var retenoInstance: Reteno

    override fun onCreate() {
        super.onCreate()
        retenoInstance = RetenoImpl(this)
    }

    override fun getRetenoInstance(): Reteno {
        return retenoInstance
    }
}
```

and then in Flutter app, call `Reteno.initWith`

```dart Dart
 await Reteno.initWith(
    accessKey: 'access_key',
    // optional
    isPausedInAppMessages: true,
    // optional
    lifecycleTrackingOptions: LifecycleTrackingOptions(
        appLifecycleEnabled: true,
        pushSubscriptionEnabled: true,
        sessionEventsEnabled: true,
    ),
    // optional if you want to use custom device id
    customDeviceId: () async {
        return await Amplitude.getInstance().getDeviceId();
    },
);
```

### Step 4:  Set Up Your Firebase Application for Firebase Cloud Messaging:

* Download your `google-services.json` config file (see how [here](https://support.google.com/firebase/answer/7015592?hl=en "\{rel='nofollow'}")).

* Add the above file to your root `app/` folder.

<Image align="center" width="80%" src="https://files.readme.io/baf1ff7-google-services-json.png" />

* Copy your FCM Server Key. In the [Firebase console](https://console.firebase.google.com/ "\{rel='nofollow'}"), click the gear icon next to *Project Overview*, then click Project Settings → Cloud Messaging → Manage Service Accounts. Go to Service accounts to download FirebaseAdminSdk account's json key.

<Image align="center" width="80%" src="https://files.readme.io/6987c7d-FirebaseConsole.png" />

<Image align="center" width="80%" src="https://files.readme.io/f4bac6b-CloudConsole1.png" />

<Image align="center" width="80%" src="https://files.readme.io/a577959-CloudConsole2.png" />

* Follow this manual to [set up Yespo admin panel](https://docs.yespo.io/docs/connect-your-mobile-app#for-all-devices) with your Firebase key.

Now you are ready to run your app and send a marketing push notification to your application.

Run your app on a physical Android device to make sure it builds correctly.

> 📘 Note
>
> [Android Debug Mode](https://docs.yespo.io/reference/android-debug-mode) enables you to ensure that all events and user properties are logged correctly.
