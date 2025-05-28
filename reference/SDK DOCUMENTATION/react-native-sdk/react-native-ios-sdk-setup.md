---
title: React Native iOS SDK Setup
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
## Setting Up the SDK

Follow our setup guide to integrate the Reteno React Native SDK with your app.

### Step 1: Add a Notification Service Extension

The `NotificationServiceExtension` allows your iOS application to receive rich notifications with images. It's also required for Reteno's analytics features.

**1.1**  In Xcode Select `File → New → Target...`

**1.2**  Select `Notification Service Extension` then press `Next`.

<Image align="center" width="80%" src="https://files.readme.io/5d9ba16-create_notification_service_extension.png" />

**1.3**  Enter the product name as `NotificationServiceExtension` and press `Finish`.

> 📘 Note
>
> Do not select `Activate` on the dialog that is shown after selecting `Finish`.

<Image align="center" width="80%" src="https://files.readme.io/65b8817-choose_options_for_extension.png" />

**1.4**  Press `Cancel` on the Activate scheme prompt.

By canceling, you keep Xcode debugging your app instead of the extension you’ve just created.

If you activate the prompt by accident, you can switch back to debugging your app in Xcode (next to the Play button).\
**1.5**  In the project navigator, select the project directory and select the `NotificationServiceExtension` target in the targets list.

Check that the Deployment Target is set to the same value as your Main Application Target.

> 📘 Note
>
> iOS versions under 10 will not be able to get Rich Media.

<Image align="center" width="80%" src="https://files.readme.io/876660e-configure_target.png.png" />

**1.6**   In the project navigator, select the `NotificationServiceExtension` folder and open the `NotificationService.swift`, then replace the entire file contents with the following code. Ignore any build errors at this point. We will import the Reteno module, which will resolve any errors.

**Note** After adding `NotificationServiceExtension` you have to make sure that sandbox is off (like on screenshot below), because it can cause an error.

<Image align="center" width="80% " src="https://files.readme.io/699302f6dc8d84b2136cd0c01c2d23787a83bd8e4d45febd8cf9e098a97403f9-sandbox_settings.png" />

```swift
import UserNotifications
import Reteno

class NotificationService: RetenoNotificationServiceExtension {}
```

More about Notification Service Extension [Modifying Content in Newly Delivered Notifications](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications "\{rel='nofollow'}")

### Step 2: Install the SDK

**2.1** Modify your `Podfile` to contain next dependencies:

```swift
target 'NotificationServiceExtension' do
  pod 'Reteno'
end

target 'RetenoSdkExample' do
  ...
  pod 'Reteno'
end
```

***2.1.1** OPTIONAL* IF YOU USE SENTRY-REACT-NATIVE SEPARATELY:

If you have previously used <a rel="nofollow" href="https://github.com/getsentry/sentry-react-native"> Sentry </a> and had a workaround for `Sentry` pod, we no longer have `Sentry` as a dependency because it lead to a version missmatch related to pod installation issues, and starting from reteno-react-native-sdk 1.4.1, we have removed `Sentry` completely, so you can remove unnecessary pod from your Podfile, you can refer to our <a rel="nofollow" href="https://github.com/reteno-com/reteno-react-native-sdk/tree/main/example"> example project </a> Podfile.

```swift
target 'NotificationServiceExtension' do
  pod 'Reteno'
end

target 'RetenoSdkExample' do
  ...
  pod 'Reteno'
end
```

**2.2**  Open the `<project-name>.xcworkspace` file.

### Step 3: Install reteno-react-native-sdk

* using `yarn`:

```shell
yarn add reteno-react-native-sdk
```

* or `npm`

```shell
npm i reteno-react-native-sdk
```

* don't forget about pods (in iOS folder)

```sh
cd ios && pod install
```

### Step 4: Import Reteno into Your App Delegate

To setup SDK you need an `SDK_ACCESS_KEY`, visit [Managing Mobile SDK Access Keys](https://docs.yespo.io/reference/managing-mobile-sdk-access-keys) to get it.

##### Method 1: you have AppDelegate.swift file

Open your `AppDelegate.swift` file and add the `Reteno` initialization code to the `didFinishLaunchingWithOptions` method.\
Make sure to import the Reteno module `import Reteno`

```swift
import UIKit
import Reteno

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {
  
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        // Reteno initialization
        Reteno.start(apiKey: "SDK_ACCESS_KEY")
      
        // Register for receiving push notifications
        // registerForRemoteNotifications will show the native iOS notification permission prompt
        // Provide UNAuthorizationOptions or use default
        Reteno.userNotificationService.registerForRemoteNotifications(with: [.sound, .alert, .badge], application: application)

        return true
    }
  
    // Remaining contents of your AppDelegate Class...
}
```

##### Method 2: you have AppDelegate.m (or AppDelegate.mm) file

Create `RetenoTransitionLayer.swift` file; Go to your project in Xcode and create new swift file under your target; When system will ask if you want to create bridge file also, agree.

**Note** File locations should looks like on screenshot below.

<Image align="center" width="40% " src="https://files.readme.io/0c1b4476cd6d47074bb0e5fb8288bad0a394e90283e847d50d915ce6505d08d9-file_locations.png" />

After that put next code in your `RetenoTransitionLayer.swift` file:

```swift
import Foundation
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

Then go to `AppDelegate.m` (`AppDelegate.mm`) and modify your code to contain `RetenoTransitionLayer` setup logic

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
/// insert this line
  [RetenoTransitionLayer setupForApplication:application];

  RCTAppSetupPrepareApp(application);

  RCTBridge *bridge = [[RCTBridge alloc] initWithDelegate:self launchOptions:launchOptions];
```

If you get an "Use of undeclared identifier `RetenoTransitionLayer`" error here, it means that you need to create a Bridging header file yourself, here's how to do that:

In Xcode press `File → New → File → Header File`

Save it with `YourProjectName-Bridging-Header.h` name, make sure to replace YourProjectName with your iOS Xcode project name, if we were creating this file for our Reteno example project, we would create it as `RetenoSdkExample-Bridging-Header`, the ".h" extension will be put automatically.

Delete the contents of this file, and replace them with just 1 import

```objectivec
#import <React/RCTBridgeModule.h>
```

Finally, you need to import this header in your AppDelegate header file (AppDelegate.h) as `RetenoSdkExample-Swift.h`

```objectivec
#import "RetenoSdkExample-Swift.h"
```

This is needed in order to use Objective-C and Swift files together in a single project.\
You can read more about <a rel="nofollow" href="https://developer.apple.com/documentation/swift/importing-swift-into-objective-c"> importing swift </a> and <a rel="nofollow" href="https://developer.apple.com/documentation/swift/importing-objective-c-into-swift"> bridging headers </a>, <a rel="nofollow" href="https://reactnative.dev/docs/native-modules-ios#exporting-swift"> react-native docs </a> exporting swift section.

If you get an "No known class method for selector `'setupForApplication:'`" error, or any other "No known class method for selector" error related to `RetenoTransitionLayer`: 

<Image align="center" width="80% " src="https://files.readme.io/57d5610-no_known_class_method_error.png" />

You need to open your Project file, go to `Build Settings`, and in the search bar type: `Swift Compiler` and scroll down until you find `Swift Compiler - General` section.

<Image align="center" width="80% " src="https://files.readme.io/a7ca188-swift_compiler_general_section.png" />

There is a chance that your `Objective-C Bridging Header` might be empty, so you need to specify the name of the bridging header that you're using. Double-click on the right side of this field, and enter the name of YOUR bridging header file, in our example project we will have `RetenoSdkExample-Bridging-Header.h`. Additionally, you can check `Objective-C Generated Interface Header Name` which should be `YourAppName-Swift.h`, in our example project it's `RetenoSdkExample-Swift.h`.

If you get an "Cycle inside ...; building could produce unreliable results" error here, you can try steps below to fix this issue:

Go to your main target -> build phases -> move `[CP] Embed Pods Frameworks` and `Embed Foundation Extensions` to the top of the list. (see screenshot)

<Image align="center" width="80% " src="https://files.readme.io/088000cec69ae628eb6ee3d44d74d4b85dc9d6630a5eacdb34b09a2413f99c84-build_phases.png" />

And that's it, you should be good to go.

### Step 5: Add App Groups

**5.1** In your Main app target got to **"Signing & Capabilities"** > **"All"**

**5.2** Click **"+ Capability"** if you do not have App Groups in your app yet.

<Image align="center" width="80%" src="https://files.readme.io/1cb301e-add_group_main_target.png" />

**5.3**  Select *App Groups*.

<Image align="center" width="80%" src="https://files.readme.io/8fe48ef-app_groups_capability.png" />

**5.4** Under App Groups click the **"+"** button.

**5.5** Fill the **"App Groups"** container as `group.{bundle_id}.reteno-local-storage` where `bundle_id` is the same as **"Bundle Identifier"** off your app (in the main target) and press `OK`.

**5.6** In the `NotificationServiceExtension` target and repeat steps **4.2** - **4.5** for extension target.

<Image align="center" width="80%" src="https://files.readme.io/ac94226-add_group_in_extension.png" />

> 📘 Note
>
> The group name structure should be `group.{bundle_id}.reteno-local-storage` where `bundle_id` is the same as your **Main App target** "Bundle Identifier". **Do Not Include** NotificationServiceExtension.

For more information visit [Configuring App Groups](https://developer.apple.com/documentation/xcode/configuring-app-groups "\{rel='nofollow'}")

### Step 6: Add `Push Notification` Capability to Your Main App Target (not `NotificationServiceExtension`!)

### Step 7: Provide Device Token to the SDK via Next Method:

##### Method 1: you have AppDelegate.swift file

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

##### Method 2: you have AppDelegate.m (or AppDelegate.mm) file

Modify your `AppDelegate.m` (`AppDelegate.mm`) to support `didRegisterForRemoteNotificationsWithDeviceToken` method:

```objectivec
- (void)application:(UIApplication *)application didRegisterForRemoteNotificationsWithDeviceToken:(NSData *)deviceToken {
  [RetenoTransitionLayer processRemoteNotificationsTokenWithDeviceToken:deviceToken];
}
```

If you use `Firebase` for Remote notifications it should be done using `FIRMessagingDelegate`:

Modify your `AppDelegate.m`'s (`AppDelegate.mm`'s) `didFinishLaunchingWithOptions` method:

```objectivec
#import <React/RCTBridgeDelegate.h>
#import <UIKit/UIKit.h>
#import "RetenoSdkExample-Swift.h"
// add this
#import <FirebaseMessaging/FirebaseMessaging.h>

// modify this and add FIRMessagingDelegate
@interface AppDelegate : UIResponder <UIApplicationDelegate, RCTBridgeDelegate, FIRMessagingDelegate>

@property (nonatomic, strong) UIWindow *window;

@end
```

Modify your `AppDelegate.m`'s `didFinishLaunchingWithOptions` method:

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
  [FIRApp configure];
  [FIRMessaging messaging].delegate = self;
  
  [RetenoTransitionLayer setupForApplication:application];
  ...
```

Add to `AppDelegate.m` (`AppDelegate.mm`) `didReceiveRegistrationToken` method and call `RetenoTransitionLayer.processRemoteNotificationsTokenWithFCMToken` in it like this:

```objectivec
- (void)messaging:(FIRMessaging *)messaging didReceiveRegistrationToken:(nullable NSString *)fcmToken {
  [RetenoTransitionLayer processRemoteNotificationsTokenWithFCMToken:fcmToken];
}
```

### Step 8: Run Your App and Send Yourself a Notification

Run your app on a physical iOS device or  iOS simulator to make sure it builds correctly. You should be prompted to subscribe to push notifications.

> 📘 Note
>
> [iOS Debug Mode](https://docs.yespo.io/reference/ios-debug-mode) enables you to ensure that all events and user properties are logged correctly.
