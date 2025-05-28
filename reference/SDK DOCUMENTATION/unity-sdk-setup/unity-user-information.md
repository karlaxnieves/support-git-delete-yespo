---
title: Unity User Information
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Tracking User Information

After you install the SDK to your app, Reteno begins automatically collect such data:

* Information about push message delivery and openings,
* Users’ push tokens,
* Screen view events,
* Statuses of the users’ subscription to push notifications. 

Reteno automatically creates user profiles with all these data, so you can immediately start working with new contacts, for example, sending them a mobile campaign.

## External User ID

When the user logs in or signs up to your app, you have to define a unique customer identifier that cannot be shared by other contacts. We call it External User Id or just User Id. The system will match all previous data with an external ID as the primary identifier and update the user’s profile.

[Read more about system customer identifiers and their matching in the system >](https://yespo.io/support/customer-identifiers-and-matching)

## User Attributes

User attributes are attributes you define to describe segments of your user base, such as language preference or geographic location.

Add your custom External User Id and user attributes like **phone**, **email**, etc by the following method:

```C#
RetenoSDK.SetUserAttributes(string externalUserId, User user);
```

> 📘 Note
>
> ExternalUserId must not be null or empty

**User** model:

```json
{
   "UserAttributes":{
      "Phone":"string",
      "Email":"string",
      "FirstName":"string",
      "LastName":"string",
      "LanguageCode":"string",
      "TimeZone":"string",
      "Address":{
         "Region":"string",
         "Town":"string",
         "Address":"string",
         "Postcode":"string"
      },
      "Fields":[
         {
            "Key":"string",
            "Value":"string"
         },
         {
            "Key":"string",
            "Value":"string"
         }
      ]
   },
   "subscriptionKeys":[
      "string1",
      "string2"
   ],
   "groupNamesInclude":[
      "string1",
      "string2"
   ],
   "groupNamesExclude":[
      "string",
      "string2"
   ]
}
```

The structure of models (all fields are optional):

```C#
public class User
{
	public UserAttributes UserAttributes { get; set; }
	public List<string> SubscriptionKeys { get; set; }
	public List<string> GroupNamesInclude { get; set; }
	public List<string> GroupNamesExclude { get; set; }
}

public class UserAttributes
{
	public string Phone { get; set; }
	public string Email { get; set; }
	public string FirstName { get; set; }
	public string LastName { get; set; }
	public string LanguageCode { get; set; }
	public string TimeZone { get; set; }
	public UserAddress Address { get; set; }
	public List<Field> Fields { get; set; }
}

public class UserAddress
{
	public string Region { get; set; }
	public string Town { get; set; }
	public string Address { get; set; }
	public string Postcode { get; set; }
}

public class Field
{
	public string Key { get; set; }
	public string Value { get; set; }
}
```

> 📘 Note
>
> `key`
>
> Custom fields variables. [Details >](https://yespo.io/support/how-add-additional-contact-fields#Updating-Custom-Fields-with-Data-from-Custom-Events-via-SDK)
>
> `phone`
>
> We use [Google's libphonenumber library](https://github.com/google/libphonenumber "\{rel='nofollow'}")  for phone number validation. Send phone numbers in the E164 format. A request with an invalid phone number will not be transmitted. You can validate phone numbers [by the link](https://libphonenumber.appspot.com/).
>
> `languageCode`
>
> Data about language in [RFC 5646](https://www.rfc-editor.org/rfc/rfc5646.html "\{rel='nofollow'}") format. Primary language subtag in [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes "\{rel='nofollow'}") format is required. Example: de-AT
>
> `timeZone`
>
> Item from [TZ database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones "\{rel='nofollow'}"). Example: `Europe/Kyiv`

## Anonymous User Attributes

`Reteno` SDK allows tracking anonymous user attributes `(no externalUserId required)`. To set user attributes without externalUserId use method `SetAnonymousUserAttributes(User user)`:

```C#
RetenoSDK.SetAnonymousUserAttributes(User user);
```

> 📘 Note
>
> You can't provide anonymous user attributes with **phone** or/and **email**. For that purpose use `SetUserAttributes()` method with externalUserId
