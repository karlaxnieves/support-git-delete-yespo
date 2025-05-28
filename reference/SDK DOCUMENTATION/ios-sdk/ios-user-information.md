---
title: iOS User Information
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

After you [install SDK](https://docs.yespo.io/reference/ios-sdk) to your app, Yespo begins automatically collect such data:

- Information about push message delivery and openings,
- Users’ push tokens,
- [_Screen view_ events](https://docs.yespo.io/reference/ios-user-behaviour#track-screen-view-events),
- [Statuses of the users’ subscription](https://docs.yespo.io/reference/ios-user-behaviour#track-mob-push-subscribers) to push notifications.

Yespo automatically creates user profiles with all these data, so you can immediately start working with new contacts, for example, sending them a mobile campaign.

When the user logs in or signs up to your app, you have to define a unique customer identifier that cannot be shared by other contacts. We call it External User Id or just User Id.  The system will match all previous data with an external ID as the primary identifier and update the user’s profile.

[Read more about system customer identifiers and their matching in the system >](https://docs.yespo.io/docs/customer-identifiers-and-matching)

## External User ID

Add your custom External User Ids within `Yespo` by the following method:

```swift
Reteno.updateUserAttributes(externalUserId: "USER_ID", attributes: UserAttributes)
```

[When to send your user ID to Yespo  >](https://docs.yespo.io/reference/using-updateuserattributes-method)

## User Attributes

User attributes are attributes you define to describe segments of your user base, such as language preference or geographic location. Before sending specific contact data via API, you must add custom user fields to Reteno. Read more on how to [set additional fields](https://docs.yespo.io/docs/custom-user-fields).

> 📘 Note
> 
> You can track user attributes only for users with external user IDs.

Add user attributes like phone, email, etc by the following method:

```swift
Reteno.updateUserAttributes(externalUserId: "USER_ID", userAttributes: UserAttributes, subscriptionKeys: [String], groupNamesInclude: [String], groupNamesExclude: [String])
```

> 📘 Note
> 
> `groupNamesInclude` and `groupNamesExclude` parameters are available in SDK version 1.0.0 or later.

The `UserAttributes` object structure:

```swift
public struct UserCustomField {
    let key: String
    let value: String
}

public struct Address {
    let region: String?
    let town: String?
    let address: String?
    let postcode: String?
}

public struct UserAttributes {
    let phone: String?
    let email: String?
    let firstName: String?
    let lastName: String?
    let languageCode: String?
    let timeZone: String?
    let address: Address?
    let fields: [UserCustomField]
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
> We use [Google's libphonenumber library](https://github.com/google/libphonenumber "{rel='nofollow'}")  for phone number validation. Send phone numbers in the E164 format. A request with an invalid phone number will not be transmitted. You can validate phone numbers [by the link](https://libphonenumber.appspot.com/).
> 
> `languageCode`
> 
> Data about language in [RFC 5646](https://www.rfc-editor.org/rfc/rfc5646.html "{rel='nofollow'}") format. Primary language subtag in [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes "{rel='nofollow'}") format is required. Example: de-AT
> 
> `timeZone`
> 
> Item from [TZ database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones "{rel='nofollow'}"). Example: `Europe/Kyiv`

## Anonymous User Attributes

`Reteno` SDK allows tracking anonymous user attributes. To start tracking information about user without identificator, use `updateAnonymousUserAttributes()` method:

```swift
let attributes = AnonymousUserAttributes(
    firstName: user.firstName,
    lastName: user.lastName,
    timeZone: TimeZone.current.identifier,
    fields: [
        UserCustomField(key: "LIST_NAME.FIELD_NAME", value: "Ukraine")
    ]
)
Reteno.updateAnonymousUserAttributes(userAttributes: attributes)
```

> 📘 Note
> 
> You can't provide to the SDK anonymous user _phone_ and _email_ attributes.