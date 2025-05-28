---
title: AbandonedCart Event Example
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: AbandonedCart Event Example | eSputnik Guide
  description: See the example of AbandonedCart request
  robots: index
next:
  description: ''
---
Events sent via Backend API typically involve sensitive data or require server-side validation and processing. Let's see the `AbandonedCart` event as an example:

```json
{
    "eventTypeKey": "AbandonedCart",
    "params":
    [
        {
            "name": "externalCustomerId",
            "value": "fb63c4a3-e684-45e1-ba0a-84b139e5e419"
        },
        {
            "name": "cartId",
            "value": "CART12345"
        },
        {
            "name": "totalValue",
            "value": 250.75
        },
        {
            "name": "currency",
            "value": "USD"
        },
        {
            "name": "itemCount",
            "value": 3
        }
    ]
}
```

## Explanation of the Request

1. `eventTypeKey` : `"AbandonedCart"`

   * Indicates the type of event being generated.

2. `params` : An array of objects with `name` and `value` pairs.

   * `externalCustomerId`: Unique customer identifier.
   * `cartId`: A unique identifier for the abandoned cart.
   * `totalValue`: The total value of items in the cart.
   * `currency`: The currency for the cart's value.
   * `itemCount`: Number of items in the cart.

This request can be sent via the **Generate Event API** to track user subscription activities, trigger workflows, and personalize messages based on event data.
