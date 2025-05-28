---
title: Promo Code Generated in a Workflow
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Promo Code Generated in a Workflow | Yespo Guide
  description: >-
    The document explains generating and decoding promo codes in a workflow:
    create an encoding key, configure messages, set up workflows, and enable
    site-based code validation for discounts.
  robots: index
next:
  description: ''
---
One can generate promo codes directly in the workflow when sending the message. The expiration date, type, and discount will be codified in the promo code itself.

On your site, using reverse algorithm, you can decode promo code, entered by user, and grant him respective discount or bonuses in accordance with conditions of your sale. Promo code encoding/decoding algorithm is described in this document.

Configuring process looks like following:

## Creating encoding key

Promo codes are encoded using key, which third persons don’t need to know. Generate the key in `eSSuperKeyXXXXXXXXXXXXXX`, where `XXXXXXXXXXXXXX` - 14 any numbers. Tell us the key. We will attach it to your account.

## Creating message for sending

It is necessary to substitute `$!data.get(‘promocode’)` variable in the message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/789cd94f70a56c404c148cfc659100849f4171bde9d3a3566d2d60b2bb572c0d-125304b-promocodes3.webp",
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

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/030e97a5fbeb53eff1f0515e799a978a7491da502dc4d96c195b951a3115acd7-promo-code-generated-in-a-workflow.webp",
        null,
        "Workflow"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The blocks _Task – Create promo code_ and _Send message_ are used in the workflow. Read more how to set up [Create promo code](https://docs.yespo.io/docs/popular-blocks#create-promo-code) block.

In _Message_ block choose preliminarily created message and indicate parameters from the event, which contains contact ID.

## Decoding promo code

Recipient will obtain promo code in the following format `CRRH-ASDF-HGVB-MNCA`.

You will be able to decode this promo code on your site using algorithm and key. Successfully decoding the promo code you will, firstly, validate it; secondly, obtain following data: expiration date, discount, type of promo code. The algorithm is described in the document.