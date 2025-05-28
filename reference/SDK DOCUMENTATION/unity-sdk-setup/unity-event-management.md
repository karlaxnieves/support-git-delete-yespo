---
title: Unity Event Management
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Unity Event Management | Yespo Guide
  description: >-
    The Event Management module allows tracking of custom events and screen
    views to provide detailed analytics on user interactions, with
    functionalities like logging events and screen visits demonstrated through a
    C# code example.
  robots: index
next:
  description: ''
---
The Event Management module tracks custom events and screen views, enabling you to gather detailed analytics about user interactions.

## How It Works

* **LogEvent**: Send custom events to the backend.
* **LogScreenView**: Track which screens users visit.

## Code Sample

```csharp
using Reteno.Core;
using Reteno.Events;
using System;
using System.Collections.Generic;
public class EventExample : MonoBehaviour
{
    void Start()
    {
        // Logging a custom event (e.g., purchase event)
        CustomEvent purchaseEvent = new CustomEvent
        {
            EventTypeKey = "purchase_completed",
            OccurredDate = new DateAndTime(DateTime.UtcNow),
            Parameters = new List<Parameter>
            {
                new Parameter { Key = "item_id", Value = "sku12345" },
                new Parameter { Key = "price", Value = "9.99" }
            },
            ForcePush = false
        };
        RetenoSDK.LogEvent(purchaseEvent);
        // Logging a screen view
        RetenoSDK.LogScreenView("HomeScreen");
    }
}
```

### Additional Tips:

* Parameter Use: Use parameters to pass extra details about events.
* Event Types: Create different event types for various user actions for better segmentation and analysis.
