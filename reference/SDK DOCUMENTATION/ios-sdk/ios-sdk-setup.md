---
title: iOS SDK Setup
excerpt: The Reteno iOS SDK for Mobile Customer Engagement and Analytics solutions
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
See the video manual on iOS SDK setup:

<Embed url="https://www.youtube.com/watch?v=T-JboJcQBpw" href="https://www.youtube.com/watch?v=T-JboJcQBpw" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FT-JboJcQBpw%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DT-JboJcQBpw%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FT-JboJcQBpw%252Fhqdefault.jpg%26key%3D02466f963b9b4bb8845a05b53d3235d7%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Overview

`Reteno` is a lightweight SDK for iOS that helps mobile teams integrate Reteno into their mobile apps. The server-side library makes it easy to call the `Reteno API`.

#### The SDK supports:

* Swift projects
* iOS 12.0 or later\
  ​

### Getting Started with Reteno SDK for iOS

Download and install SDK via **CocoaPods**.

[CocoaPods](https://cocoapods.org/ "\{rel='nofollow'}") is a dependency manager for Cocoa projects. For usage and installation instructions, visit their website. To integrate Reteno into your Xcode project using CocoaPods, specify it in your `Podfile`:

```ruby
pod 'Reteno', '2.5.6'
```

> 📘 Note
>
> If you are developing app modules, read the instructions on [installing the SDK via Swift Package Manager](https://docs.yespo.io/reference/ios#installing-the-sdk-via-swift-package-manager)

##### License

`Reteno iOS SDK` is released under the MIT license. See [LICENSE](https://github.com/reteno-com/reteno-mobile-ios-sdk/blob/main/LICENSE "\{rel='nofollow'}") for details.

## Setting Up the SDK

Follow our setup guide to integrate the Reteno SDK with your app.

### Step 1: Add the Notification Service Extension

The `NotificationServiceExtension` allows your iOS application to receive rich notifications with images, design the buttons in notifications, and get message statuses (delivered, clicked).

> 📘 Note
>
> If you already have Notification Service Extension in your app, follow Step 1.6.

**1.1**  In Xcode, *Select File* → *New* → *Target*...

**1.2**  Select *Notification Service Extension* , then press *Next*.

<Image align="center" width="80% " src="https://files.readme.io/2758667-create_notification_service_extension.png" />

**1.3**  Enter the product name as `NotificationServiceExtension` and press *Finish*.

> 📘 Note
>
> Do not select *Activate* on the dialog that is shown after selecting *Finish*.

<Image align="center" width="80% " src="https://files.readme.io/5b8118c-choose_options_for_extension.png" />

**1.4**  Press *Cancel* in the Activate scheme prompt.

By canceling, you keep Xcode debugging your app instead of the extension you’ve just created.

If you activate the prompt by accident, you can switch back to debugging your app in Xcode (next to the Play button).

**1.5**  In the project navigator, select the project directory and select the `NotificationServiceExtension` target in the targets list.

Check that the Deployment Target is set to the same value as your Main Application Target.

> 📘 Note
>
> iOS versions under 10 will not be able to get Rich Media.

<Image align="center" width="80% " src="https://files.readme.io/16595d9-configure_target.png" />

**1.6**  In the project navigator, select the `NotificationServiceExtension` folder and open the `NotificationService.swift`, then replace the entire file contents with the following code. Ignore any build errors at this point. We will import the Reteno module, which will resolve any errors.

```swift
import UserNotifications
import Reteno

class NotificationService: RetenoNotificationServiceExtension {}
```

This gives the ability to allow your iOS application to receive rich notifications with images.

More about the [Modifying Content in Newly Delivered Notifications](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications) Extension

### Step 2: Install the SDK via CocoaPods

**2.1**  If you don't have CocoaPods and the Podfile installed in your project, run the following script in Terminal:\
`sudo gem install cocoapods`

**2.2**  Run `pod init` from the terminal in your project directory.

**2.3**  Open the newly created `Podfile` with your code editor.

**2.4**  Add the `Reteno` dependency under your project name target and the\
`NotificationServiceExtension` target as below:

```swift
platform :ios, '14.0'

target 'RetenoExample' do
  use_frameworks!

  pod 'Reteno'
  
  target 'NotificationServiceExtension' do
    use_frameworks!

    pod 'Reteno'

  end

end
```

**2.5**  Run the following command in your terminal, in your project directory: `pod install`

**2.6**  Open the newly created `<project-name>.xcworkspace` file.

### Step 3: Import Reteno into Your App Delegate File

> 📘
>
> To setup SDK you need an `SDK_ACCESS_KEY`, visit [Managing Mobile SDK Access Keys](https://docs.yespo.io/reference/managing-mobile-sdk-access-keys) to get it.

#### Method 1: UIKit

In  [UIKit](https://developer.apple.com/documentation/uikit), navigate to your AppDelegate file and add the `Reteno` initialization code to the `didFinishLaunchingWithOptions` method.\
Make sure to import the `Reteno` module `import Reteno`

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

#### Method 2: SwiftUI

In SwiftUI, update your main 'APP\_NAME'App.swift file and use the code below. Make sure to replace 'YOURAPP\_NAME' with your app name.

```swift
import SwiftUI
import Reteno

class AppDelegate: NSObject, UIApplicationDelegate {

    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil
    ) -> Bool {
        // Reteno initialization
        Reteno.start(apiKey: "SDK_ACCESS_KEY")

        // Register for receiving push notifications
        // registerForRemoteNotifications will show the native iOS notification permission prompt
        // Provide UNAuthorizationOptions or use default
        Reteno.userNotificationService.registerForRemoteNotifications(with: [.sound, .alert, .badge], application: application)

        return true
    }

}
```

```swift
import SwiftUI
import Reteno

@main
struct YOURAPP_NAME: App {
    @UIApplicationDelegateAdaptor(AppDelegate.self) var appDelegate
    
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

> 📘 Note
>
> Starting from Reteno SDK 2.0.4 onwards, the `start` method was updated. In the previous version, it had the following parameters: `apiKey`, `isAutomaticScreenReportingEnabled`, `isDebugMode`, `isPausedInAppMessages`, `inAppMessagesPauseBehaviour`. In the new version, it now has the following parameters: `apiKey`, `configuration`. `RetenoConfiguration` is a struct containing the previous setups.

### Step 4: Set Up a Notification Permission Request

#### Option 1. Saving existing logic

If you have already configured subscribing for push notifications by yourself and don't want to change an existing logic, but have `Reteno` analytics features, call the `Reteno.userNotificationService.processRemoteNotificationResponse(_:)` SDK method right after you have received user response on the push notification. Pass a UNNotificationResponse as a parameter.

For example, you are using `UNUserNotificationCenterDelegate` for processing incoming notifications and responding to notification actions. Call the SDK method like described below:

```swift
extension AppDelegate: UNUserNotificationCenterDelegate {
    
    func userNotificationCenter(
        _ center: UNUserNotificationCenter,
        willPresent notification: UNNotification,
        withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void
    ) {
        completionHandler([.sound, .badge, .alert])
    }
    
    func userNotificationCenter(
        _ center: UNUserNotificationCenter,
        didReceive response: UNNotificationResponse,
        withCompletionHandler completionHandler: @escaping () -> Void
    ) {
        Reteno.userNotificationService.processRemoteNotificationResponse(response)
        completionHandler()
    }
    
}
```

#### Option 2. Creating new logic

From Reteno SDK 1.5.4 onwards, method `registerForRemoteNotifications` has a closure with user response on notifications permission prompt and you can register for Remote notifications wherever you want. For example, you want to ask a user permissions for Remote notifications only after they have completed onboarding.

```swift
func onboardingCompleted() {
    Reteno.userNotificationService.registerForRemoteNotifications(with: [.sound, .alert, .badge]) { granted in
        // granted == true if user allowed receiving Remote notifications
    }
}
```

[Old SDK versions support >](https://docs.yespo.io/reference/ios-sdk-old-versions-support)

### Step 5: Add App Groups

App Groups allow additional interposes communication between the app and notification service and are necessary to provide access to Reteno storage data.

**5.1**  In your Main app target got to *"Signing & Capabilities"* → *"All"*

**5.2**  Click *"+ Capability"* if you do not have App Groups in your app yet.

<Image align="center" width="80% " src="https://files.readme.io/67d7ac3-add_group_main_target.png" />

**5.3**  Select App Groups.

<Image align="center" width="80% " src="https://files.readme.io/fc76751-app_groups_capability.png" />

**5.4**  Under App Groups, click the *"+"* button.

**5.5**  Fill the *"App Groups"* container with `group.{bundle_id}.reteno-local-storage`, where `bundle_id` is the same as *"Bundle Identifier"* off your app (in the main target), then press `OK`.

**5.6**  In the `NotificationServiceExtension` target, repeat steps **5.2** - **5.5** for the extension target.

<Image align="center" width="80% " src="https://files.readme.io/69cfe0a-add_group_in_extension.png" />

> 📘 Note
>
> The group name structure must be `group.{bundle_id}.reteno-local-storage`, where `bundle_id` is the same as your **Main App target** "Bundle Identifier". **Do Not Include** NotificationServiceExtension.

For more information, visit [Configuring App Groups](https://developer.apple.com/documentation/xcode/configuring-app-groups)

### Step 6: Provide Device Tokens to the SDK via the Following Method:

```swift
Reteno.userNotificationService.processRemoteNotificationsToken(_ deviceToken: String)
```

> 📘 Note
>
> Providing device token depends on how you send push notifications: via **[Firebase Cloud Messaging (FCM)](https://docs.reteno.com/docs/connect-your-mobile-app#for-all-devices)** or directly to **[APNs](https://docs.reteno.com/docs/connect-your-mobile-app#only-for-ios-devices-apple)**

**Option 1.** If you send push notifications via **Firebase Cloud Messaging (FCM)** include a call to `Reteno` `processRemoteNotificationsToken:` in your `MessagingDelegate` delegate as follows:

```swift
extension AppDelegate: MessagingDelegate {
    
    func messaging(_ messaging: Messaging, didReceiveRegistrationToken fcmToken: String?) {
        guard let fcmToken = fcmToken else { return }
        
        Reteno.userNotificationService.processRemoteNotificationsToken(fcmToken)
    }
    
}
```

**Option 2**. In case sending push notifications directly to **APNs** include a call to `Reteno` in the AppDelegate method like in the example below:

```swift
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
        let tokenString = deviceToken.map { String(format: "%02.2hhx", $0) }.joined()
        Reteno.userNotificationService.processRemoteNotificationsToken(tokenString)
    }
```

> 📘 Note
>
> Device token data should be converted to `String` as in the example. Don't send this token if you are using Firebase Cloud Messaging (FCM).

### Step 7: Add Custom Behavior for Notifications

If you want to add custom behavior in the `UNUserNotificationCenterDelegate` methods, provide your implementation in the appropriate closure:

```swift
Reteno.userNotificationService.willPresentNotificationHandler = { notification in
    // The closure will be called only if the application is in the foreground. 
    // You can choose to have the notification presented as a sound, badge, alert and/or in the notification list.
    // This decision should be based on whether the information in the notification is otherwise visible to the user.

    let authOptions: UNNotificationPresentationOptions
    if #available(iOS 14.0, *) {
        authOptions = [.badge, .sound, .banner]
    } else {
        authOptions = [.badge, .sound, .alert]
    }
    return authOptions
}
```

```swift
Reteno.userNotificationService.didReceiveNotificationResponseHandler = { notification in
    // Add your code here.
    // The closure will be called when the user responded to the notification by opening the application, 
    // dismissing the notification or choosing a UNNotificationAction.
}
```

Do it after configuring the Reteno SDK.

### Step 8: Run Your App and Send Yourself a Notification

Run your app on a physical iOS device to make sure it builds correctly. You should be prompted to subscribe to push notifications. Send test notifications not from the Firebase but directly from the Yespo. [More on sending test messages from the event debug view >](https://docs.yespo.io/docs/sending-test-messages-from-the-event-debug-view)

> 📘 Note
>
> The iOS Simulator does not support receiving remote push notifications.

Also, we recommend using [Debug Mode](https://docs.yespo.io/reference/ios-debug-mode) to detect possible errors and inaccuracies within your Analytics implementation and events' logging.

## Installing the SDK via Swift Package Manager

The [Swift Package Manager](https://swift.org/package-manager/ "\{rel='nofollow'}") is a tool for automating the distribution of Swift code and is integrated into the `swift` compiler.\
​
Once you have your Swift package set up, adding Reteno as a dependency is as easy as adding it to the `dependencies` value of your `Package.swift`.

```swift
dependencies: [
    .package(url: "https://github.com/reteno-com/reteno-mobile-ios-sdk.git", .upToNextMajor(from: "2.5.6"))
]
```

**Installation process:**

**1.** Go to the project settings and select `Package Dependencies`:

<Image align="center" width="80% " src="https://files.readme.io/54bd62b-package_dependencies.png" />

**2.** Press "**+**" to add a new package to the project. In the opened window enter in a search field `reteno-ios-sdk` or paste a full URL `https://github.com/reteno-com/reteno-mobile-ios-sdk.git`. Select found package and fill required settings (dependency rule and project you are adding package).

<Image align="center" width="80% " src="https://files.readme.io/dca0783-search_for_package.png" />

**3.** Add the `Reteno` package to the main target

<Image align="center" width="80% " src="https://files.readme.io/da80795-connect_package_1.png" />

and don't forget to add it to the `NotificationServiceExtension`.

<Image align="center" width="80% " src="https://files.readme.io/3dcb3c3-connect_package_to_extension.png" />