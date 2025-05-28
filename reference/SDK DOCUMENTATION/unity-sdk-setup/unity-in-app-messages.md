---
title: Unity In-App Messages
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: In-App Messages | Yespo Guide
  description: >-
    The In-App Messages module allows you to manage in-app messaging by pausing
    them or adjusting their behavior based on app context, with options to skip
    or postpone messages.
  robots: index
next:
  description: ''
---
The In-App Messages module allows you to manage and configure the behavior of in-app messages. You can pause messages entirely or adjust their behavior based on your app’s context.

## How It Works

* **Pause In-App Messages**: Temporarily disable in-app messaging.
* **Set In-App Messages Pause Behaviour**: Specify whether messages should be skipped or postponed.

## Code Sample

```csharp
using Reteno.Core;
public class InAppExample : MonoBehaviour
{
    void Start()
    {
        // Pause all in-app messages
        RetenoSDK.PauseInAppMessages(true);
        // Optionally, set a specific pause behavior (e.g., skip or postpone)
        RetenoSDK.SetInAppMessagesPauseBehaviour(Reteno.InAppMessages.InAppPauseBehaviour.POSTPONE_IN_APPS);
    }
}
```

### Additional Tips:

* Dynamic Control: You can pause and resume in-app messages based on user actions or app state.
* User Experience: Adjust the pause behavior to avoid interrupting the user experience during critical moments.
