---
title: Tracking User Time Zone and Language
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Tracking User Time Zone and Language | Yespo Guide
  description: >-
    The document outlines methods for recording a contact's time zone and
    language via API or SDK, and provides examples for implementing these
    updates
  robots: index
next:
  description: ''
---
You can record the contact's time zone and language in two ways:

* via API.
* using the SDK (when transferring data from the frontend of the mobile application).

> 📘 Note
>
> Send data about language in <a rel="nofollow" href="https://www.rfc-editor.org/rfc/rfc5646.html" target="_blank"> RFC 5646</a> format. A primary language subtag in <a rel="nofollow" href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes" target="_blank"> ISO 639-1</a> format is required. Example: de-AT
>
> Send data about time zone in <a rel="nofollow" href="https://en.wikipedia.org/wiki/List_of_tz_database_time_zones" target="_blank"> TZ database</a> format. Example: Europe/Kyiv

> ❗️ Important
>
> You can track user attributes (language, time zone etc.) only for users with [external user IDs](https://docs.yespo.io/docs/external-id-creating-and-updating-users).

## API Methods

Use [Add/update a contact](https://docs.yespo.io/reference/addcontact-1) API method to add a new or update an existing user and [Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1) for bulk adding/updating your users’ data.

### Add/update a contact request example

```json
curl --request POST \
     --url https://api.yespo.io/api/v1/contact \
     --header 'accept: application/json; charset=UTF-8' \
     --header 'authorization: Basic 
your_api_key 
\
     --header 'content-type: application/json' \
     --data '
{
     "channels": [
          {
               "type": "email",
               "value": "john@example.com"
          }
     ],
     "languageCode": "en-us",
     "timeZone": "Europe/Kyiv",
     "firstName": "John",
     "lastName": "Smith",
     "externalCustomerId": "24233"
}
'
```

### Add/update contacts request example

```json
curl --request POST \
     --url https://api.yespo.io/api/v1/contacts \
     --header 'accept: application/json; charset=UTF-8' \
     --header 'authorization: Basic 
your_api_key
 \
     --header 'content-type: application/json' \
     --data '
{
     "contacts": [
          {
               "channels": [
                    {
                         "type": "email",
                         "value": "john@example.com"
                    }
               ],
               "firstName": "John",
               "lastName": " Smith",
               "languageCode": "en-US",
               "timeZone": "Europe/Kyiv",
               "externalCustomerId": "543323"
          }
     ],
     "dedupeOn": "externalCustomerId"
}
'
```

## iOS SDK

Add user attributes like time zone and language by the following method:

```swift
Reteno.updateUserAttributes(externalUserId: "USER_ID", userAttributes: UserAttributes, subscriptionKeys: [String], groupNamesInclude: [String], groupNamesExclude: [String])
```

The **UserAttributes** object example:

```swift
func saveUser() {
    let attributes = UserAttributes(
        phone: user.phone,
        email: user.email,
        firstName: user.firstName,
        lastName: user.lastName,
        languageCode: "en-US",
        timeZone: "Europe/Kyiv"
    )
    Reteno.updateUserAttributes(externalUserId: user.id, userAttributes: attributes)
}
```

[Details >](https://docs.yespo.io/reference/ios-user-information#user-attributes)

## Android SDK

Methods for adding user attributes:

```java
Reteno.setUserAttributes(String externalUserId, User user)

Reteno.setUserAttributes(externalUserId: String, user: User?)
```

The **userAttributes** object example:

```java
fun setLanguageTimeZone() {
        val userId = "UserIdHere"
        val userAttributes = UserAttributes(
            languageCode = "en-US",
            timeZone = "Europe/Kyiv"
        )
        val user = User(
            userAttributes = userAttributes,
            subscriptionKeys = listOf("key1", "key2", "key3")
        )
        application.getRetenoInstance().setUserAttributes(userId, user)
    }
```

[Details >](https://docs.yespo.io/reference/android-user-information#user-attributes)

## React Native SDK

Method for adding user attributes:

```typescript
import { setUserAttributes } from 'reteno-react-native-sdk';

setUserAttributes({
    externalUserId: "USER_ID",
    user: {
        attributes: userAttributes,
        subscriptionKeys: string[],
        groupNamesInclude: string[],
        groupNamesExclude: string[]
    }
})
```

The **userAttributes** object example:

```typescript
setUserAttributes({
  externalUserId,
  user: {
    userAttributes: {
      languageCode: "de-AT",
      timeZone: "Europe/Kyiv",
    },
  },
);
```

[Details >](https://docs.yespo.io/reference/react-native-user-information#user-attributes)