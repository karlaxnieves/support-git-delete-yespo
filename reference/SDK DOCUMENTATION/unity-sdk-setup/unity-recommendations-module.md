---
title: Unity Recommendations
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Unity Recommendations Module | Yespo Guide
  description: >-
    The Recommendations module provides product suggestions based on user
    behavior and context, and allows logging of related events like impressions
    and clicks, with code samples demonstrating how to retrieve and log these
    recommendations.
  robots: index
next:
  description: ''
---
The Recommendations module provides product recommendations based on user behavior and context. It also allows you to log recommendation-related events such as impressions and clicks.

## How It Works

* **GetRecommendations**: Retrieve product recommendations by providing a recommendation variant ID, a list of product IDs, a category ID, filters, and required fields.
* **LogRecommendations**: Log events related to recommendations, such as impressions and clicks.

## Code Samples

### Getting Recommendations

```csharp
using Reteno.Core;
using System;
public class RecommendationExample : MonoBehaviour
{
    void Start()
    {
        // Example inputs for recommendations
        string recomVariantId = "variant_001";
        string[] productIds = { "prod1", "prod2", "prod3" };
        string categoryId = "electronics";
        string filtersJSON = "{\"priceRange\": \"100-500\"}";
        string[] fields = { "name", "price", "availability" };
        // Retrieve recommendations
        RetenoSDK.GetRecommendations(recomVariantId, productIds, categoryId, filtersJSON, fields, (jsonResult, error) =>
        {
            if (string.IsNullOrEmpty(error))
            {
                Debug.Log("Recommendations received: " + jsonResult);
            }
            else
            {
                Debug.LogError("Error fetching recommendations: " + error);
            }
        });
    }
}
```

### Logging Recommendation Events

```csharp
using Reteno.Core;
using Reteno.Core.Recommendations;
using System;
using System.Collections.Generic;
public class LogRecommendationExample : MonoBehaviour
{
    void Start()
    {
        // Create recommendation events
        RecomEvents recomEvents = new RecomEvents
        {
            RecomVariantId = "variant_001",
            RecomEventsList = new List<RecomEvent>
            {
                new RecomEvent
                {
                    RecomEventType = RecomEventType.IMPRESSIONS,
                    Occurred = DateTimeOffset.UtcNow,
                    ProductId = "prod1"
                },
                new RecomEvent
                {
                    RecomEventType = RecomEventType.CLICKS,
                    Occurred = DateTimeOffset.UtcNow,
                    ProductId = "prod2"
                }
            }
        };
        // Log recommendation events
        RetenoSDK.LogRecommendations(recomEvents);
    }
}
```

### Additional Tips:

* Asynchronous Callbacks: Handle the callback from GetRecommendations carefully to update your UI or further process the recommendation data.
* Logging Events: Log both impressions and clicks to analyze user interaction with recommended products.
