---
title: Flutter User Information
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
You can track the user related information using external user ID and/or user attributes. For that, you have to add `userExternalId` and `setUserAttributes` to Reteno Flutter.

## Adding External User ID

External user ID is an ID you have assigned to a user in your system (external for 'Reteno').\
You can add these in `Reteno` Flutter using the following method:

```text Dart
import 'package:reteno_plugin/reteno.dart';

final reteno = Reteno();
reteno.setUserAttributes(
  userExternalId: 'USER_ID',
  user: userInfo,
);
```

[When to send your user ID to Yespo  >](https://docs.yespo.io/reference/using-updateuserattributes-method)

## Adding User Attributes

User attributes define the information you collect about contacts in your user base. For example, phone number, email address, language preference, geographic location.

You can add user attributes using the following method:

```text Dart
import 'package:reteno_plugin/reteno.dart';

final reteno = Reteno();
reteno.setUserAttributes(
  userExternalId: 'USER_ID',
  user: userInfo,
);
```

Structure of the `RetenoUser` object:

```text Dart
class RetenoUser {
  RetenoUser({
    this.subscriptionKeys,
    this.userAttributes,
    this.groupNamesExclude,
    this.groupNamesInclude,
  });

  final UserAttributes? userAttributes;
  final List<String>? subscriptionKeys;
  final List<String>? groupNamesInclude;
  final List<String>? groupNamesExclude;
}

class UserAttributes {
  UserAttributes({
    this.lastName,
    this.firstName,
    this.address,
    this.email,
    this.fields,
    this.languageCode,
    this.phone,
    this.timeZone,
  });
  final String? phone;
  final String? email;
  final String? firstName;
  final String? lastName;
  final String? languageCode;
  final String? timeZone;
  final Address? address;
  final List<UserCustomField>? fields;
}

class Address {
  Address({
    this.address,
    this.postcode,
    this.region,
    this.town,
  });
  final String? region;
  final String? town;
  final String? address;
  final String? postcode;
}

class UserCustomField {
  UserCustomField({
    required this.key,
    this.value,
  });
  final String key;
  final String? value;
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

> Available for reteno\_plugin starting from version **1.1.0**\
> `Reteno` plugin allows tracking anonymous user attributes `(no externalUserId required)`. To set user attributes without externalUserId use method `setAnonymousUserAttributes()`:

````text Dart
Reteno.setAnonymousUserAttributes(AnonymousUserAttributes attributes);
**AnonymousUserAttributes** model:
```dart
class AnonymousUserAttributes {
  AnonymousUserAttributes({
    this.lastName,
    this.firstName,
    this.address,
    this.fields,
    this.languageCode,
    this.timeZone,
  });
  final String? firstName;
  final String? lastName;
  final String? languageCode;
  final String? timeZone;
  final Address? address;
  final List<UserCustomField>? fields;
}
````

> **Note**: you can't provide anonymous user attributes with **phone** or/and **email**. For that purpose use `setUserAttributes()` method with externalUserId
