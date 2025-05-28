---
title: Naming Custom Events
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Naming Custom Events | Support
  description: >-
    See how to make event naming consistent, transparence and easy for
    understanding
  robots: index
next:
  description: ''
---
Set up standard naming for your custom events and their parameters from the beginning of working with eSputnik. This will make your code easier to interpret so anyone on your team can easily understand what each event means.

## What Is Standardized Naming

Standardizing naming is following certain rules when naming events and their parameters sent from your side to other platforms. Standardized names will streamline analytics and simplify tracking setup.

## Benefits of Standardized Naming

With standardized naming, your data will be consistent and convenient to use and understand:

- **Unification.** When all data types and events have consistent names across all platforms, it simplifies their utilization.
- **Usability.** As your business grows, you will need to keep track of more and more new events. Standardized naming will simplify the implementation of their transferring and save time for your developers.
- **Transparency.** Different teams work with the same data: developers, marketers, analysts, etc. Standardized names make it easy for everyone to understand an event and its parameters for further analysis, experimentation, and other actions.

## ObjectAction Scheme

Without clear and standard rules for events’ naming, your analytics will become increasingly confusing and unclear. For example, when a user logs in to your site, you can send this event as `Log in`, `Login` or `User logged in`.

To avoid such problems and use all data effectively, create a standard naming scheme and stick to it when creating all events and their parameters.

We recommend creating events’ names from two parts: objects and actions related to them. For example, `CartAbandoned` or `ProductViewed`.

Use verbs in the past tense to underline that events created after actions happened.

The `ObjectAction` scheme of events’ naming will help you

- To build a funnel for analyzing interactions with particular features of your site: you will see object-related actions in alphabetical order.
- To easily find events in the event history.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/790b692-Event_naming_1.png",
        "",
        "Event history"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- To ensure an understanding of what events are recorded in analytics: it’s obvious that an event called `ProductAddedToWishlist` means a contact added product to a wishlist.

## Event Parameters

The more parameters you send in an event, the bigger picture of the interaction with your brand you get. For example, you can transfer in `ProductPurchased` event the total cost and cost of each item, discount value, product description, delivery method, etc.

Create a list of standard parameters for all events. For example, for the `CartAbandoned` and `ProductViewd` events, you must collect parameters such as `productId`, `productName`, `productDescription`, `productCost`, and so on.

Standardized event parameters will allow you [to build dynamic segments](https://docs.yespo.io/docs/creating-dynamic-segment) based on contact behavior on your site for marketing analytics and target campaigns.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3de5949-Event_naming_2.gif",
        "",
        "Dynamic segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## `CamelCase` Format

Use exceptional `CamelCase` format:

- Write the event name by capitalizing the first letter of each word and not using spaces, underlines, and other special characters: **`ProductPurchased`**.
- Write the parameter name by making the first letter of the first word lowercase and every subsequent word capitalized, not using spaces, underlines, and other special characters: **`imageUrl`**.

## List of Standard Events and Parameters

| Event name       | Parameters                                                                                     |
| :--------------- | :--------------------------------------------------------------------------------------------- |
| `CartAbandoned`  | `productName`, `productPrice`, `productUrl`, `imageUrl`, `brand`, `tagsWeight`, `tagsOldprice` |
| `ContactCreated` | `externalCustomerId`, `email`, `phone`, `token`                                                |

> 📘 Note
> 
> All events should include standard information about devices and contacts

[More on launching event tracking >](https://docs.yespo.io/reference/integrating-your-app-with-reteno#3-launch-event-tracking)