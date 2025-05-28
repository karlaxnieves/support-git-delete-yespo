---
title: Add/Update a Contact Request Example
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Add/Update a Contact Request Example | Yespo Guide
  description: >-
    Learn about using a Backend API for regularly updating contact information,
    including personal details, communication channels, address, custom fields,
    and group memberships.
  robots: index
next:
  description: ''
---
We recommend regularly updating contacts by Backend API (server-to-server). Request example:

```json
{  
  "firstName": "John",  
  "lastName": "Smith",  
  "channels": [  
    {  
      "type": "email",  
      "value": "john.smith@example.com"  
    },  
    {  
      "type": "sms",  
      "value": "+1234567890"  
    },  
    {  
      "type": "webPush",  
      "value": "subscription-id-12345"  
    }  
  ],  
  "address": {  
    "city": "New York",  
    "region": "NY",  
    "country": "US",  
    "postalCode": "10001",  
    "addressLine": "123 Main Street"  
  },  
  "fields": [  
    {  
      "name": "birthDate",  
      "value": "1990-01-01"  
    },  
    {  
      "name": "loyaltyLevel",  
      "value": "Gold"  
    }  
  ],  
  "externalCustomerId": "EM12790",  
  "groups": [  
    {  
      "id": 1001,  
      "name": "Newsletter Subscribers"  
    }  
  ],  
  "languageCode": "en",  
  "timeZone": "America/New_York"  
}
```

## Explanation of Fields:

1. `firstName`:

   * Value: `"John"`
   * The contact's first name.

2. `lastName`:
   * Value: `"Smith"`
   * The contact's last name.

3. `channels`:
   * An array specifying the contact's communication channels. Each channel includes:
     * `type`: The channel type (e.g., `"email"`, `"sms"`, `"webPush"`).
     * `value`: The identifier for the channel (e.g., email address, phone number).

4. `address`:
   * Contains the contact's full address details:
     * `city`, `region`, `country`, `postalCode`, and `addressLine`.

5. `fields`:
   * An array of custom fields containing additional information about the contact:
     * Example: `"birthDate"` and `"loyaltyLevel"`.

6. `externalCustomerId`:
   * Value: `"EM12790"`
   * Your system's unique identifier for the contact.

7. `groups`:
   * An array of static segments (groups) the contact belongs to. 
   * Example: `"Newsletter Subscribers"`.

8. `languageCode`:
   * Value: `"en"`
   * The contact's preferred language.

9. `timeZone`:
   * Value: `"America/New_York"`
   * The contact's time zone.

> 📘 Note
>
> We strongly recommend [using your External ID](https://docs.yespo.io/docs/external-id-creating-and-updating-users) as the main identifier to match the contact data in our system.
