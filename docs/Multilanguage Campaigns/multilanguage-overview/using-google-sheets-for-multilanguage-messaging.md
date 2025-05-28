---
title: Using Google Sheets for Multilanguage Messaging
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using Google Sheets for Multilingual Messaging | Yespo Guide
  description: >-
    Find out how to use Google Sheets for multilingual messaging by creating a
    Google Sheet with multilingual content and connecting it to the Yespo
    account.
  robots: index
next:
  description: ''
---
Create one message and connect it with the spreadsheet with your multilingual content — the system will automatically send a message version depending on the user’s profile language. Suitable for both bulk and triggered campaigns in all Yespo channels.

> 📘 Important
>
> To enable this feature, please contact our support team at [support@yespo.io](mailto:support@yespo.io)

Steps to use Google Sheets for multilingual messaging:

1. Prepare a spreadsheet with your multilingual content.
2. Connect it to your Yespo account.
3. Create a message with variables.

## Preparing Spreadsheet

You can place message content on one or several sheets.

1. **An example with one sheet:**

<Image align="center" width="80% " src="https://files.readme.io/46358e7a77470147ec3ff3feee8bf98eeaf29d214e201bfe6240afbd2db8921d-Multilanguage_1.webp" />

Values in the first column are language codes, and horizontal values in the first line are keys used in the message. The values of keys for different language versions are placed at the intersection of language codes and keys. The top language is the default, so users without a specified language in their profiles will receive the top language version.

> 📘 Note
>
> Name the file sheets with the corresponding language codes according to <a rel="nofollow" href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes" target="_blank">ISO 639-1</a> (e.g., en) or <a rel="nofollow" href="https://www.rfc-editor.org/rfc/rfc5646.html" target="_blank">RFC 5646</a> for dialects (e.g., es-MX).
>
> Multilingualism in messages is only supported for some dialects; if you still need to find the one you need, please contact our support at [support@yespo.io](mailto:support@yespo.io)

2\. **An example with several sheets:**

<Image align="center" width="80% " src="https://files.readme.io/81caf88e726c1ecffacad650f3ffbcfa309f82cb336e5b3a5ea9b2d2d4b4164c-Multilanguage_2.webp" />

The first line contains keys used in the message, and the second line contains values for keys in the corresponding columns. The names of the sheets are language codes according to <a rel="nofollow" href="https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes" target="_blank">ISO 639-1</a> specification.

The first language sheet is the default, so users without a specified language in their profiles will receive the first sheet’s language version.

Let’s create a table for the multilingual mobile push campaign with such content:

* The subject: *Just before you go*
* The main text: *Try out our new educational games with 25% off for 1 month*

And the same content in Ukrainian and Spanish.

The table will look like this:

<Image align="center" width="80% " src="https://files.readme.io/2f9ccb4d8b03af59831b2240739611b5494eb7a45b7c01e9bab0c9c96b39226f-Multilanguage_3.webp" />

## Connecting Google Sheet to Yespo

[See detailed instructions here >](https://docs.yespo.io/docs/how-import-external-data-google-sheets)

## Creating a Message with Variables

Add variables to the message in the following format:

```json
$data.get('NAME').get(0).get('subject'),
```

where the *NAME* is *your Google Sheets file name*, and the *subject* is a key from the spreadsheet.

<Image align="center" width="80% " src="https://files.readme.io/d9b219faf1ea23369bfa9e6b31d8d231e2d29a8227a500353fa08230e38e95e7-Multilanguage_4.webp" />

That's how a user will see this notification in English:

<Image align="center" width="40% " src="https://files.readme.io/52f1d3a884dc47041d5e98b1f2284f2b46e71d43270567fe6ae3d030c88be416-Multilanguage_5.webp" />

The report on such a message will look like a standard [multilanguage report](https://docs.yespo.io/docs/report-on-multilingual-campaigns).
