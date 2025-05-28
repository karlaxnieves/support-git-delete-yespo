---
title: Designing Recommendations in Email
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Designing Recommendations in Email | Yespo Guide
  description: >-
    The document guides on designing email templates for product
    recommendations, customizing options like "Abandoned cart" or "Abandoned
    browse," and structuring blocks with varied product card counts.
  robots: index
next:
  description: ''
---
Let’s consider the design features of an email template with products from viewed/cart/recommendations, etc.

## Selecting Template

You can create an email based on the system's basic templates. Go to _Messages → Messages_, click _New email_, and select _Abandoned cart_ or _Abandoned browse_ in the _Basic tab_:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/53c9bf2d79c8265c4b13674913db4ba7cc3068964a0a3508ac31234f173e07e7-block_design_1.webp",
        null,
        "Basic templates"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The _Abandoned browse_ template is universal because it contains several structures with a different number of cards in them. Such a template is suitable not only for triggers based on user browses but also for any other, where, for example, product recommendations are used. The _Abandoned browse_ template already contains all the necessary variables. You just need to [adjust the data substitution according to the instructions](https://docs.yespo.io/docs/how-set-product-recommendations-email).

If the proposed recommendation block layout is unsuitable, you can create them yourself. After that, request [integration@yespo.io](mailto:integration@yespo.io) so our specialists set up a dynamic content substitution.

## Designing Recommendation Blocks

Customize the appearance of the email and product cards following your campaigns’ design. Structurally, in addition to the standard elements — header, footer, information block — the message must contain:

- Block with one card if a user browses one product;

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/80dc82de82782f203bf0798bfb7a9d29e779dc4cf815b5fd83f85f20861a835b-block_design_2.webp",
        null,
        "Block with one card"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Block with two cards;

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a1b602db0581a680a3c7a080be0c8bc941febf9d5dccc8b7128bbb98690ed43e-block_design_3.webp",
        null,
        "Block with two cards"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Block with three cards.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0fc8e5454fce14b82708fc09a075028d2afd936b087fc00ed1be849313888968-block_design_4.webp",
        null,
        "Block with three cards"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Lay out structures with a different set of cards in the same stripe, one under the other.

If a user browses 15 products during a session, the last 6 products will be displayed in the email (by default), so there is no need to make up more than 3 product cards in the structure. 

If the products in your emails are displayed one in a row, then you do not need to make up stripes with 1, 2, or 3 products.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fd81570ed088ea9711a0d94facf5c97f5ea80cd9d85239f7d2a147256a19741a-block_design_6.webp",
        null,
        "One block in a row"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can copy such a block from the _Abandoned cart_ template.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dbdd3733b3ff5edd3c3837401404062815bfab615ff577f01d65b4466572db74-block_design_7.webp",
        null,
        "Abandoned cart template"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Prepare in advance the entire chain of messages that will participate in the workflow.