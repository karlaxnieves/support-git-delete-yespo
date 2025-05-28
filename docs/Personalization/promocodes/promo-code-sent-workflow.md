---
title: Promo Code Sent from a Workflow
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Promo Code Sent from a Workflow | Yespo Guide
  description: >-
    The document explains how to manage promo codes via API for trigger
    messages: generate, upload, configure codes in workflows, and ensure each
    code is used only once.
  robots: index
next:
  description: ''
---
There is a possibility to preliminarily upload the list of promo codes in the system for trigger messages, sent from [workflow](https://docs.yespo.io/docs/introduction-to-workflows). In the moment of sending the message the workflow will obtain next promo code from the list. The system guarantees that one promo code will be used only once.

The system of promo codes is uploaded in the system using special API methods:

- [Uploading from CSV file](https://docs.yespo.io/reference/getpromocodes-1)
- [Uploading from JSON](https://docs.yespo.io/reference/insertpromocodes_1)

The process of configuring looks like following:

## Generating promo codes and transferring them using API

Create enough quantity of promo codes and them not to run out suddenly.

Upload promo codes in our system by API using method, convenient for you. Uploading CSV-file or use JSON with next characteristics of promo codes:

- **code** – value of promo code
- **expirationDate** – expiration date of the promo code. Date format is next: 2017-12-31T23:59
- **discount** – discount. Indicate value from 0 up to 99.
- **type** – promo code type. Indicate any value. For example, birthday, blackfriday, christmas etc.
- **inUse** – flag if promo code is already used or not.

_discount_ and _type_ are created for segmentation promo codes in database. Technically it is not important, what discount is indicated. Real discount for the customer will be as you grant it on your site.

It is impossible to delete uploaded, but not used promo code. That is why if some promo codes are not urgent, update them by indicated true value for inUse flag. During using, the system will change statuses of using promo codes from false to true.

## Creating the message

It is necessary to substitute variable `$!data.get(‘promocode’)` in the message on the place of promo code.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e69c732d6eb3e65c74f911b41cdaa1f2cf29c754f1e8061e0bdf56305283a26-81936db-promocodes3.webp",
        null,
        "Variable in the message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Configuring the workflow

It is necessary to substitute at least 2 blocks in the workflow: Task – _Get promo code_ and block with communication channel (token, email, phone number).

The workflow can look like following:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1eeffe23f66b2b4fd2396730d7fdb422bc1e15d31ced5db3c91502b25a029b02-promo-code-sent-from-a-workflow.webp",
        null,
        "Workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


<br />

Read more [how to configure Get promo code block](https://docs.yespo.io/docs/popular-blocks#get-promo-code). In message block choose preliminarily created message and indicate parameters from the event, which contains contact ID.