---
title: Promo Code Sent via Preprocessor
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Promo Code Sent via Preprocessor | Yespo Guide
  description: >-
    The document explains how to use the Preprocessor in Yespo to send
    personalized bulk emails by uploading a JSON file with unique data, such as
    promo codes, for each subscriber, and substituting this data into messages.
  robots: index
next:
  description: ''
---
Preprocessor is designed for sending mass mailings, but with unique content for each subscriber. At first, you need to generate a file with data in certain format and upload it in Yespo. During mailing, the system will take data from this file and substitute in messages. Usually it is used for sending mailing with personal goods recommendations, but one can use it to transfer any data, for example, promo code, instead of set of goods.

> 📘 Note
>
> This method works only for emails. Learn more about preprocessor here.

Mailing sending process using preprocessor looks like following:

## Creating and upload file for preprocessor with promo codes

It is necessary to create file of certain format for sending messages using preprocessor. File in JSON format needs to contain keys (email-addresses) and array with data for each key.

Example of file contents:

```json
{
    "mail1@example.com": [{
        "promocode": "001100"
    }],
    "mail2@example.com": [{
        "promocode": "001101"
    }],
    "mail3@example.com": [{
        "promocode": "001102"
    }]
}
```

More information about file format [is here](https://docs.yespo.io/docs/what-preprocessor).

## Creating the message

It is necessary to substitute variable on the place of promo code. For a given example, the variable will be following:

`$!data.get('recommendations').get(0).get('promocode')`

Also, it is necessary to attach the preliminarily uploaded file of preprocessor to this message. And then you can send the usual campaign.

<Image align="center" width="80% " src="https://files.readme.io/e656ea06eca8b302274150269a517567e5436057220e7113d5a990d2a042a14e-3c344d6-promocodes9.webp" />
