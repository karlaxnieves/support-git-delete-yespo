---
title: Naming Custom Events
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Naming Custom Events | Yespo Guide
  description: >-
    Find out how to set up convenient and informative naming of custom events
    and their parameters at the start
  robots: index
next:
  description: ''
---
Set up standard naming for your custom events and their parameters from the beginning of working with Yespo. This will make your code easier to interpret so anyone on your team can easily understand what each event means.

## What Is Standardized Naming

Standardizing naming is following certain rules when naming events and their parameters sent from your side to other platforms. Standardized names will streamline analytics and simplify tracking setup.

## Benefits of Standardized Naming

With standardized naming, your data will be consistent and convenient to use and understand:

- **Unification.** When all data types and events have consistent names across all platforms, it simplifies their utilization.
- **Usability.** As your business grows, you will need to keep track of more and more new events. Standardized naming will simplify the implementation of their transferring and save time for your developers.
- **Transparency.** Different teams work with the same data: developers, marketers, analysts, etc. Standardized names make it easy for everyone to understand an event and its parameters for further analysis, experimentation, and other actions.

## ObjectAction Scheme

Without clear and standard rules for events’ naming, your analytics will become increasingly confusing and unclear. For example, when a user logs in to your site, you can send this event as _Log in_, _Login_ or _User logged in_.

To avoid such problems and use all data effectively, create a standard naming scheme and stick to it when creating all events and their parameters.

We recommend creating events’ names from two parts: objects and actions related to them. For example, _CartAbandoned_ or _ProductViewed_.

Use verbs in the past tense to underline that events created after actions happened.

The _ObjectAction_ scheme of events’ naming will help you

- To build a funnel for analyzing interactions with particular features of your site: you will see object-related actions in alphabetical order.
- To easily find events in the event history.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ee905004c0fd738704783ab42442829fecdf4544eac5aaef7e856f8f17eaa03c-2.webp",
        "Event history",
        "Event history"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- To ensure an understanding of what events are recorded in analytics: it’s obvious that an event called _ProductAddedToWishlist_ means a contact added product to a wishlist.

## Event Parameters

The more parameters you send in an event, the bigger picture of the interaction with your brand you get. For example, you can transfer in _ProductPurchased_ event the total cost and cost of each item, discount value, product description, delivery method, etc.

Create a list of standard parameters for all events. For example, for the _CartAbandoned_ and _ProductViewed_ events, you must collect parameters such as _productId_, _productName_, _productDescription_, _productCost_, and so on.

Standardized event parameters will allow you to build [dynamic segments](https://docs.yespo.io/docs/how-add-dynamic-segment) based on contact behavior on your site for marketing analytics and target campaigns.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/845e5c28d34d5524388d7146b517db84e28de85275111003c8dcb7170710c5fd-creating-dynamic-segment-10.webp",
        "Dynamic segment creation",
        "Dynamic segment creation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## CamelCase Format

Use exceptional _CamelCase_ format:

- Write the event name by capitalizing the first letter of each word and not using spaces, underlines, and other special characters: **ProductPurchased**.
- Write the parameter name by making the first letter of the first word lowercase and every subsequent word capitalized, not using spaces, underlines, and other special characters: **imageUrl**.

## List of Standard Events and Parameters

| Event name       | Parameters                                                                                     |
| :--------------- | :--------------------------------------------------------------------------------------------- |
| `CartAbandoned`  | `productName`, `productPrice`, `productUrl`, `imageUrl`, `brand`, `tagsWeight`, `tagsOldPrice` |
| `ContactCreated` | `externalCustomerId`, `email`, `phone`, `token`                                                |

> 📘 Note
> 
> All events should include standard information about devices and contacts

[More on launching event tracking >](https://docs.yespo.io/docs/events-and-behaviour-tracking)