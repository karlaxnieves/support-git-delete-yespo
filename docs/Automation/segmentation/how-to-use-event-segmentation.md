---
title: Segmentation by User Events
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Segmentation by User Events | Yespo Guide
  description: >-
    Build contact segments based on type and number of events as well as on
    event parameters. Such segmentation will help deliver more personalized
    content and offers for each subscriber.
  robots: index
next:
  description: ''
---
An [event](https://docs.yespo.io/docs/creating-events) is any event on a website/in a mobile app that has a date, type, and a set of mandatory and optional parameters.

Examples of such events are:

- orders;
- abandoned browses;
- abandoned carts;
- new promotions;
- price drop.

Set up segmentation by events so that custom events and their parameters are written to contact cards and can be used to create dynamic segments.

> 📘 Note
> 
> Segmentation by events is available depending on your pricing plan. To activate it, contact to [sales@yespo.io](mailto:sales@yespo.io)

## Event Parameters for Contact Mapping

When using the [Generate event v2 method](https://docs.yespo.io/reference/registerevent_1), a new contact is created, provided [segmentation is enabled for the event](https://docs.yespo.io/docs/how-to-use-event-segmentation#using-events-for-segmentation).

If a contact identifier is found in the event parameters, the system associates it with this contact; if not, it creates a new one. The source for creating such a contact will be recorded as _Event_ in the contact card.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f30d20b7fd2b918f62c33798bbef85034e65c55e1f6b8fef9a38709de6ac8b52-en.webp",
        null,
        "Source"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To save the event assigned to the contact, the event parameter must contain the contact identifier, by which the contact can be found in the Yespo. Also, you need to know which [contact field](https://docs.yespo.io/docs/how-import-and-match-contact-fields-in-the-system) is used as an identifier.

By default, the system connects events with contacts when passing the following parameters:

[block:parameters]
{
  "data": {
    "h-0": "Event parameter",
    "h-1": "Contact field",
    "0-0": "ContactId  \nContact_id",
    "0-1": "Contact ID",
    "1-0": "externalCustomerId",
    "1-1": "External ID",
    "2-0": "Email  \nEmailAddress  \nUserEmail  \nContactEmail",
    "2-1": "Email",
    "3-0": "Phone  \nSMS  \nPhoneNumber",
    "3-1": "Phone number",
    "4-0": "PushToken",
    "4-1": "Web push or mobile push token",
    "5-0": "ContactKey  \nContact_key",
    "5-1": "Additional contact field with the name {ContactKey}"
  },
  "cols": 2,
  "rows": 6,
  "align": [
    "left",
    "left"
  ]
}
[/block]


> 📘 Note
> 
> - Standard parameter names are compared with the passed event parameter names, case insensitive.
> - Parameter values, except the email address, are compared with the passed event parameter values, case sensitive.

Suppose an event has one of the parameters listed in the left column. In that case, Yespo will automatically associate it with the corresponding contact field in the system (right column) when it finds such an identifier.

Here is the event example automatically assigned to the contact:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/34c9edca4629d0e8749b6f7c8bd2dba144d83e39d51800fbaa8387b22387f151-segmentation_user_events_001.webp",
        null,
        "Event example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The event key is `contact_id” : “123abc456ef`. Yespo will assign the event to this contact if such contact exists.

### Checking the event parameters

Select the event type which you will use for segmentation, and check its parameters. Let's look at the _OrderDeliveredRefferal_ example.

1. Go to _Automation → Event history._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2943c85572250665bd3c2323329b1e41edac7d18272837985e23a0d5a2ff5b0e-segmentation_user_events_002.webp",
        null,
        "Event history"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In the _Event type_ drop-down menu, select the `OrderDeliveredRefferal` or search it.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/27504af49890c1f40576a2ca8e8b0098bcf63caf90f324e25463e0dff1c396c2-segmentation_user_events_003.webp",
        null,
        "Selecting event type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click the event name to see the event's parameters and check them with the parameters from the table above. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b433da77a59a103ba5110f0b781d43010e48ca13253ef99f94733d457dad75d-segmentation_user_events_004.webp",
        null,
        "Event parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the example, `email_client` parameter doesn't fit any value from the table. In this case, additional configuration for the `email_client` parameter is required.

[block:parameters]
{
  "data": {
    "h-0": "Event parameter",
    "h-1": "Contact field",
    "0-0": "Email  \nEmailAddress  \nUserEmail  \nContactEmail",
    "0-1": "Email"
  },
  "cols": 2,
  "rows": 1,
  "align": [
    "left",
    "left"
  ]
}
[/block]


### Setting event parameters

Set a matching rule to bind event parameters to a contact ID if you want to use a different event parameter name or a different contact field.

1. Go to _Settings → Events._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7725ecbcfd47422457f1accc8af77b59b02e4e7e7815823ca00d001d57efeba4-events.png",
        null,
        "Setting event parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Activate _Use custom parameter for event assignment_ switcher, select the contact field, and enter the event parameter name.

In the example, the search for a match will go by _Email_ additional field and _email\_client_ event parameter.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af09f55b27b1fc6f561c964561297b86ef4e27bd4b347e78eb30fdc24ab543e6-events_3.png",
        null,
        "Custom parameter for event assignment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Save._

## Using Events for Segmentation

1. Go to _Automation → Event types_ and activate the switcher for the required event type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62d32a9a45b17e18296cfd9ad4b27906b93bbceb2fff3ec12e683890ddd81eb7-segmentation-user-events-00007.webp",
        null,
        "Using events for segmentation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In a pop-up window, click the _Use event for segmentation_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6151b07f44d6b2ecfbe3060e7858442b07dfbd991fdd95ef7ff1b2d1aeb4979c-segmentation_user_events_008.webp",
        null,
        "Use event for segmentation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 🚧 Important
> 
> - Only the events that occur after the feature has been enabled are used for segmentation.
> - You can use up to 50 events for segmentation.

## Adding a Dynamic Segment for Segmentation by Events

1. Go to _Contacts → Segments_. Click the _Add segment_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4403480f19e9cce4019cd3dbcb9c293a2c211b2572e296ed14f1fb2c947eb35e-segmentation_user_events_009.webp",
        null,
        "Adding a dynamic segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Choose the _Dynamic_ segment type and click _Create_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/981cb06183a881c94e8fcbb751b66d1025c542492d9d6e602b84a929d45b6fe3-segmentation_user_events_010.webp",
        null,
        "Dynamic segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Fill in the general properties:

- Segment name: it will be displayed in the general segments’ list.
- Segment purpose: for example, for regular promo campaigns.
- [Tags](https://docs.yespo.io/docs/how-add-tags): to find and filter the segments in the general list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5a5c760bfcf8d69aabfb5a61865d29767ea079f9cb2f51b0016798dd6062f7b7-segmentation_user_events_011_1.webp",
        null,
        "General properties"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the _Next_ button.

4. Click the _Add condition_ button. A new set of fields will appear in the list of conditions after the system receives event. Select the _Custom event → Other_ fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e10c2d6e9ca35ec40a509959a62cc8f6f7db5170fc1fee28e06641a8eef439de-segmentation_user_events_012.webp",
        null,
        "Conditions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- With basic segmentation, you can segment events only by the number and type.
- With advanced segmentation, you can segment by the event parameters.

For example, we need to find everyone who ordered the _Super Device_ brand in London today for more than $ 1,500.

To do this, first, create a card with all the events corresponding to making an order (you can specify other parameters of the number of events: for this, in the _Event count_ condition, specify _equals, greater than, less than_ or the range _between_).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4e80b382a304ed722f0773928e58fb417ef24fb84cd68fecd63cbce3ed233647-image3.webp",
        null,
        "All events"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Card Conditions

We can select the event parameters required for additional filtering by clicking on the three dots in the card.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0b49212b55e58176e1f63842ebf444549a4a35b699531f73e3fd6d2e6e697839-image2.webp",
        null,
        "Select event parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Let's choose the following options:

- brand → Super Brand.
- totalCost →  more than $ 1500
- town → London

The segment card will look like this:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9678aa32d1c72ad7e5d62b45319556d5894b44680d0237591a5ebbc63242c4b8-image1.webp",
        null,
        "Card example"
      ],
      "align": "center",
      "sizing": "50% "
    }
  ]
}
[/block]


Please note: events are selected for today by default. To change the period, click on this word and select a value from the drop-down list:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a07359e2ba6d3c6e569ef6e453a9d814c1fcb92dd509c077d3481e3fc1141c74-image4.webp",
        null,
        "Select period"
      ],
      "align": "center",
      "sizing": "50% "
    }
  ]
}
[/block]


Click _Done_ to save the segment and use it to send promo campaigns or [build workflows](https://docs.yespo.io/docs/introduction-to-workflows).

To create segments based on events that reflect the customer lifecycle stage, use the following conditions:

- **First event** – to identify the user's initial interaction (e.g., subscription, unsubscription, purchase, etc.);
- **Last event** – to understand when they last engaged in the same event.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d76dbbfa87084064036b2cd381878e420e9e52c37524837220ebc9cfc81e800-image004.webp",
        "",
        "First and last event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


 These conditions help you:

- Identify new users (e.g., the first event occurred within the last week, month, or a specific period);
- Find inactive users (e.g., the last event happened a month ago or hasn't occurred within the selected timeframe);
- Analyze returning users (e.g., the first event was a year ago, but a new one occurred last week).

This allows you to clearly distinguish between new and returning users. For example, if a contact was previously subscribed, then unsubscribed, and re-subscribed a few months later, they should not be considered new.