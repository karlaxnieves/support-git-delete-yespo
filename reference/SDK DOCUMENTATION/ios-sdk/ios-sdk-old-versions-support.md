---
title: iOS SDK Old Versions Support
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Manual push notifications setup

For SDK versions **before 1.4.0** use `processRemoteNotificationResponse(_:)` method. Call this method only for opening app action (UNNotificationDefaultActionIdentifier).  

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
        if response.actionIdentifier == UNNotificationDefaultActionIdentifier {
            Reteno.userNotificationService.processOpenedRemoteNotification(response.notification)
        }
        completionHandler()
    }
    
}
```
