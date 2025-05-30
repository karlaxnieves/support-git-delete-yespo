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

> **Note**  
> Connect one of the [advanced features](https://yespo.io/segmentation-price) tariffs to use data about user behavior on the site in campaigns.

The feed upload function will become available after you generate a script for your site in the _Settings → Web tracking_ menu. You can switch between the _Upload feed_ and _Feed sample_ tabs.

![The window for loading product feed into the system](https://files.readme.io/ffd2cdd901bb414adeb19673fc6683d6ed40a7a4b388c0b3a10a43eeebcea619-image2.webp)

## Feed Requirements

The data must be in the [XML, RSS 2.0 format](https://support.google.com/merchants/answer/160589?hl=en) according to the [Google product specification](https://support.google.com/merchants/answer/7052112?hl=en). The file's MIME type must conform to: `application/xml`, `text/xml`, `application/rss+xml`, `application/xhtml+xml`.

![Feed sample](https://files.readme.io/4cd75e278445dca81c09df4e0d9acf881b27e4b1e2ebe4ff82625c8bcd6d7806-image12.webp)

> **Important**  
> Add as many product parameters as possible (size, color, material...) for better recommendation accuracy.

### Required Attributes

| Advanced                        | Pro                         |
|---------------------------------|-----------------------------|
| `&lt;g:id&gt;`                  | `&lt;g:id&gt;`              |
| `&lt;g:title&gt;`               | `&lt;g:title&gt;`           |
| `&lt;g:brand&gt;`               | `&lt;g:brand&gt;`           |
| `&lt;g:google_product_category&gt;` | `&lt;g:google_product_category&gt;` |
| `&lt;g:description&gt;`         | `&lt;g:description&gt;`     |
| `&lt;g:link&gt;`                | `&lt;g:link&gt;`            |
| `&lt;g:image_link&gt;`          | `&lt;g:image_link&gt;`      |
| `&lt;g:availability&gt;`        | `&lt;g:availability&gt;`    |
| `&lt;g:price&gt;`               | `&lt;g:price&gt;`           |
|                                 | `&lt;g:sale_price&gt;`      |
|                                 | `&lt;g:new&gt;`             |

## Feed Uploading

Click the **Upload a product data feed** button and fill out:

1. Default feed language  
2. Feed link  
3. Feed type  
4. Update frequency

![Feed settings](https://files.readme.io/ad2239ab0aeeeb3a94d1d0ca7df19097ca901ab88fc811af4c439ceef1ead0d5-image9.webp)

## Multilingual Feed

Language detection works automatically or can be set manually. Each feed version must be identical in structure but in a different language.

![Set the default feed language](https://files.readme.io/783efa575c68e7458e19218295d4d250133c295f2b524afefe61011d5bdc5a36-image7.webp)  
![Adding translated feed](https://files.readme.io/67a05597759331dfbcc825df127186c83f4d289132624ca7bd5f63dc98ea9b94-image14.webp)  
![Set language](https://files.readme.io/0bdf56fce6564511e374fa89521e41182a23f7278de60b4381084c7af741bdce-image11.webp)

## Updating Feed

You can choose:

- Daily updates  
- Weekly updates  
- Custom schedule (via support)

![Update frequency](https://files.readme.io/3d2529a3afffeba608ba7b008aaa159f5a2189c06bf0b71a830a4da198bafb25-image3.webp)

## Product Preview

View:

- Total products  
- Products in stock  
- Price = 0  
- Products without or with invalid categories

![Multilingual tabs](https://files.readme.io/05e79bb64f44f0127b40c12c71b692185eccef4232657023565ff5e33da0e1a5-product_data.webp)  
![Product view](https://files.readme.io/839435f924187cc81a998701264d0031f34ea907c0bdc21b10e76421c66ad614-image15.webp)  
![Search filter](https://files.readme.io/7a7805d2d46bfa699a3b3e22742c65ef251b5fed6ec330ce54b4fb46e39862ef-image4.webp)

## Manual Update

Click **Set up feed** → **Update feed now**

![Set up](https://files.readme.io/3eff6dad321e40bb8f380fd855713da0de7b4fab02985392dc02f87d328a8ca4-set-up-feed.webp)  
![Update now](https://files.readme.io/c39e8ba7db3ca4c739f83ae8817d1ba2f8e5fe87b2768d3537761edfcfe5dc8b-update_feed.webp)

## Common Errors

| Description                                  | Recommendation                                                                 |
|----------------------------------------------|---------------------------------------------------------------------------------|
| Resource not available                       | Ensure the resource is accessible via HTTP or HTTPS.                           |
| Unsupported file format                      | Only XML files are supported.                                                  |
| Missing parameters (e.g., `google_product_category`) | Use correct [Google spec](https://yespo.io/settings-ui/assets/files/product-feed-example.xml). |
| Internal service error                       | Contact support.                                                               |

![Error sample](https://files.readme.io/173ed851010817e8b10268852799131f5657b2ac0238d4d6e52235487554fb56-image8.webp)
