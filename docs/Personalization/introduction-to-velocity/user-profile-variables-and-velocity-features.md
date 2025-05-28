---
title: User Profile Variables and Velocity Features
excerpt: >-
  Personalize your marketing communications with data from your users’ profiles
  in Yespo. Optimize personalization with Velocity features.
deprecated: false
hidden: false
metadata:
  title: User Profile Variables and Velocity Features | Yespo Guide
  description: >-
    The document explains how to personalize messages using variables, and
    demonstrates using Velocity features to conditionally display email content
    based on user data, such as location.
  robots: index
next:
  description: ''
---
## Using profile variables

The simplest and most widely used example of message personalization is to automatically replace the `%FIRSTNAME%`variable with the user's name.

Also, you can substitute any other data from the user profile in the same way:

- `%NICKNAME%`
- `%CITY%`
- `%PROMOCODE%`
- `%BONUSES%`

You can see the list of these variables in the message editor (it includes standard contact fields and additional fields that you can create in your account).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6471947f038130e7fb6dd605145e8888ca426e785bd0539801c149cf1b1c6910-user-profile-variables-and-velocity-features.-001.gif",
        null,
        "Variables in the message editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To see all user fields available in your account, go to your profile → _Settings → Additional fields_. [Additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) can contain any contact data you send to Yespo through [API](https://docs.yespo.io/reference/getting-started-with-your-api).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/70d427c1b5dd8b0203c60268b951bc614ac13c9fbc61cd8ea9d7460e8d9cc50f-user-profile-variables-and-velocity-features.-002.webp",
        null,
        "ditional fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


[More on using user profile variables >](https://docs.yespo.io/docs/personalization-and-dynamic-variables)

## Optimizing user profile variables usage with Velocity features

The use of user profile variables has some potential issues. For example, you may need to show different message blocks depending on users’ data. Or to hide certain blocks unless all data is available. To do this, use velocity features. Let’s see an example of using velocity with data from user profile.

### Use case: personalizing message depending on location data

#### Task

We have an additional data field in users’ profiles — `PERSONAL.LOCATION`. We need to show different email blocks depending on on data in this field:

- If `PERSONAL.LOCATION` = Maldives — show block with description of this location and don’t show block with Tuscany description.
- If `PERSONAL.LOCATION` = Tuscany — show block with description of this location and don’t show block with Maldives description.
- If `PERSONAL.LOCATION` ≠ Maldives or Tuscany — don't show any of these blocks.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/534f34492cf982f916495ba58eebe8dcb80610bce587b2ef216dfda7ef82023b-2ba17fe-8589aaa-user_profile_variables_3.webp",
        null,
        "Personalizing message depending on location data"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Solution

1. Click on the first structure in the email where you want to show dynamic content (Tuscany) and open the _Code editor._

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/435f0e5e47cfd929421bdb6652dd776b1771c9c6a9ad5fd16b75305376be0037-user-profile-variables-and-velocity-features.-003.webp",
        null,
        "Code editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Find the first `tr` tag in the selected email structure code.
3. Declare a personalization variable(s) that will be used in the email above `tr` tag. In our case this is

```json
<!--%PERSONAL.LOCATION%-->
```

4. Add conditional statements that are responsible for displaying this structure to the structure code. Use the following statement format:

```json
<!--#if($data.get('parameter name')=='value1')-->
```

In our case it will be the following statement:

```json
<!--#if($data.get('PERSONAL.LOCATION')=='Tuscany')-->
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cdb1cec5df61a2d247d10a8c9268e4d6c2149e38fbe7d9639730f2855e528d47-user-profile-variables-and-velocity-features.-004.webp",
        null,
        "Conditional statements"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Click on the second structure in the email where you want to show dynamic content (Maldives). The corresponding structure code will be opened in the _Code editor_.
6. Find the first `tr` tag in the selected email structure code.
7. Add conditional statements that are responsible for displaying this structure to the structure code above `tr` tag. Use the following statement format:

```json
<!--#elseif($data.get('parameter name')=='value2')-->
```

In our case it will be the following statement:

```json
<!--#elseif($data.get('PERSONAL.LOCATION')=='Maldives')-->
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b29b7121f7bc777733c218c4c0bf59968f18248e6f2b41ef92acc57fc6e24e4-user-profile-variables-and-velocity-features.-005.webp",
        null,
        "Add statement"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Results

That’s how users with different `PERSONAL.LOCATION` parameters will see the message after sending:

**1) User with _Tuscany_ parameter\_:**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b8a4c27be27df1b6138495c8fdae94ebfa9b43f51ea88128dfdc7503e5ffd05-user-profile-variables-and-velocity-features.-006.webp",
        null,
        "Tuscany parameter"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


**2) User with _Maldives_ parameter\_:**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d2442f2696d17ccb13c4afb6fa617aab98913f224167b944b5f6a66e0132dc0c-41f7e14-07d036d-user_profile_variables_9.webp",
        null,
        "Maldives parameter"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


**3) User with empty `PERSONAL.LOCATION` parameter:**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3df15d2feaf8d2a0d43117879d75c61ae65f09354e01b97219fd1a533fa9300e-847cc16-fdd48fc-user_profile_variables_10.webp",
        null,
        "Empty PERSONAL.LOCATION"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]