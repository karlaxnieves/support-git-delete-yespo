---
title: Ionic User Information
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
## External User ID

Add your custom External User Ids within `Reteno` by the following method:

```typescript
import {
  Address,
  UserAttributes,
  SetUserAttributesPayload,
  AwesomeCordovaPluginReteno,
} from "awesome-cordova-plugin-reteno/dist/ngx";

var payload = {
  externalUserId: "USER_ID",
  user: user,
};

RetenoPlugin.setUserAttributes(payload, success, error);
```

## User Attributes

User attributes are attributes you define to describe segments of your user base, such as language preference or geographic location.

Add user attributes like phone, email, etc by the following method:

```typescript
import {Address, UserAttributes, SetUserAttributesPayload, AwesomeCordovaPluginReteno} from "awesome-cordova-plugin-reteno/dist/ngx";


setUserAttributes({
    externalUserId: "USER_ID",
    user: {
        userAttributes: userAttributes,
        subscriptionKeys: string[],
        groupNamesInclude: string[],
        groupNamesExclude: string[]
    }
})
```

The `userAttributes` object structure:

```typescript
type Address = {
  region?: string | null;
  town?: string | null;
  address?: string | null;
  postcode?: string | null;
};

type Field = {
  key: string;
  value: string;
};

type Fields = Field[];

type UserAttributes = {
  phone?: string | null;
  email?: string | null;
  firstName?: string | null;
  lastName?: string | null;
  languageCode?: string | null;
  timeZone?: string | null;
  address?: Address | null;
  fields?: Fields | null;
};

type User = {
  userAttributes?: UserAttributes | null;
  subscriptionKeys?: String[] | null;
  groupNamesInclude?: String[] | null;
  groupNamesExclude?: String[] | null;
};

type SetUserAttributesPayload = {
  externalUserId: string;
  user: User;
};
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

Reteno SDK allows tracking anonymous user attributes. To start tracking information about user without identificator, use `setAnonymousUserAttributes` function:

```typescript
function setAnonymousUserAttributes(
  payload: AnonymousUserAttributes
): Promise<void>;

type AnonymousUserAttributes = {
  user: {
    userAttributes: {
      firstName?: string | null | undefined;
      lastName?: string | null | undefined;
      languageCode?: string | null | undefined;
      timeZone?: string | null | undefined;
      address?: Address | null | undefined;
      fields?: Fields | null | undefined;
    };
  };
};
const userAttributes = {
  firstName: this.firstName,
  lastName: this.lastName,
  languageCode: this.language,
  timeZone: this.timezone,
  address: retenoAddress,
};

const payload = {
  user: { userAttributes },
};
this.retenoPlugin.setAnonymousUserAttributes(payload);
```

> 📘 Note
>
> You can't provide anonymous user attributes with **phone** or/and **email**. For that purpose use `setUserAttributes` method with externalUserId
