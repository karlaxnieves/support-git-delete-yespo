---
title: Adding New Contacts
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adding New Contacts | Yespo Guide
  description: >-
    Add new contacts via JSON data streaming using the Public API. Read more in
    the instructions.
  robots: index
next:
  description: ''
---
To add a new contact use data streaming in JSON format via Public API.

Use the [Add Contact](https://docs.yespo.io/reference/addcontact-1) method to create the user's profile to an account or update an existing one.

> 📘 Note
> 
> - This method doesn't generate [events](https://docs.yespo.io/docs/events-and-behaviour-tracking), so you won't use it to launch workflows.
> - Using the specified methods, contacts with email addresses will be created as confirmed, as [imported from a file](https://docs.yespo.io/docs/file-uploading). It doesn't allow [configuring double opt-in](https://docs.yespo.io/docs/subscription-form-configuration).
> - If you want to store some custom information about your users, create [additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) before uploading contacts.
> - For adding/updating bulk of contacts use the [Add Contacts](https://docs.yespo.io/reference/contactsbulkupdate-1) method. This resource allows adding/updating up to 3000 contacts with one request.

## JSON sample of request body

For this API method, you must pass channels; other fields are optional. Format and description of all fields are available [here](https://docs.yespo.io/reference/addcontact-1).

```json
{
    "firstName": "John",
    "lastName": "Smith",
    "channels": [
        {
            "type": "mobilepush",
            "value": "8900-7654-6456-9876-0012",
            "device": {
                "appId": "83b77a49-fc28-409b-aeaa-68c9d544ab9d",
                "deviceModel": "iPhone 13",
                "os": "Android",
                "locale": "uk-UA",
                "clientVersion": "native",
                "appVersion": "4.1.7",
                "active": true
            }
        },
        {
            "type": "email",
            "value": "john.contact@gmail.com"
        }
    ],
    "fields": [
        {
            "id": 12345,
            "value": "writer"
        },
        {
            "id": 12346,
            "value": "1990-03-09"
        }
    ]
}
```

## Validation of Contacts' Names and Last Names

Yespo validates contact data received through the API according to the following rules:

### First Name

The maximum field value length is 40 characters.

Letters of any alphabet (unicode) and up to 3 digits are allowed.

Special characters are prohibited, except:

- apostrophes in the middle of a word
- hyphens in the middle of a word or between words without spaces
- a dot at the end of a short (up to 3 characters) word (for example, Jr.)

It is allowed to use 3 words of more than 3 characters and 3 words of a maximum of 3 characters. Names exclusively composed of numbers and/or special characters are prohibited.

### Last Name

The validation rules of the Last name field are the same as for the `First name`, except that any number of words of any length are allowed (but not more than 40 characters in total).