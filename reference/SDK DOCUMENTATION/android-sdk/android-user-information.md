---
title: Android User Information
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
## Tracking User Information

After you [install SDK](https://docs.yespo.io/reference/android-sdk) to your app, Yespo begins automatically collect such data:

- Information about push message delivery and openings,
- Users’ push tokens,
- [_Screen view_ events](https://docs.yespo.io/reference/android-user-behaviour#track-screen-view-events),
- Statuses of the users’ subscription to push notifications.

Yespo automatically creates user profiles with all these data, so you can immediately start working with new contacts, for example, sending them a mobile campaign.

When the user logs in or signs up to your app, you have to define a unique customer identifier that cannot be shared by other contacts. We call it External User Id or just User Id.  The system will match all previous data with an external ID as the primary identifier and update the user’s profile.

[Read more about system customer identifiers and their matching in the system >](https://docs.yespo.io/docs/customer-identifiers-and-matching)

## External User ID

Add your custom External User Ids within `Yespo` by the following method:

```kotlin
Reteno.setUserAttributes(externalUserId: String)
```
```java
Reteno.setUserAttributes(String externalUserId)
```

> 📘 Note
> 
> `externalUserId` should not be null or empty, or `IllegalArgumentException` will be thrown.

[When to send your user ID to Yespo  >](https://docs.yespo.io/reference/using-updateuserattributes-method)

## User Attributes

User attributes are attributes you define to describe segments of your user base, such as language preference or geographic location. Before sending specific contact data via API, you must add custom user fields to Reteno. Read more on how to [set additional fields](https://docs.yespo.io/docs/custom-user-fields).

> 📘 Note
> 
> You can track user attributes only for users with external user IDs.

Add user attributes like **phone**, **email**, etc by the following method:

```kotlin
Reteno.setUserAttributes(externalUserId: String, user: User?)
```
```java
Reteno.setUserAttributes(String externalUserId, User user)
```

**User** model:

```json
{
   "userAttributes":{
      "phone":"String",
      "email":"String",
      "firstName":"String",
      "lastName":"String",
      "languageCode":"String",
      "timeZone":"String",
      "address":{
         "region":"String",
         "town":"String",
         "address":"String",
         "postcode":"String"
      },
      "fields":[
         {
            "key":"string",
            "value":"string"
         },
         {
            "key":"string",
            "value":"string"
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

The structure of models with optional and required fields:

```kotlin
data class User(
    val userAttributes: UserAttributes? = null,
    val subscriptionKeys: List<String>? = null,
    val groupNamesInclude: List<String>? = null,
    val groupNamesExclude: List<String>? = null
)

data class UserAttributes(
    val phone: String? = null,
    val email: String? = null,
    val firstName: String? = null,
    val lastName: String? = null,
    val languageCode: String? = null,
    val timeZone: String? = null,
    val address: Address? = null,
    val fields: List<UserCustomField>? = null,
)

data class Address(
    val region: String? = null,
    val town: String? = null,
    val address: String? = null,
    val postcode: String? = null
)

data class UserCustomField(
    val key: String,
    val value: String? = null
)
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

> Available for RetenoSDK starting from version **1.5.3**

`Reteno` SDK allows tracking anonymous user attributes `(no externalUserId required)`. To set user attributes without externalUserId use method `setAnonymousUserAttributes()`:

```kotlin
Reteno.setAnonymousUserAttributes(attributes: UserAttributesAnonymous)
```
```java
Reteno.setAnonymousUserAttributes(UserAttributesAnonymous attributes)
```

**UserAttributesAnonymous** model:

```kotlin
data class UserAttributesAnonymous(
    /**
     *  Contact first name. Numbers cannot be used
     */
    val firstName: String? = null,
    /**
     * Contact last name. Numbers cannot be used
     */
    val lastName: String? = null,
    /**
     * Data about language in RFC 5646 format.
     * Primary language subtag in ISO 639-1 format is required.
     * Example: de-AT
     */
    val languageCode: String? = null,
    /**
     * Item from TZ database. Example: Europe/Kyiv.
     * See column [TZ database name](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
     */
    val timeZone: String? = null,
    /**
     * Contact full address
     *
     * @see Address
     */
    val address: Address? = null,
    /**
     * Additional field values for contact
     *
     * @see UserCustomField
     */
    val fields: List<UserCustomField>? = null,
)
```

> 📘 Note
> 
> You can't provide anonymous user attributes with **phone** or/and **email**. For that purpose use `setUserAttributes()` method with externalUserId