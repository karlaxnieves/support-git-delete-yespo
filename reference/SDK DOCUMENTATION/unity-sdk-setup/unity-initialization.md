---
title: Unity Initialization
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Unity Initialization | Yespo Guide
  description: >-
    The document explains how to initialize and configure the Reteno SDK in an
    app, emphasizing the importance of early initialization and offering a code
    sample for setting up the SDK with customizable configurations.
  robots: index
next:
  description: ''
---
This module initializes the Reteno SDK and configures its behavior based on your needs.

## How It Works

The `RetenoSDK.Initialize` method must be called as early as possible in your app’s lifecycle. It sets up the platform-specific components (such as notifications, user management, events, etc.) using the provided app ID and optional configuration.

## Code Sample

```csharp
using Reteno.Core;
using Reteno.Core.Initialization;
public class AppInitializer : MonoBehaviour
{
    void Start()
    {
        // Optional: Configure SDK behavior
        RetenoConfiguration config = new RetenoConfiguration(
            isAutomaticScreenReportingEnabled: true,
            isAutomaticAppLifecycleReportingEnabled: true,
            isAutomaticPushSubscriptionReportingEnabled: true,
            isAutomaticSessionReportingEnabled: true,
            isPausedInAppMessages: false,
            inAppMessagesPauseBehaviour: 0,
            isDebugMode: true,
            pushNotificationProvider: PushNotificationProvider.Fcm
        );
        // Initialize the SDK with your App ID and configuration
        RetenoSDK.Initialize("your_access_key", config);
    }
}
```

### Additional Tips:

* Early Initialization: Ensure that RetenoSDK.Initialize is called before any other SDK methods.
* Custom Configuration: Customize the RetenoConfiguration to fit your app’s requirements.
* Debug Mode: Enabling debug mode can help during development by providing detailed logs.
