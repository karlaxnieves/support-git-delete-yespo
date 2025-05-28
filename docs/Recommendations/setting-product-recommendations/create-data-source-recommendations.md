---
title: Creating a Data Source for Recommendations
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating a Data Source for Recommendations | Yespo Guide
  description: >-
    The document outlines the process of creating a data source in Yespo for
    setting up recommendation algorithms on websites, media channels, and mobile
    applications.
  robots: index
next:
  description: ''
---
The data source is a recommendation filtering algorithm that can be applied to the website, media channels, and mobile application.

Creating a data source is mandatory when setting up any recommendation type in Yespo.

> 📘 Note
> 
> When setting up website recommendations in the Yespo admin panel, you can select the data source directly when configuring recommendations.

## Creating a Data Source in Account Settings

1\. Go to account settings:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe2035d46343c4c31e6dce875532676551f998523928a191d0f7b3d4806c7af0-e-7.webp",
        "",
        "Settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. In the menu on the left, select the section _Data sources_ and click _New data source_ → _Recommendations for messages or website_:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e4d2c59acc276f9c5b1cdf2d6bc871c3511a717f792507a862f7d6ef673f01f5-e-4.webp",
        "",
        "Recommendations for messages or website"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3\. Select a recommendation algorithm:

- Recommendations based on visitor data: The recommended products will be unique for each visitor. If the visitor is not authorized, bestsellers of all products will be displayed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e883bd4633597798cdf8d52e14382ee62d93c838224cbd65369796b76009a860-e-3.webp",
        "",
        "Recommendations based on visitor data"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Recommendations based on product data: for pages that show a product or a product category.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5dca91b0a783aebe39db9399ca65a7c053b51aae898e02b2205fc9f31d78c28a-e-5.webp",
        "",
        "Recommendations based on product data"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- General recommendation algorithms.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e68cd2f5e8a0f65f7c9b38b5b5b5dbd28a558ba8a53225041aff8f87fdc0e382-e-6.webp",
        "",
        "General recommendation algorithms"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In addition, you can add [custom filtering rules for the block](https://docs.yespo.io/docs/custom-filters-recommendation-blocks).

> 📘 Note
> 
> For email recommendations, use the following data sources:
> 
> - Abandoned cart (up to 6 products);
> - Recommendations for 6 abandoned products in the cart (up to 6 rec.);
> - Abandoned view (up to 6 products);
> - Recommendations for 6 abandoned views (up to 6 rec.);
> - Personal recommendations or bestsellers (up to 6 rec.) — for promo campaigns.
> 
> To find out which source is better to use for other triggered campaing types, please contact our support team at [support@yespo.io](mailto:support@yespo.io)

4\. Specify a unique source name, configure additional options below (optional), and click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a1f6908162358e2e37db48e6ae2217f259f3fee4fb798c4bcc3cea5f1221cc96-e-1.webp",
        "",
        "Craeating algorithm"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The created data source will appear in the general list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9b2043d204580cc4f2895ec7a520e86460abf9e7bab2251dd4244b67c1514e23-e-2.webp",
        "",
        "New data source"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can use the generated source when setting up recommendations for your site, app, and campaigns.