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
To integrate a subscription form, use the API resource *[Subscribe contact](https://docs.yespo.io/reference/subscribecontact-1)*.

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

To configure the contact name, add the *firstName* value to the contact field:

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

You can see these events in *Automation → Event history*.

<Image align="center" width="80% " src="https://files.readme.io/d7c836cea225f12ba59ccca7e3031045ac36a34fd9ca642bc80b4ee89d5eb295-integrating-subscription-form-via-api-001.webp" />

## Adding Workflow

Any event can be added to a **workflow**. When an event that is incorporated in a workflow is triggered, the workflow launch begins. For new contacts, it is advisable to send a [subscription confirmation](https://docs.yespo.io/docs/subscription-form-configuration).

To make sure a new contact is created, go to *Contacts → All Contacts*, and enter the necessary email address into the search.

<Image align="center" width="80% " src="https://files.readme.io/db054bd0016e59021083278eee59f32add91f5b9798e2225ad83ead591b789fb-integrating-subscription-form-via-api-002.webp" />

The contact will be found. This means the contact’s email address is inactive and requires confirmation.

<Image align="center" width="80% " src="https://files.readme.io/147c382d10f4f6e767b29efc40b1666f36d822cdddd099c06dfc8e668fa6a82a-integrating-subscription-form-via-api-003.webp" />

You can't send any campaigns to such addresses besides a subscription confirmation email and other transactional emails, for example, an abandoned cart or order confirmation.
