---
title: React Native Android SDK Setup
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
## Getting Started with Reteno SDK for Android

1. Install reteno-react-native-sdk using `yarn`:

```shell
yarn add reteno-react-native-sdk
```

or `npm`

```shell
npm i reteno-react-native-sdk
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
    implementation "com.google.firebase:firebase-messaging:(latest_version_here)"
    implementation "com.google.firebase:firebase-messaging-ktx:(latest_version_here)"
}
```

<Table>
  <thead>
    <tr>
      <th>
        <div style="width:250px">**Library**</div>
      </th>

      <th>
        **Description**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        com.reteno:fcm
      </td>

      <td>
        FCM enables push notifications through SDK and all core functionality
      </td>
    </tr>

    <tr>
      <td>
        firebase:firebase-messaging
      </td>

      <td>
        Firebase cloud messaging
      </td>
    </tr>

    <tr>
      <td>
        firebase:firebase-messaging-ktx
      </td>

      <td>
        Firebase cloud messaging Kotlin extensions
      </td>
    </tr>
  </tbody>
</Table>

## Setting up SDK

Follow our setup guide to integrate the Reteno SDK with your app.

### Step 1: Enable androidx in your gradle.properties file

```groovy
android.useAndroidX=true
android.enableJetifier=true
```

### Step 2: Add `com.reteno:fcm` and firebase dependencies in build.gradle

> 📘 Note
>
> Java 1.8 compiler is required. In app level `build.gradle`:

```groovy
android {
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
```

### Step 3: Edit your MainApplication class and provider API Access-Key at SDK initialization.

> 📘
>
> To setup SDK you need an SDK\_ACCESS\_KEY, visit [Managing Mobile SDK Access Keys](https://docs.yespo.io/reference/managing-mobile-sdk-access-keys) to get it.

Below is sample code you can add to your application class which gets you started with `RetenoSDK`.

If you have `MainApplication.java` :

```java
package [com.YOUR_PACKAGE];

import android.app.Application;

import androidx.annotation.NonNull;

import android.content.Context;
import com.facebook.react.PackageList;
import com.facebook.react.ReactApplication;
import com.facebook.react.ReactInstanceManager;
import com.facebook.react.ReactNativeHost;
import com.facebook.react.ReactPackage;
import com.facebook.react.bridge.ReactContext;
import com.facebook.react.config.ReactFeatureFlags;
import com.facebook.soloader.SoLoader;
import com.reteno.sample.newarchitecture.MainApplicationReactNativeHost;
import java.lang.reflect.InvocationTargetException;
import java.util.List;

import com.reteno.core.Reteno;
import com.reteno.core.RetenoImpl;
import com.retenosdk.RetenoReactNativeApplication;

public class MainApplication extends Application implements ReactApplication, RetenoReactNativeApplication {

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

    @Override
    public ReactContext getReactContext() {
        return this.getReactNativeHost().getReactInstanceManager().getCurrentReactContext();
    };
}
```

If you have `MainApplication.kt` :

```kotlin
package [com.YOUR_PACKAGE]
import android.app.Application
import com.facebook.react.PackageList
import com.facebook.react.ReactApplication
import com.facebook.react.ReactHost
import com.facebook.react.ReactNativeHost
import com.facebook.react.ReactPackage
import com.facebook.react.bridge.ReactContext
import com.facebook.react.defaults.DefaultNewArchitectureEntryPoint.load
import com.facebook.react.defaults.DefaultReactHost.getDefaultReactHost
import com.facebook.react.defaults.DefaultReactNativeHost
import com.facebook.react.flipper.ReactNativeFlipper
import com.facebook.soloader.SoLoader
import com.reteno.core.Reteno
import com.reteno.core.RetenoImpl
import com.retenosdk.RetenoReactNativeApplication
class MainApplication : Application(), ReactApplication, RetenoReactNativeApplication {
  private lateinit var retenoInstance: Reteno
  override fun getRetenoInstance(): Reteno {
    return retenoInstance
  }
  override fun getReactContext(): ReactContext? {
    return this.reactNativeHost.reactInstanceManager.currentReactContext
  }
  override fun onCreate() {
    super.onCreate()
    retenoInstance = RetenoImpl(this, "your_access_key_here")
  }
}
```

### Step 4: Set up your Firebase application for Firebase Cloud Messaging:

* Download your `google-services.json` config file (see how [here](https://support.google.com/firebase/answer/7015592?hl=en)).

* Add the above file to your root `app/` folder.

<Image align="center" width="80%" src="https://files.readme.io/aac2153-google-services-json.png" />

* Copy your FCM Server Key. In the [Firebase console](https://console.firebase.google.com/), click the gear icon next to Overview.

<Image align="center" width="80%" src="https://files.readme.io/5ee0068-FirebaseConsole.png" />

Click Project Settings → Cloud Messaging → Manage Service Accounts. 

<Image align="center" width="80%" src="https://files.readme.io/6706069-CloudConsole1.png" />

Go to Service accounts to download FirebaseAdminSdk account's json key.

<Image align="center" width="80%" src="https://files.readme.io/fd47a55-CloudConsole2.png" />

* Follow this manual to [set up Reteno admin panel](https://docs.yespo.io/docs/connect-your-mobile-app#for-all-devices) with your Firebase key.

Now you are ready to run your app and send a marketing push notification to your application.

Run your app on a physical Android device to make sure it builds correctly.

If you get an error like below:

<Image align="center" width="80% " src="https://files.readme.io/db1f8873da48293ddc74def3e82a968e2d5b553612245666fb64033c4dd47863-deshugaring_error.jpg" />

You can fix it by adding `coreLibraryDesugaring` to your `android/app/build.gradle`:

```groovy
android {
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
        coreLibraryDesugaringEnabled true
    }
}
...
dependencies {
  coreLibraryDesugaring 'com.android.tools:desugar_jdk_libs:(latest_version_here)'
}
```

If you get an error like below:

<Image align="center" width="80% " src="https://files.readme.io/7aee2dce2104eed53307cc0d20b1a947c3bbe52f481ab607bda98d78eed296d2-cxx_error.png" />

It can be fixed by updating react native version in your project to 0.75.4 or higher.

### Step 5 (OPTIONAL): Using Firebase for Remote notifications

If you already use Firebase for Remote notifications and would like to use Reteno as well, you need to Create a custom Messaging Service Class:

In your project folder, create a new Java Class file. You can choose any name for it, we'll use `CustomMessagingService.java` for the convenience.\
And put those contents in this Class. Basically, we override the `MessagingService` that is provided by firebase, by a custom one, that's extended from `RetenoFirebaseMessagingService`.

```java
package com.reteno.sample; // <-- make sure to replace it with your package name

import androidx.annotation.NonNull;

import com.google.firebase.messaging.RemoteMessage;
import com.reteno.fcm.RetenoFirebaseMessagingService;

public class CustomMessagingService extends RetenoFirebaseMessagingService {
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

And one more change, you need to go to your `AndroidManifest.xml` usually located in `.../android/app/src/main/AndroidManifest.xml` and add the above service, so it will be used for Firebase messaging events in your `application` tag:

```xml
<service android:name=".CustomMessagingService" android:exported="false">
    <intent-filter>
        <action android:name="com.google.firebase.MESSAGING_EVENT"/>
    </intent-filter>
</service>
```

So your `AndroidManifest.xml` will look something like this: 

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
  package="com.reteno.sample">

    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.POST_NOTIFICATIONS" />

    <application
      android:name=".MainApplication"
      android:label="@string/app_name"
      android:icon="@mipmap/ic_launcher"
      android:roundIcon="@mipmap/ic_launcher_round"
      android:allowBackup="false"
      android:networkSecurityConfig="@xml/network_security_config"
      android:usesCleartextTraffic="true"
      android:theme="@style/AppTheme">
      <service android:name=".CustomMessagingService" android:exported="false">
        <intent-filter>
          <action android:name="com.google.firebase.MESSAGING_EVENT"/>
        </intent-filter>
      </service>
      <activity
        android:name=".MainActivity"
        android:label="@string/app_name"
        android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|screenSize|smallestScreenSize|uiMode"
        android:launchMode="singleTask"
        android:windowSoftInputMode="adjustPan"
        android:exported="true">
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />
            <category android:name="android.intent.category.LAUNCHER" />
        </intent-filter>
      </activity>
    </application>
</manifest>
```

**Optional.** You may add your default icon and color for all Reteno notifications via AndroidManifest.xml. @drawable/ic\_notification is the icon to be displayed, and @color/red\_dark is the color of the icon. The only thing is that since Android 12, Material You has appeared - the user can change the color scheme of the entire device as they wants. Therefore, the color of the icon may differ on the latest android devices.

```xml
<meta-data
            android:name="@string/notification_icon"
            android:resource="@drawable/ic_notification" />
<meta-data
            android:name="@string/notification_icon_color"
            android:resource="@color/red_dark" />
```

> 📘 Note
>
> [Android Debug Mode](https://docs.yespo.io/reference/android-debug-mode) enables you to ensure that all events and user properties are logged correctly.
