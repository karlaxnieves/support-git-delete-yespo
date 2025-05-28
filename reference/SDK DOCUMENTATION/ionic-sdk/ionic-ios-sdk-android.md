---
title: Ionic Android SDK Setup
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
### Getting started with Reteno Plugin for Android

1. Install cordova-plugin-reteno using `cordova`:

```shell
ionic cordova plugin add cordova-plugin-reteno
```

2. Install `firebase`  plugin in application:

```shell
ionic cordova plugin add cordova-plugin-firebasex
```

3. Compile bundles to use Awesome Cordova Plugin for both plugins
   - <a rel="nofollow" href="https://github.com/reteno-com/reteno-cordova/tree/main/awesome-cordova-plugin-reteno"> awesome-cordova-plugin-reteno </a> 
   - <a rel="nofollow" href="https://github.com/reteno-com/reteno-cordova/tree/main/awesome-cordova-plugin-reteno-firebase"> awesome-cordova-plugin-reteno-firebase </a>

```shell
npm run build
```

4. Add dependency into your project:

```shell
npm i <path>/awesome-cordova-plugin-reteno/dist/  
npm i <path>/awesome-cordova-plugin-reteno-reteno/dist/
```

## Setting up SDK

Follow our setup guide to integrate the Reteno SDK with your app.

### Step 1: Add Android platform

```shell
ionic cordova platform add android
```

### Step 2: Set up your Firebase application for Firebase Cloud Messaging:

- Download your `google-services.json` config file (see how [here](https://support.google.com/firebase/answer/7015592?hl=en)).

- Add the above file to your root `app/` folder.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4202e48-google-services-json.png",
        "",
        "Firebase Cloud Messaging"
      ],
      "align": "center"
    }
  ]
}
[/block]


- Copy your FCM Server Key. In the [Firebase console](https://console.firebase.google.com/), click the gear icon next to Overview. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/232a501-FirebaseConsole.png",
        "",
        "FCM Server Key"
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


Then click _Project Settings_ → _Cloud Messaging_ → _Manage Service Accounts_. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2f62d0c-CloudConsole1.png",
        "",
        "Manage Service Accounts"
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


Go to Service accounts to download `FirebaseAdminSdk` account's json key.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b841909-CloudConsole2.png",
        "",
        "FirebaseAdminSdk"
      ],
      "align": "center",
      "sizing": "600px"
    }
  ]
}
[/block]


- Follow this manual to [set up Reteno admin panel](https://docs.reteno.com/docs/connect-your-mobile-app) with your Firebase key.

Now you are ready to run your app and send a marketing push notification to your application.

### Step 3: Edit your MainApplication class

Below is sample code you can add to your application class which gets you started with `RetenoSDK`.

```java
package [com.YOUR_PACKAGE];

import android.app.Application;

import androidx.annotation.NonNull;

import com.reteno.core.Reteno;
import com.reteno.core.RetenoImpl;
import com.reteno.plugin.CordovaRetenoApplication;

public class MainApplication extends Application implements CordovaRetenoApplication {
    private Reteno retenoInstance=null;

    @Override
    public void onCreate() {
        super.onCreate();
        retenoInstance = new RetenoImpl(this, "YOUR_API_KEY");
    }

    @NonNull
    @Override
    public Reteno getRetenoInstance() {
        return retenoInstance;
    }
}
```

### Step 4: Link development plugin folder (optional)

In case you have a local copy of Reteno Cordova Plugin, you may want to add it to the project, in order to be able to modify or debug it. If this is the case, you should remove the current plugin version from npm and add the local one. Provided that the plugin is located at the parent folder, this can be done as follows:

```shell
  ionic cordova plugin remove cordova-plugin-reteno
  ionic cordova plugin add --link <path_to_plugin_folder>/cordova-plugin-reteno/

  ionic cordova plugin remove cordova-plugin-reteno-firebase
  ionic cordova plugin add --link <path_to_plugin_folder>/cordova-plugin-reteno-firebase/
```

So, `config.xml` file should contain one line like this:

```shell
<plugin name="cordova-plugin-reteno" spec="file:../cordova-plugin-reteno" />
<plugin name="cordova-plugin-reteno-firebase" spec="file:../cordova-plugin-reteno-firebase" />
```

### Step 5: Firebase usage

If you already use Firebase for Remote notifications or would like to use Firebase along with Reteno, you can use it as it is, because cordova-plugin-reteno-firebase provides Firebase support out of the box.

## Run Android version

- **Run from command line**: 

```shell
ionic cordova run android
```

- **Run from Android Studio**: Go to plaftforms/android folder. Create android studio project and run `MainActivity` class

Run your app on a physical Android device to make sure it builds correctly.

> 📘 Note
> 
> [Android Debug Mode](https://docs.yespo.io/reference/android-debug-mode) enables you to ensure that all events and user properties are logged correctly.