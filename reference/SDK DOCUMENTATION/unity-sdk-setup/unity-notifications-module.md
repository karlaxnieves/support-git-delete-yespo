---
title: Unity Notifications
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Unity Notifications Module | Yespo Guide
  description: >-
    The Notifications module manages push notifications in your app by handling
    permission requests and status updates, ensuring synchronization of user
    data and engagement metrics.
  robots: index
next:
  description: ''
---
The Notifications module manages push notifications within your app. It handles permission requests, status updates, and ensures your app can receive push notifications.

## How It Works

The NotificationsManager provides methods to request permissions and update the push notification status. This is important for keeping your user data and engagement metrics in sync.

## Code Sample

```csharp
using Reteno.Core;
public class NotificationExample : MonoBehaviour
{
    void Start()
    {
        // Request push notification permissions
        RetenoSDK.RequestPushPermission(
            onPermissionGranted: () => Debug.Log("Push permission granted."),
            onPermissionDenied: () => Debug.Log("Push permission denied."),
            onPermissionDeniedAndDontAskAgain: () => Debug.Log("Permission denied permanently."),
            onDataReceived: (data) => Debug.Log("Additional data: " + data)
        );
    }
}
```

### Additional Tips:

- Permission Callbacks: Handle each callback to provide proper feedback to the user.
- Data Handling: Use the optional onDataReceived callback to process any additional data returned by the native push service.