---
title: Uploading Your Mobile Token Base
excerpt: >-
  Before launching a campaign, you must add information about your users to
  Yespo.
deprecated: false
hidden: false
metadata:
  title: Uploading Your Mobile Token Base | Yespo Guide
  description: Guide to exporting mobile tokens to the Yespo system via the Public API
  robots: index
next:
  description: ''
---
To configure the sending of mobile push notifications through the Yespo, it’s necessary to export the existing mobile token database in `JSON` format to our system via [Public API](https://docs.yespo.io/reference/integrating-your-app-with-yespo).

## How to Upload Mobile Token

The [Add contacts](https://docs.yespo.io/reference/contactsbulkupdate-1) method allows for creating new contacts to an account or updating existing ones. ​​You can add/update up to 3000 contacts with one request.

> 📘 Note
>
> * This method automatically generates [events](https://docs.yespo.io/docs/events-and-behaviour-tracking) for new contacts but will not run a workflow for updated or existing contacts.
> * Contacts with email addresses will be created as confirmed, as [imported from a file](https://docs.yespo.io/docs/file-uploading); however, it doesn't allow configuring double opt-in.
> * If you want to store some custom information about your users, create [additional fields](https://docs.yespo.io/docs/usage-of-additional-fields) before uploading contacts.
> * For adding/updating one contact, use the [Add Contact](https://docs.yespo.io/docs/adding-new-users) method. This resource allows to create a user's profile or update an existing one.
> * Upload your contact list with external user ID as the main identifier.

## JSON sample for channel

For this API method, you must pass the required fields `channels` and `dedupeOn`; others are optional. Format and description of all fields are available [here](https://docs.yespo.io/reference/contactsbulkupdate-1).

```json
{
    "contacts":
    [
        {
            "firstName": "John",
            "lastName": "Smith",
            "channels":
            [
                {
                    "type": "mobilepush",
                    "value": "8900-7654-6456-9876-0011",
                    "device":
                    {
                        "appId": "83b77a49-fc28-409b-aeaa-68c9d544ab9d",
                        "deviceModel": "iPhone 13",
                        "os": "Android",
                        "locale": "ua",
                        "appVersion": "4.1.6"
                    }
                },
                {
                    "type": "email",
                    "value": "tgsh@gmail.com"
                }
            ],
            "externalCustomerId": "6add3c31-3ec6-4f34-b20e-8c757fe65270",
            "fields":
            [
                {
                    "id": 12345,
                    "value": "writer"
                },
                {
                    "id": 12346,
                    "value": "1814-03-09"
                }
            ]
        }
    ],
    "dedupeOn": "externalCustomerId",
    "contactFields":
    [
        "firstName",
        "lastName",
        "email",
        "mobilepush",
        "externalCustomerId"
    ],
    "customFieldsIDs":
    [
        12345,
        12346
    ]
}
```
