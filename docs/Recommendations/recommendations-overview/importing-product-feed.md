---
title: Importing a Product Feed
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Importing a Product Feed | Yespo Guide
  description: >-
    The document outlines the process of using a product feed to create
    personalized messages and recommendations based on user behavior and
    detailing the setup of web tracking
  robots: index
next:
  description: ''
---
We use a product feed to generate personalized messages and product recommendations based on user behavior on the site. You can import the feed to your account after [setting up web tracking](https://docs.yespo.io/docs/web-tracking-overview).

> 📘 Note
> 
> Connect one of the [advanced features](https://yespo.io/segmentation-price) tariffs to use data about user behavior on the site in campaigns.

The feed upload function will become available after you generate a script for your site in the _Settings → Web tracking_ menu. You can switch between the _Upload feed_ and _Feed sample_ tabs.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ffd2cdd901bb414adeb19673fc6683d6ed40a7a4b388c0b3a10a43eeebcea619-image2.webp",
        "",
        "The window for loading product feed into the system"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Feed Requirements

The data must be in the <a rel="nofollow" href="https://support.google.com/merchants/answer/160589?hl=en" target="_blank">XML, RSS 2.0 format</a> according to the <a rel="nofollow" href="https://support.google.com/merchants/answer/7052112?hl=en" target="_blank">Google product specification</a>. The file's mime type must conform to the XML specification application/xml, text/xml, application/rss+xml, application/xhtml+xml. In the right tab, you can see an example:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4cd75e278445dca81c09df4e0d9acf881b27e4b1e2ebe4ff82625c8bcd6d7806-image12.webp",
        "",
        "Feed sample"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


<br />

> 📘 Important
> 
> We recommend adding as many product parameters as possible to the product feed: size, color, accessory, material, etc. This directly affects the accuracy of the recommendation selection. The more diverse parameters a product feed contains, the more relevant products the message recipient or site visitor will see.

A list of required product attributes depends on which [advanced segmentation plan](https://yespo.io/segmentation-price) you use in Yespo.

| Advanced                       | Pro                          |
| :----------------------------- | :--------------------------- |
| \<g:id>                        | \<g:id>                      |
| \<g:title>                     | \<g:title>                   |
| \<g:brand>                     | \<g:brand>                   |
| \<g:google\_product\_category> | \<g:google_product_category> |
| \<g:description>               | \<g:description>             |
| \<g:link>                      | \<g:link>                    |
| \<g:image\_link>               | \<g:image_link>              |
| \<g:availability>              | \<g:availability>            |
| \<g:price>                     | \<g:price>                   |
|                                | \<g:sale_price>              |
|                                | \<g:new>                     |

You may need to add attributes to configure some triggers and recommendations on the site. To correctly identify them in the feed, please contact our support team at [support@yespo.io](mailto:support@yespo.io).

## Feed Uploading

Click on the _Upload a product data feed_ button to open the settings window:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ad2239ab0aeeeb3a94d1d0ca7df19097ca901ab88fc811af4c439ceef1ead0d5-image9.webp",
        "",
        "Feed settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Fill in the following information:

1. The default feed language.
2. Feed link.
3. Feed type (Product data type is set by default).
4. Update frequency.

### Multilingual feed

If you have several language versions of your website and communication with customers in campaigns [in different languages](https://docs.yespo.io/docs/multilanguage-overview), add other feed language versions. The language of [product recommendations on the site](https://docs.yespo.io/docs/recommendations-overview) may also depend on feed language versions.

Language detection occurs automatically if you add an optional language parameter to the feed according to the Google specification. If it is missing, you can configure the settings manually by clicking on the globe icon in the field where you need to enter the feed URL. Specify the default feed language here.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/783efa575c68e7458e19218295d4d250133c295f2b524afefe61011d5bdc5a36-image7.webp",
        "",
        "Set the default feed language"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After that, the option to download another version will become available.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/67a05597759331dfbcc825df127186c83f4d289132624ca7bd5f63dc98ea9b94-image14.webp",
        "",
        "Adding translated feed"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The feed should be the same in content and structure, only in a different language. After specifying a link to the location of the feed, set the language value for it, too, by clicking on the globe icon again:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0bdf56fce6564511e374fa89521e41182a23f7278de60b4381084c7af741bdce-image11.webp",
        "",
        "Setting the language for different feed versions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you use [multilingual messages](https://docs.yespo.io/docs/creating-multilingual-messages), the substitution of the feed data into the email will depend on three parameters:

- primary message language;
- availability of the feed language versions;
- the language recorded [in the contact card](https://docs.yespo.io/docs/adding-the-preferred-language-to-the-user-profile).

For example, German is the default language for multilingual messages, and there are also versions of messages in Ukrainian and English. At the same time, feeds are loaded only in UK and ENG, the latter is set by default. In this case, messages will be sent as follows:

[block:parameters]
{
  "data": {
    "h-0": "Contact languages",
    "h-1": "Message languages",
    "h-2": "Feed languages",
    "h-3": "Result",
    "0-0": "UK or ENG",
    "0-1": "",
    "0-2": "",
    "0-3": "The contact will receive a message in the corresponding language with product substitution in the same language",
    "1-0": " DE",
    "1-1": "",
    "1-2": "",
    "1-3": "Will not receive a message because there is no feed on DE",
    "2-0": "Not specified",
    "2-1": "DE, UK, ENG  \nPrimary:  DE",
    "2-2": "UK, ENG  \nPrimary: ENG",
    "2-3": "Will not receive a message, because the DE feed, which is not in the system, should also be pulled into the main version of the message (DE)",
    "3-0": "ESP  \n(or any other language other than the language of messages)",
    "3-1": "",
    "3-2": "",
    "3-3": "Will not receive a message, because the DE feed, which is not in the system, should also be pulled into the main version of the message (DE)"
  },
  "cols": 4,
  "rows": 4,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


> 📘 Important
> 
> Always set the same default language for message and feed.

By default, only the product feed can be uploaded to the system. If you need to work with other feeds, such as news or promotions, order their setup from Yespo support specialists.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8b93f1f47a115f0e91672701f12620734eb4c099bf3fd05a0947c91173b9bed3-image1.webp",
        "",
        "Request custom feed"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Setting update frequency

The feed update frequency is the same for all its language versions. When setting up a schedule, choose one of three options:

- Every day at a certain time;
- Every week on a specific day and time;
- Another period — selecting this option will open a chat window with our support, where you can order a special feed update schedule.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3d2529a3afffeba608ba7b008aaa159f5a2189c06bf0b71a830a4da198bafb25-image3.webp",
        "",
        "Update frequency"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When setting the feed update frequency in Yespo, build on the actual update of your product list.

You can download the feed instantly or schedule a time (e.g., if you set up web tracking in the morning, but you have a product feed update scheduled at 20:00).

### Checking the correctness of the feed and product preview

After a successful feed downloading, the following data will appear:

- the number of products in the feed;
- products in stock;
- products with a price equal to 0;
- products with non-existent categories (for example, you have category 1, category 2, category 3, and some products are assigned categories 4-7 that do not exist);
- products that do not have a category.

The number of products with a price equal to 0, with non-existent categories, without categories should tend to zero.

If you have added a multilingual feed, you will have several tabs with different versions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/05e79bb64f44f0127b40c12c71b692185eccef4232657023565ff5e33da0e1a5-product_data.webp",
        "",
        "Multilingual feed"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To make sure that the product data has been pulled up correctly, click the _View products_ button.

In addition to invalid product groups, here you can see all feed positions or create a specific segment for viewing. For example, products in the category _Jackets_:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/839435f924187cc81a998701264d0031f34ea907c0bdc21b10e76421c66ad614-image15.webp",
        "",
        "Product feed view"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Missing product information will be marked in red. Use the upper left corner filter to display error data for the required parameter. The filter helps to find products with errors by:

- Product ID;
- Product Name;
- Product Brand;
- Product URL;
- Product Price;
- Product Category;
- Product in Stock;
- Product Image.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a7805d2d46bfa699a3b3e22742c65ef251b5fed6ec330ce54b4fb46e39862ef-image4.webp",
        "",
        "Search filter"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To get to the settings page where you previously added a feed and set the frequency of its updates, click the _Set up_ feed button in the general web tracking settings section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3eff6dad321e40bb8f380fd855713da0de7b4fab02985392dc02f87d328a8ca4-set-up-feed.webp",
        "",
        "Set up feed"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the _Update feed now_ button to update the feed without waiting for the time specified in the settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c39e8ba7db3ca4c739f83ae8817d1ba2f8e5fe87b2768d3537761edfcfe5dc8b-update_feed.webp",
        "",
        "Update feed now"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Possible mistakes

A feed may be invalid if there are errors in the structure. In this case, it will not load, and an error will appear with a description of what needs to be done:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/173ed851010817e8b10268852799131f5657b2ac0238d4d6e52235487554fb56-image8.webp",
        "",
        "Product feed error notification"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You may also encounter other errors when loading a feed. List of the most common ones:

[block:parameters]
{
  "data": {
    "h-0": "Description",
    "h-1": "Recommendation",
    "0-0": "The resource is not available at the specified URL",
    "0-1": "The resource must be accessible via HTTP or HTTPS",
    "1-0": "Unsupported file format",
    "1-1": "Only XML files are supported",
    "2-0": "Some products are missing required parameters:  \n  \n- google_product_category\n- product_type",
    "2-1": "The product feed must conform to one of the <a rel=\"nofollow\" href=\"https://support.google.com/merchants/answer/160589?hl=en&ref_topic=2473799\" target=\"_blank\"> Google RSS 2.0 XML specifications</a>  \n  \n[Look at the feed example](https://yespo.io/settings-ui/assets/files/product-feed-example.xml) ",
    "3-0": "Internal service error",
    "3-1": "Contact support"
  },
  "cols": 2,
  "rows": 4,
  "align": [
    "left",
    "left"
  ]
}
[/block]


When using a multilingual feed, errors can only be detected in certain versions of it. In this case, the tab with such a feed will be highlighted in red. This version will not affect other feeds, and you will only need to fix the bug in this version. If you receive an error notification, follow the recommendations, make the necessary changes, and re-upload the feed. Up to this point, the previously successfully uploaded version will be used or nothing if the addition is the first.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5829f53556058600721bdd7884a3c26905fdb5bd4c80f64b641ae2baadf856b7-germ.webp",
        "",
        "Errors in the feed language versions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]