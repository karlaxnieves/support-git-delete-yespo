---
title: Android In-App Messages
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: In-App Messages | Yespo Guide
  description: >-
    SDK allows you to handle custom data in in-app message buttons by extending
    a BroadcastReceiver class and registering it in the AndroidManifest.xml
    file.
  robots: index
next:
  description: ''
---
## Handling Custom Data

By default, Reteno SDK will handle links in in-app message buttons by starting an activity with `Intent.ACTION_VIEW` intent.

But you can put a map with key `customData` in button click action in your in-app layout.  
To receive this data in your application you have to extend a `BroadcastReceiver` class where you will receive custom data when button is clicked.

```kotlin
class CustomReceiverInAppData : BroadcastReceiver() {

    override fun onReceive(context: Context, intent: Intent) {
        // You can find all your custom data inside intent.extras and process it.
        // link from the button can also be found inside intent.extras under the "url" key.
    }

}
```
```java
public class CustomReceiverInAppData extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        // You can access all your custom data by calling intent.getExtras() and process it.
        // link from the button can also be found inside intent extras under the "url" key.
    }
}
```

In order for this to work, you have to register this receiver in `AndroidManifest.xml` under the `application` tag and set `com.reteno.custom-inapp-data` action in intent filter:

```xml
<application>
    ...
    <receiver
        android:name="com.reteno.sample.CustomReceiverInAppData"
        android:enabled="true"
        android:exported="false" >

        <intent-filter>
            <action android:name="com.reteno.custom-inapp-data" />
        </intent-filter>
    </receiver>
    ...
</application>
```

If you register such receiver, Reteno SDK will not open any links from buttons in in-app messages but instead will pass all data to your custom `BroadcastReceiver`.

All your custom data can be accessed through `intent.extras` in this receiver.

If there was a link assigned to a button, it will also be contained inside `intent.extras` under the `url` key.