---
title: iOS SDK In-App Status Handler
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: iOS SDK In-App Status Handler | Yespo Guide
  description: Find out how to get In-App statuses of messages.
  robots: index
next:
  description: ''
---
You can detect In-App presenting status where needed.

From Reteno SDK 2.0.1 onwards, you can add a handler that provides In-App presenting status

```swift
Reteno.addInAppStatusHandler { [weak self] inAppMessageStatus in
    switch inAppMessageStatus {
    case .inAppShouldBeDisplayed:
        // called when the in-app should be displayed
                
    case .inAppIsDisplayed:
        // called when the in-app is displayed
                
    case .inAppShouldBeClosed(let action):
        // called when the in-app should be closed
        // also can be 
            
    case .inAppIsClosed(let action):
        // called when the in-app is closed

    case .inAppReceivedError(let error):
        // called when the in-app can't be shown for some reason.
    }
}
```
