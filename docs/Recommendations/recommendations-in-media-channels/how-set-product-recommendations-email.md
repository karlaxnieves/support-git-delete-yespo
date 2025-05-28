---
title: Setting Up Recommendations for Trigger Campaigns
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Recommendations for Trigger Campaigns | Yespo Guide
  description: >-
    Product recommendations in email show relevant offers based on customer’s
    behaviour and website activity. Learn how to set up recommendation
    algorithms and add dynamic content to your template.
  robots: index
next:
  description: ''
---
The recommendation blocks in the email are placed in stripes. Stripe’s code contains the rules for substituting dynamic data.

You will find the _Abandoned browse_ template in your account, where this stripe is already set up. 

You only need to create data sources and insert their names into the stripes’ code.

We will show how to create a trigger template with two dynamic stripes: one with products viewed by the user and one with recommendations based on products viewed. Each stripe requires its data source.

## Recommendation Setup Steps

1. Create [data sources](https://docs.yespo.io/docs/create-data-source-recommendations) based on the _Abandoned view (up to 6 products)_ and _Recommendations for 6 abandoned views (up to 6 rec.)_ algorithms.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84618b8b47eead2f06028503b7fe4d5132382eed102f329d6834a68939ef3fa5-recommendation_blocks_1.webp",
        null,
        "New data source"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Most algorithms are designed for specific advanced segmentation triggers and work only in them. Setting up a universal algorithm is described in the article [Setting Up Product Recommendations for Promo Campaigns](https://docs.yespo.io/docs/product-recommendations-promo).

2. Go to the _Messages_ section on the _Messages_ tab and click _New Email_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/00c50fe547673fe67150f8b0b943869d21bf36a6add1a57073e54bce1d068ac3-recommendation_blocks_2.webp",
        null,
        "New Email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Select the _Abandoned browse_ basic template.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b07f2b1419cd770d6b4780cd1548f0c6dd92138bd703a5f6f4846d0819c0b72b-abandoned_browse.webp",
        null,
        "Abandoned browse"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The template contains 2 stripes with product cards:

- the first (_You recently viewed_) — with dynamic settings;
- the second (_You may also like_) is illustrative, without dynamic settings.

4. Select the first stripe with products and open its code.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7020a855ac1dd63b48d57994fe2c3a164d4f2fce5fbc3bc1179ec49876ad63ba-recommendation_blocks_4.webp",
        null,
        "Stripe's code"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. In the **`#foreach($item in $data.get('views'))`** line, replace **`views`** with the name of the data source you created based on the _Abandoned view (up to 6 products)_ algorithm.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4de78c9dc61f065bfe6eb4812402041a0a862e582df89dd3ab3ab7d871eea3e3-recommendation_blocks_5.webp",
        null,
        "Your source name"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Customize the stripe’s appearance.

The stripe’s structure is universal: depending on the number of viewed items, the recipient will see one, two, or three cards in a row.

You can change the design of the stripe’s elements: colors, text, and background.

We do not recommend changing the stripe’s structure, i.e., the arrangement of its elements to each other: this will break the layout, and the recipient will see an incorrect display of the email’s content. Also, you cannot change the variables specified in the structure blocks since they are responsible for displaying product data from your feed.

If you want to create a fundamentally different structure with dynamic content, please send a request to [support@yespo.io](mailto:support@yespo.io)

[Learn more about designing recommendations in email](https://docs.yespo.io/docs/designing-recommendations-email).

7. Save the stripe as a module.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e3c807b1c3fcedc824a78021b2a4946383edb022fed66533f4f515ee2d6e7459-recommendation_blocks_6.webp",
        null,
        "Save as a module"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can insert the saved module in any campaigns with product selections, for example, for the _Abandoned cart_ trigger. You just need to replace the name of the data source.

We will use the saved module in the same template as a stripe with recommendations for viewed products.

8. Remove the illustrative stripe with product cards from the template (_You may also like_).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4809517d3e77ee47a49a244bb976689d449c5f2dac589ea87fa134197ad87c88-recommendation_blocks_7.webp",
        null,
        "Delete stripe"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


9. Insert the module you saved before in place of the removed stripe.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/69049040b8c12c9de3e3ffbbb8f48c68a9e07616ef90c69a065f7f731e057fac-recommendation_blocks_8.webp",
        null,
        "Insert the module"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


10. Replace the name of the data source in the stripe’s code with the one you created for the _Recommendations for 6 abandoned views (up to 6 rec.)_ algorithm.

This completes the recommendation settings. You can insert saved modules into your trigger template or redesign the template you are currently working on to match the style of your site.

> 📘 Note
> 
> You can define what to do with messages when there is no data for recommendations - to send or not. To do this, add one of the variants of the Velocity command to the recommendations’ code:
> 
> - **`$!datasource('source_name').required('false')`** — send,
> - **`$!datasource('source_name').required('true')` **— do not send.