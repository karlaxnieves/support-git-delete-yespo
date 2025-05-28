---
title: Setting Rules for Data Sources
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Rules for Data Sources | Yespo Guide
  description: >-
    The document outlines how to set up rules for recommending products from a
    data source, including main rules based on product characteristics, rules
    for contact fields, and general conditional rules, with step-by-step
    instructions for adding and configuring these rules.
  robots: index
next:
  description: ''
---
For any data source, you can additionally set the rules for issuing recommended products. For example, show or exclude products from the display

- by characteristics from the feed (e.g., brand, price, category),
- according to contact details (e.g., favorite seller, shoe size),
- according to the configured conditions (if — then).

## Adding Rules for a Data Source

1\. Go to the _Data Sources_ tab in your account settings.

2\. Click _Add rules_ on the data source, or edit a previously created rule.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc469130789153619651d6b04ad556ec0740e49e79e22dced6c7d42052c8ebf7-add_rules_12.webp",
        "",
        "Data sources"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3\. Enter a name for the rules.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60f07cce137df926cb164390f7f91ec44ea0e35fd54b7aaad7d9bc49838147d1-add_rules_2.webp",
        "",
        "Name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


There are three types of rules available to you:

- Main
- For contact fields
- General conditionals

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d457785305fbac7f60563636702ce7c29b1ae8d04945393274886beda06dd7ed-add_rules_3.webp",
        "",
        "Rule types"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Main rules

The main rules are set for any product characteristics presented in your feed. These rules apply regardless of any other rules that you have defined.

#### Setting main rules

1\. Click the _Add rule_ button in the _Main rules_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ad0a3bb58b5b7179935bd8d54c3bcbcaccd60c2008b998322bbebfea4fdb72db-add_rules_4.webp",
        "",
        "Add rule"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. Set up conditions for filtering products:

- **Show only products:** for example, a specific brand.
- **Show more products:** for example, promotional.
- **Do not show products:** for example, cheaper than $200.
- **Diversity:** for example, show up to 2 products from one category.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/64d82ed81a913fa2bb64de8d56b4aa53a4f35d7a3104710fde8b5da2d87ce2e3-add_rules_5.webp",
        "",
        "Set up conditions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Data source rules include the _Relative Range_ option, which allows you to configure the display of products within the price range relative to the price of the specific product that the customer is viewing or to which the recommendation is linked. For example, if you set the range from 70% to 300%, and the user is viewing a product for $1000, the system will select products within the range from $700 to $3000.
> 
> [block:image]{"images":[{"image":["https://files.readme.io/1567cc65b5c0fda66939190a3a6473ee9b5b5225c0a945d538e63342dec8b713-range.png","","Relative range"],"align":"center","sizing":"80% "}]}[/block]

### Rules for contact fields

Recommended products in campaigns may depend on the values in the contact fields. For example, a marketplace can recommend products from a favorite seller, an online store can only show shoes according to a contact's size, etc.

#### Setting rules for contact fields

1\. Select one of the following display options in the first column:

**a. Show only products:**

- If a contact does not have the value of an additional field specified in the filter, for example, Size, they will receive personalized recommendations without applying the filter.
- If a contact has a field value, but the feed doesn't have that value, they will not get recommendations.
- If a contact has a field value, and there are recommended products with the required Size in the feed, the contact will receive recommendations based on the filter.

**b. Show more products:**

- If a contact has the value of an additional field specified in the filter, they will receive personalized recommendations without applying the filter.
- If a contact has a field value, but in the feed, let's say, only 3 products with the required value, they will receive 3 recommendations according to the filter, the rest — without applying the filter.
- If a contact has a field value and enough products in the feed with a matching value, they will receive a full set of recommendations with the filter applied.

**c. Do not show products:**

- If the value in the additional field specified as a filter matches the product's value in the feed, a contact will not see such a product in the recommendations.
- If a contact does not have the value of the additional field specified in the filter, they will receive recommendations without applying the filter.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a390804a2674fbef21eb7d0f29d028c7a4af1785cd8115106bb75ce6341ba9e-add_rules_6.webp",
        "",
        "Display options"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


2\. Select the contact data field in the second column.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/960c5ade813c118650a8bd16fc2887cb68d83faadabdb7ff085f54d0b8362cda-add_rules_7.webp",
        "",
        "Contact fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3\. Select a field from the product feed in the last column.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/abe430e62aeda0b170d8940e025f912c1ca9872fc8b992a3034ca10e66dd17cf-add_rules_8.webp",
        "",
        "Fields from the product feed"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Matching links the contact field and the product field in the feed. For example, the _size_ in the contact field is equal to the _eu\_size_ field in the feed.

### General conditional rules 

Rules that are followed on certain conditions for all items. For example, IF the website visitor views the product page of a particular brand, THEN recommend them only products of this brand. Conditional rules are followed after the main rules and rules for contact fields, if set.

#### Setting general conditional rules

1\. Click the arrow next to the description of conditional rules →  the _Add condition_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0728c18f4df46aaaae7a3dace063a366d6811aecfde2a0e86ed5a56e45cac2bf-add_rules_9.webp",
        "",
        "Add condition"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. Add _If_ and _Then_ conditions: for example, if the user viewed the _Bags_ category, only show bestsellers from this category.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e764fab7f9c226e7e58c539367c232b6ab8bae3492627900b69c6737f9da508d-add_rules_10.webp",
        "",
        "Condition's example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Saving Settings

When finished adding rules, click _Done_ at the bottom of the page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/047ca9559e6d70ca7a96516f5f5bc599fba72091649e7f4c4d945c8212b1560a-add_rules_11.webp",
        "",
        "Saving settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The rules you created will be displayed on the card of the data source to which they refer.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f03e928f29655f0708d9825807cf1486aa26a123735ff5c8fc5219b1fbd9ce5c-add_rules_12.webp",
        "",
        "Rule for data source"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]