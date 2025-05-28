---
title: Unity Push Handling
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Unity Push Handling | Yespo Guide
  description: >-
    Discover how to trigger logic with user interaction on notifications using
    the OnNotificationClicked method in the Reteno SDK within a Unity
    environment.
  robots: index
next:
  description: ''
---
## Get Initial Notification

To run a logic after user click on notification, use the `OnNotificationClicked` method.

```csharp
using System;
using RetenoSdk;

public class YourClass : MonoBehaviour
{
    void OnApplicationFocus(bool hasFocus)
    {
        RetenoSdk.OnNotificationClicked();
    }
}
```