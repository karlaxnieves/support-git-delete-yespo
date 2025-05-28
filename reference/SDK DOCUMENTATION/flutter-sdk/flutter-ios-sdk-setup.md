---
title: Flutter iOS SDK Setup
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Flutter iOS SDK Setup | Guide
  description: >-
    This guide shows the setup process of integrating the Reteno Flutter SDK
    with your app and enhancing your app's notification delivery and analytics
    features.
  robots: index
next:
  description: ''
---
## Setting up the SDK

Follow our setup guide to integrate the Reteno Flutter SDK with your app.

### Step 1: Add a Notification Service Extension

The `NotificationServiceExtension` allows your iOS application to receive rich notifications with images. It's also required for Reteno's analytics features.

**1.1**  In Xcode Select `File → New → Target...`

**1.2**  Select `Notification Service Extension` then press `Next`.

<Image align="center" width="80%" src="https://files.readme.io/8d1311e-create_notification_service_extension.png" />

**1.3**  Enter the product name as `NotificationServiceExtension` and press `Finish`.

Do not select `Activate` on the dialog that is shown after selecting `Finish`.

<Image align="center" width="80%" src="https://files.readme.io/43947d4-choose_options_for_extension.png" />

**1.4**  Press `Cancel` on the Activate scheme prompt.

By canceling, you keep Xcode debugging your app instead of the extension you’ve just created.

If you activate the prompt by accident, you can switch back to debugging your app in Xcode (next to the Play button).

**1.5**  In the project navigator, select the project directory and select the `NotificationServiceExtension` target in the targets list.

Check that the Deployment Target is set to the same value as your Main Application Target.

> 📘 Note
>
> iOS versions under 10 will not be able to get Rich Media.

<Image align="center" width="80%" src="https://files.readme.io/13b02af-configure_target.png" />

**1.6**   In the project navigator, select the `NotificationServiceExtension` folder and open the `NotificationService.swift`, then replace the entire file contents with the following code. Ignore any build errors at this point. We will import the Reteno module, which will resolve any errors.

```swift
import UserNotifications
import Reteno

class NotificationService: RetenoNotificationServiceExtension {}
```

More about Notification Service Extension [Modifying Content in Newly Delivered Notifications](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications "\{rel='nofollow'}")

### Step 2: Install the SDK

**2.1** Modify your `Podfile` to contain next dependencies:

```swift
target 'Runner' do
  ...
  pod 'Reteno', '2.0.11'
  pod 'FirebaseCore'
  pod 'FirebaseMessaging'
  ...
end

target 'NotificationServiceExtension' do
  ...
  pod 'Reteno', '2.0.11'
  ...
end
```

**2.2**  Open the `<project-name>.xcworkspace` file.

### Step 3: Add reteno\_flutter\_sdk dependency in pubspec.yaml:

Install reteno\_plugin using flutter pub command

```shell
flutter pub add reteno_plugin
```

This will add entry in your project's pubspec.yaml (and run flutter pub get):

```yaml
dependencies:
  reteno_flutter_sdk: (latest_version_here)
```

### Step 3: Import Reteno into Your App Delegate

To setup SDK you need an `SDK_ACCESS_KEY`, visit [Managing Mobile SDK Access Keys](https://docs.reteno.com/reference/managing-mobile-sdk-access-keys) to get it.

#### Method 1: you have AppDelegate.swift file

Open your `AppDelegate.swift` file and add the `Reteno` initialization code to the `didFinishLaunchingWithOptions` method.\
Make sure to import the Reteno module `import Reteno`

```swift
import UIKit
import Flutter
import Reteno
import FirebaseCore
import FirebaseMessaging

@UIApplicationMain
@objc class AppDelegate: FlutterAppDelegate {
    override func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        GeneratedPluginRegistrant.register(with: self)
        FirebaseApp.configure()
        Messaging.messaging().delegate = self
        Reteno.start(apiKey: "SDK_ACCESS_KEY")
        
        Reteno.userNotificationService.registerForRemoteNotifications(with: [.sound, .alert, .badge], application: application)
        return super.application(application, didFinishLaunchingWithOptions: launchOptions)
    }

    // Remaining contents of your AppDelegate Class...
}
```

### Step 4: Add App Groups

**4.1**  In your Main app target got to **"Signing & Capabilities"**  → **"All"**

**4.2**  Click **"+ Capability"** if you do not have App Groups in your app yet.

<Image align="center" width="80%" src="https://files.readme.io/daac1ed-add_group_main_target.png" />

**4.3**  Select App Groups.

<Image align="center" width="80%" src="https://files.readme.io/2f8b430-app_groups_capability.png" />

**4.4**  Under App Groups click the **"+"** button.

**4.5**  Fill the **"App Groups"** container as `group.{bundle_id}.reteno-local-storage` where `bundle_id` is the same as **"Bundle Identifier"** off your app (in the main target) and press `OK`.

**4.6**  In the `NotificationServiceExtension` target and repeat steps **4.2** - **4.5** for extension target

<Image align="center" width="80%" src="https://files.readme.io/d0624fa-add_group_in_extension.png" />

> 📘 Note
>
> The group name structure should be `group.{bundle_id}.reteno-local-storage` where `bundle_id` is the same as your **Main App target** "Bundle Identifier". **Do Not Include** NotificationServiceExtension.

For more information visit [Configuring App Groups](https://developer.apple.com/documentation/xcode/configuring-app-groups "\{rel='nofollow'}")

### Step 5: Add ‘Push Notification’ Capability to Your Main App Target (not `NotificationServiceExtension`!)

### Step 6: Provide Device Token to the SDK via Next Method:

```swift
Reteno.userNotificationService.processRemoteNotificationsToken(_ deviceToken: String)
```

If you use `Firebase` for Remote notifications, it should be done in `MessagingDelegate` method

```swift
extension AppDelegate: MessagingDelegate {
    
    func messaging(_ messaging: Messaging, didReceiveRegistrationToken fcmToken: String?) {
        guard let fcmToken = fcmToken else { return }
        
        Reteno.userNotificationService.processRemoteNotificationsToken(fcmToken)
    }
    
}
```

In other case, convert `deviceToken` data to the `String` and provide to the SDK, like in the example below:

```swift
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
        let tokenString = deviceToken.map { String(format: "%02.2hhx", $0) }.joined()
        Reteno.userNotificationService.processRemoteNotificationsToken(tokenString)
    }
```

### Step 7: Run Your App and Send Yourself a Notification

Run your app on a physical iOS device to make sure it builds correctly. You should be prompted to subscribe to push notifications. Please note that the iOS Simulator does not support receiving remote push notifications. 

> 📘 Note
>
> [iOS Debug Mode](https://docs.yespo.io/reference/ios-debug-mode) enables you to ensure that all events and user properties are logged correctly.
