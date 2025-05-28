---
title: Cordova iOS SDK Setup
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
## Setting up the SDK

Follow our setup guide to integrate the Reteno Plugin with your app.

### Getting Started with Reteno Plugin for iOS

1. Install cordova-plugin-reteno using `cordova`:

```shell
cordova plugin add cordova-plugin-reteno
```

2. Install `firebase`  plugin in application:

```shell
cordova plugin add cordova-plugin-firebasex
```

## Setting up SDK

Follow our setup guide to integrate the Reteno SDK with your app.

### Step 1: Add iOS platform

```shell
cordova platform add ios
```

### Step 2: Set up your Firebase application for Firebase Cloud Messaging:

* Download your `google-services.json` config file (see how [here](https://support.google.com/firebase/answer/7015592?hl=en)).

* Add the above file to your root `app/` folder.

<Image align="center" src="https://files.readme.io/401a279-google-services-json.png" />

* Copy your FCM Server Key. In the [Firebase console](https://console.firebase.google.com/), click the gear icon next to Overview.

<Image align="center" width="600px" src="https://files.readme.io/5a5bf7c-FirebaseConsole.png" />

Then click *Project Settings* → *Cloud Messaging* → *Manage Service Accounts*.

<Image align="center" width="600px" src="https://files.readme.io/a74ba86-CloudConsole1.png" />

 Go to Service accounts to download `FirebaseAdminSdk` account's json key.

<Image align="center" width="600px" src="https://files.readme.io/ca223b0-CloudConsole2.png" />

* Follow this manual to [set up Reteno admin panel](https://docs.reteno.com/docs/connect-your-mobile-app) with your Firebase key.

Now you are ready to run your app and send a marketing push notification to your application.

### Step 3: Configure IOS project:

Create `RetenoTransitionLayer.swift` file; Go to your project in Xcode and create new swift file under your target; When system will ask if you want to create bridge file also, agree

After that put next code in your `RetenoTransitionLayer.swift` file:

```swift
import Foundation
import UIKit
import Reteno

@objc public class RetenoTransitionLayer: NSObject {
  @objc class func setup(forApplication application: UIApplication) {
    Reteno.start(apiKey: "SDK_API_KEY");

    // Register for receiving push notifications
    // registerForRemoteNotifications will show the native iOS notification permission prompt
    // Provide UNAuthorizationOptions or use default
    Reteno.userNotificationService.registerForRemoteNotifications(with: [.sound, .alert, .badge], application: application);
  }

  @objc class func processRemoteNotificationsToken(withDeviceToken token: Data) {
    let tokenString = token.map { String(format: "%02.2hhx", $0) }.joined();
    Reteno.userNotificationService.processRemoteNotificationsToken(tokenString);
  }

  @objc class func processRemoteNotificationsToken(withFCMToken fcmToken: String?) {
    guard let fcmToken = fcmToken else { return }
    Reteno.userNotificationService.processRemoteNotificationsToken(fcmToken);
  }
}
```

Then go to `AppDelegate.m` and modify your code to contain `RetenoTransitionLayer` setup logic

```objectivec
#import "AppDelegate.h"
#import "MainViewController.h"

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary<UIApplicationLaunchOptionsKey, id> *)launchOptions
{
    self.viewController = [[MainViewController alloc] init];

    [RetenoTransitionLayer setupForApplication:application];

    return [super application:application didFinishLaunchingWithOptions:launchOptions];
}

@end

```

If you get an "Use of undeclared identifier 'RetenoTransitionLayer'" error here, it means that you need to create a Bridging header file yourself, here's how to do that:\
In Xcode press File → New → File → Header File

Save it with `YourProjectName-Bridging-Header.h` name, make sure to replace YourProjectName with your ios Xcode project name, in our example project, the header was created manually as `Bridging-Header.h`, the ".h" extension will be put automatically.

Delete the contents of this file, and replace them with next imports:

```objectivec
#import <Cordova/CDV.h>
```

Finally, you need to import this header in your AppDelegate header file (AppDelegate.h) as `#import "ExampleCordova-Swift.h"` (you should enter your file name)

```objectivec
#import "ExampleCordova-Swift.h"
```

This is needed in order to use Objective-C and Swift files together in a single project.\
You can read more about [importing swift](https://developer.apple.com/documentation/swift/importing-swift-into-objective-c) and [bridging headers](https://developer.apple.com/documentation/swift/importing-objective-c-into-swift), [react-native docs](https://reactnative.dev/docs/native-modules-ios#exporting-swift) exporting swift section.

If you get an "No known class method for selector `'setupForApplication:'`" error, or any other "No known class method for selector" error related to `RetenoTransitionLayer`:

<Image align="center" width="80% " src="https://files.readme.io/2bb6f1d-Screenshot_2023-12-21_at_20.27.12.png" />

You need to open your Project file, go to `Build Settings`, and in the search bar type: `Swift Compiler` and scroll down until you find `Swift Compiler - General` section.

There is a chance that your `Objective-C Bridging Header` might be empty, so you need to specify the name of the bridging header that you're using. Double click on the right side of this field, and enter the name of YOUR bridging header file, in our example project we will have `Bridging-Header.h`. Additionally you can check `Objective-C Generated Interface Header Name` which should be `YourAppName-Swift.h`, in our example project it's `ExampleCordova-Swift.h`.

And that's it, you should be good to go.

### Step 4: Add a Notification Service Extension

The `NotificationServiceExtension` allows your iOS application to receive rich notifications with images. It's also required for Reteno's analytics features.

**4.1** In Xcode Select `File > New > Target...`

**4.2** Select `Notification Service Extension` then press `Next`.

<Image align="center" width="80%" src="https://files.readme.io/c5fad32-create_notification_service_extension.png" />

**4.3** Enter the product name as `NotificationServiceExtension` and press `Finish`.

Do not select `Activate` on the dialog that is shown after selecting `Finish`.

<Image align="center" width="80%" src="https://files.readme.io/9faf03c-choose_options_for_extension.png" />

**4.4** Press `Cancel` on the Activate scheme prompt.

By canceling, you keep Xcode debugging your app instead of the extension you’ve just created.

If you activate the prompt by accident, you can switch back to debugging your app in Xcode (next to the Play button).

**4.5** In the project navigator, select the project directory and select the `NotificationServiceExtension` target in the targets list.

Check that the Deployment Target is set to the same value as your Main Application Target.

> 📘 Note
>
> iOS versions under 10 will not be able to get Rich Media.

<Image align="center" width="80%" src="https://files.readme.io/b1e7987-configure_target.png" />

**4.6** In the project navigator, select the `NotificationServiceExtension` folder and open the `NotificationService.swift`, then replace the entire file contents with the following code. Ignore any build errors at this point. We will import the Reteno module, which will resolve any errors.

```swift
import UserNotifications
import Reteno

class NotificationService: RetenoNotificationServiceExtension {}
```

More about Notification Service Extension [Modifying Content in Newly Delivered Notifications](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications)

### Step 5: Add App Groups

**5.1** In your Main app target got to **"Signing & Capabilities"** > **"All"**

**5.2** Click **"+ Capability"** if you do not have App Groups in your app yet.

<Image align="center" width="80%" src="https://files.readme.io/1173533-add_group_main_target.png" />

**5.3** Select App Groups.

<Image align="center" width="80%" src="https://files.readme.io/945e24e-app_groups_capability.png" />

**5.4** Under App Groups click the **"+"** button.

**5.5** Fill the **"App Groups"** container as `group.{bundle_id}.reteno-local-storage` where `bundle_id` is the same as **"Bundle Identifier"** off your app (in the main target) and press `OK`.

**5.6** In the `NotificationServiceExtension` target and repeat steps **5.2** - **5.5** for extension target

<Image align="center" width="80%" src="https://files.readme.io/2875896-add_group_in_extension.png" />

Note that group name structure should be `group.{bundle_id}.reteno-local-storage` where `bundle_id` is the same as your **Main App target** "Bundle Identifier". **Do Not Include** NotificationServiceExtension.

For more information visit [Configuring App Groups](https://developer.apple.com/documentation/xcode/configuring-app-groups)

### Step 6: Add `Push Notification` capability to your main app target (not `NotificationServiceExtension`!)

### Step 7: Link development plugin folder (optional):

In case you have a local copy of Reteno Cordova Plugin, you may want to add it to the project, in order to be able to modify or debug it. If this is the case, you should remove the current plugin version from npm and add the local one. Provided that the plugin is located at the parent folder, this can be done as follows:

```sh
  cordova plugin remove cordova-plugin-reteno
  cordova plugin add --link <path_to_plugin_folder>/cordova-plugin-reteno/
  cordova plugin remove cordova-plugin-reteno-firebase
  cordova plugin add --link <path_to_plugin_folder>/cordova-plugin-reteno-firebase/
```

So, `config.xml` file should contain one line like this:

```
<plugin name="cordova-plugin-reteno" spec="file:../cordova-plugin-reteno" />
<plugin name="cordova-plugin-reteno-firebase" spec="file:../cordova-plugin-reteno-firebase" />
```

### Step 8: Firebase usage

If you already use Firebase for Remote notifications or would like to use Firebase along with Reteno, you can use it as it is, because cordova-plugin-reteno-firebase provides Firebase support out of the box.

## Run iOS version

* **Run from command line**:

```shell
cordova run ios
```

* **Run from Xcode**: Go to platforms/ios folder and open `Reteno Cordova Example.xcworkspace`

> 📘 Note
>
> [iOS Debug Mode](https://docs.yespo.io/reference/ios-debug-mode) enables you to ensure that all events and user properties are logged correctly.
