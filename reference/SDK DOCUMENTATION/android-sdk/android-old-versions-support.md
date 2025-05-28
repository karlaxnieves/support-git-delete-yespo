---
title: Android Old Versions Support
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
## Android 5 Support

In RetenoSDK version **1.5.2** we've decreased minSdkVersion from **26** to **21**. If your application supports Android OS versions starting from Android 5 it should be able to compile with RetenoSDK. Please note that all RetenoSDK features are disabled for devices running Android OS version lower than 8 (SDK 26), so your users on older devices won't benefit from using RetenoSDK. Also, if you are sending your custom Firebase push notifications and want to support devices older than Android 8, please add custom FirebaseMessagingService and extend it from **RetenoFirebaseMessagingService**, like this:

```kotlin
class CustomFirebaseMessagingService : RetenoFirebaseMessagingService() {
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
public class CustomFirebaseMessagingService extends RetenoFirebaseMessagingService {
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

And don't forget the `AndroidManifest.xml` part:

```xml
<service
    android:name=".CustomFirebaseMessagingService"
    android:exported="false">
    <intent-filter>
        <action android:name="com.google.firebase.MESSAGING_EVENT"/>
    </intent-filter>
</service>
```

For Android 8 and newer this service is not required.

Also, due to the fact that some Java 8 APIs are used in the SDK which are only supported from Android 8 (sdk-26) or higher, it is necessary to add the following lines to the app module’s `build.gradle` file.

```groovy
android {
    compileOptions {
        // Flag to enable support for the new language APIs
        coreLibraryDesugaringEnabled true
        // Sets Java compatibility to Java 8
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
dependencies {
    coreLibraryDesugaring 'com.android.tools:desugar_jdk_libs:1.2.2'
}
```