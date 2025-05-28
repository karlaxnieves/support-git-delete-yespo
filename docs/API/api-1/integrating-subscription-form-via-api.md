---
title: Integrating Subscription Form via API
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Integrating Subscription Form via API | Yespo Guide
  description: >-
    The document explains how to integrate a subscription form via the
    "Subscribe contact" API: add contacts, configure names, assign segments,
    generate events, manage workflows, and confirm contacts.
  robots: index
next:
  description: ''
---
To integrate a subscription form, use the API resource _[Subscribe contact](https://docs.yespo.io/reference/subscribecontact-1)_.

## Request Body

The standard request body looks as follows:

```json
{
"contact" : {
"channels" : [ {
"type" : "email",
"value" : "test@mail.com"
} ]
}
}
```

After a resource call, one contact with the email address `test@mail.com` will be added to the system.

To configure the contact name, add the _firstName_ value to the contact field:

```json
{
"contact" : {
"firstName" : "...",
"channels" : [ {
"type" : "email",
"value" : "test@mail.com"
} ]
}
}
```

To specify the segments where the subscribed contact will be added, add to the request the groups field - the string array, segment names. If the specified segments don’t exist in the system, they will be created automatically:

```json
{
"contact" : {
"firstName" : "...",
"channels" : [ {
"type" : "email",
"value" : "test@mail.com"
} ]
},
"groups" : [ "Subscribers" ]
}
```

## Generating Events

Once this resource is called, the system automatically generates one of two events:

1. **subscribeFromAPI** if a new contact has been created;

2. **subscribeUpdateFromAPI** — if such a contact exists.

You can see these events in _Automation → Event history_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d7c836cea225f12ba59ccca7e3031045ac36a34fd9ca642bc80b4ee89d5eb295-integrating-subscription-form-via-api-001.webp",
        "Event history",
        "Event history"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Adding Workflow

Any event can be added to a **workflow**. When an event that is incorporated in a workflow is triggered, the workflow launch begins. For new contacts, it is advisable to send a [subscription confirmation](https://docs.yespo.io/docs/subscription-form-configuration).

To make sure a new contact is created, go to _Contacts → All Contacts_, and enter the necessary email address into the search.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db054bd0016e59021083278eee59f32add91f5b9798e2225ad83ead591b789fb-integrating-subscription-form-via-api-002.webp",
        "All contacts",
        "All contacts"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The contact will be found. This means the contact’s email address is inactive and requires confirmation.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/147c382d10f4f6e767b29efc40b1666f36d822cdddd099c06dfc8e668fa6a82a-integrating-subscription-form-via-api-003.webp",
        "Inactive contact is highlighted in gray",
        "Inactive contact is highlighted in gray"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can't send any campaigns to such addresses besides a subscription confirmation email and other transactional emails, for example, an abandoned cart or order confirmation.