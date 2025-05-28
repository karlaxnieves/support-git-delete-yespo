---
title: Mapping Events with Contacts by External IDs
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Mapping Events with Contacts by External IDs | Yespo Guide
  description: >-
    Read how to use External ID. Utilizing External IDs prevents the duplication
    of contacts, consolidates all accessible data into unified profiles, and
    provides comprehensive insights into contacts’ interactions with your brand.
  robots: index
next:
  description: ''
---
The system automatically links events to user with the help of an event parameter that contains user identifier. If user ID is not specified in the event, the system searches the _ContactId_ event parameter by default.

If you pass the identifier in the _External ID_ field to the event, you do not need to configure the mapping additionally. But if this ID is passed in a field with a different name, it must be correlated with the _External ID_ system field.

## What is the External ID

The external ID is a [unique contact identifier](https://docs.yespo.io/docs/customer-identifiers-and-matching) generated in your system. To learn more about external IDs, please read [the following article](https://docs.yespo.io/docs/external-id-creating-and-updating-users).

## Why Use External IDs

Utilizing External IDs prevents the duplication of contacts, consolidates all accessible data into unified profiles, and provides comprehensive insights into contacts’ interactions with your brand. All these benefits are crucial for the accuracy of the [segmentation by events](https://docs.yespo.io/docs/how-to-use-event-segmentation).

Check out [5 best segmentation practices](https://yespo.io/blog/advanced-segmentation-marketing-automation-applications-and-examples) showing you how to use event data to increase your business efficiency.

## Mapping Settings

1. Go to your account _Settings_ → _Events_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ed1cfc056b0763fb291d73493037eb041ef5e16cdf9253e0a1d00d73268172bd-events.png",
        "",
        "Events"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enable _Use custom parameter for event assignment_ switcher. Set your parameter name and select the _External ID_ contact field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e92a05d982ffe6f34275e854c6f5c923c925dd2dd38319901625b5a928a6f1ef-events_2.png",
        "",
        "Custom parameter for event assignment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Save_.