---
title: Products Block
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Products Block | Yespo Guide
  description: >-
    Learn how to add and configure a product recommendation block in an email,
    including setting options like the number of product cards, rows, spacing,
    and data sources.
  robots: index
next:
  description: ''
---
Use the _Products_ block to configure and visualize recommended products in the email.

Before working with the block, you need to:

1. Connect one of the [advanced features](https://yespo.io/segmentation-price) pricing plans
2. Set up [web tracking](https://docs.yespo.io/docs/web-tracking-overview)
3. Create [a data source for recommendations](https://docs.yespo.io/docs/create-data-source-recommendations)

> ❗️ Important
> 
> The Products block is available when you have at least one [order](https://docs.yespo.io/docs/orders-1) in your account.

## Block Configuration

To add the _Products_ block to the email content, drag and drop it to the content area.

> 📘 Note
> 
> A block with default settings will be used in the message if you have not set up web tracking and created a data source for recommendations

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ebd6dbf94238dc6c2b282f4890f12ba11e6d5c4a2a73ddcf93d1dad9b4ddd45-products-01.gif",
        "Products block",
        "Products block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the block in the message container. The following tabs will open on the sidebar:

- Product list
- Modules
- Data

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3ef1ec4024a8438e42c7c3420fa1bd57f5c2490f48f4c64cae96041eeb34c7c2-product-block-menu11.png",
        "Products block tabs",
        "Products block tabs"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Let's consider the configuration of each tab in detail.

### Product List

Configure the number of product cards in the block and their alignment, placement, padding, and background.

#### Number of products in a row

Set the number of products to display in a single row (1 to 4).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/799f655d1a563f5e624e8748950d7a5f5e480b725b77b219b81d223e8e66d3b7-products-in-row3.png",
        "Number of products in a row",
        "Number of products in a row"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To set the number of products in a row for the mobile version:

1. Click the _Mobile version_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/862a340bebffa6ed91482bb6ffe46227a54c2a06491ba50662f57a6ea2bdfce5-mob-version-products-in-row.png",
        "Number of products in a row",
        "Mobile version button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select the _number of products_ to display in one row (from 1 to 3) for the mobile version.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a19450a159115bd0578faa69223ed772afa51353f93bd11f46f720ba05d3849d-mob-version-products-in-row-select.png",
        "Number of products in a row",
        "Number of products in a row"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The message preview in the editor is displayed only for the desktop version. To see how the message will be displayed in the mobile version, click the _View message_ button on the top panel.

#### Number of rows

Enter the number of rows with products in the _Up to_ parameter.

> 📘 Note
> 
> Possible values range from 1 to 50 rows. If there are not enough products to fill all the rows, the system may display only 1 row.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/790e14fad73d98c0404e5e81ce8cf2d20e7e4758b11ff20159a920b7c82a0a2a-up-to-rows-en2.png",
        "Number of rows",
        "Number of rows"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To show all the products available in the data source, select the _Show all products_ radio button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f9ec3d99aa3f194a77de11998f7d0a19ad3c26f020e4435d1260bdcf4f357990-show-a11-en.png",
        "Show all products",
        "Show all products"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### If there are not enough products to fill the last row

Choose one of the options:

- **Don't show partially filled row**: If the last row of product cards contains fewer cards than the value you selected in the Number of products in a row section, then this row is not displayed for the recipient.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b0871fd70ac40befd09aaca70b425ba5b25007cea8b22368abaa0042da46056e-partially-filled-dontshow-en.png",
        "Don't show partially filled row",
        "Don't show partially filled row"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- **Show partially filled row**: The last row of product cards is displayed for the recipient, even if it contains fewer cards than the value you selected in the Number of products in a row section. 

Set the alignment of cards in the last row for the second option: center, left edge, right edge, or adjust to width.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/26f6086d18271a0f01aeeb8a0dafdc4cd1423752956cca8e1292dbead1ce5b88-show-partially-filled-en2.png",
        "Show partially filled row",
        "Show partially filled row"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### If there are no products to show

In this case, choose one of these options:

- **Do not send the message**: Default setting. The message will not be sent if there are no products to show.
- **Hide product list**: The message will be sent, but the content of the Products block will not be displayed for the recipient.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18a184f1e5298397203e55b1b5e24b323e61bd3441f63723e51ee629045b44b9-products-08.webp",
        "If there are no products to show",
        "If there are no products to show"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If the message contains multiple _Products_ blocks, you can set separate conditions for each block.

For example, the first block shows items in the abandoned cart, and the second one shows recommendations based on the items in the cart. If you select the Hide product list option for the second block, it will not be displayed in the message if there are no recommendations. The header and the footer of this block will not be displayed as well.

#### Indent options

Set indents between cards and rows.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/21a2af97962cf2d8f43213ae1608c6531f43c5cc115c60284903668f378731e1-idents-cards-rows.png",
        "Idents between cards and rows",
        "Idents between cards and rows"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Row background and rounding

Select the _background color_ for the rows from the palette, or enter the _hexadecimal code_ that corresponds to the desired color. By default, the row background is transparent.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/14d1ff0d18ff5c8d064335f366ab81f1ba5551502efd012eacc86692d056cf01-row-background.png",
        "Row background",
        "Row background"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Enter the row rounding value for all rows. The maximum value is 50.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bc68e0e3e5f047d5f05b33d6865cb67568180d6673c2752c98036577599f720-row-rounding.png",
        "Row rounding",
        "Row rounding"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To select the rounding value for each corner separately:

1. Enable the _Separately_ slide button.
2. Enter or select the required value for each corner. The maximum value is 50.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79105572479a51b4e4dafd48518e56549f391a510495c41a50c9839c31e8ab09-row-rounding-separately.png",
        "",
        "Row rounding separately for each corner"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Block background

By default, the block background is transparent. To change it, click the corresponding field and select a color from the palette or enter the hexadecimal code corresponding to the required color.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/26e12573acd7f606975f314e945708a80ff947cea52b63cadc047a111eaf4af8-block-background.png",
        "Block background",
        "Block background"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Products paddings

Set up paddings around the _Products_ block content for the desktop and mobile versions.

You can set all the padding at once, or configure each side of the block individually.

Activate the _More toggle_ button to set individual values and specify the desired parameters.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1703e3bb00daaf9b25a2b7d3bd7cbd18f15c08e467c73817afdcf478ca4fe34b-product-paddings.png",
        "Paddings around the Products block",
        "Paddings around the Products block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The maximum padding and indent value is 40 px

Click on the smartphone icon to set the padding around the block for the mobile version of the email.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cb8fec28ac30be7935cc08b43e689fd8c6292beeae22bb977a5d5cc13d15db17-product-paddings-mobile.png",
        "Padding around the block for the mobile version",
        "Padding around the block for the mobile version"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Modules

Configure the display or replace headers, footers, and product cards.

The principle for changing elements in the tab is the same. For example, let's consider replacing _Product cards_.

1. Click the _Replace_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cfd58b394e4ed763bc73717aa36c5e5931030765e6db320029f5ff0553421910-modules-replace-en.png",
        "Replace button",
        "Replace button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select a product card from the list or use the search field by name or tag.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a2b048fd32744945c954025d241ab2a615578b2d004a5e8e194133333ca5487-products-14.webp",
        "Select product card",
        "Select product card"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Headers and footers are optional elements of the _Products_ block, so they can be hidden by deactivating the corresponding switches.

_Header before product_ cards is enabled by default.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a49bd2d15fecd5a4c75ea6e2c1e218dc44a4248c19c6bd7b3fa3792665ae2f4-headers-footers-en.png",
        "Headers and footers",
        "Headers and footers"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The header and footer will be hidden if there are no products to display in the block, even if their visibility is activated.

[More about setting up and creating modules >](https://docs.yespo.io/docs/module-library)

### Data

Select a data source and configure the automation for displaying products in the message.

There are two types of data sources for the _Products_ block:

- Recommendations based on contact data
- General recommendation algorithms

The _Bestseller type algorithm_ is set in the _Products_ block by default. If there is no _Bestseller type algorithm_, any of the general recommendation algorithms will be applied. If no general recommendation algorithms are available, then the algorithms based on contact data recommendations are set.

To replace the data source, click the _Replace_ button and select the necessary one.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9b2911fa55d85a549b71a512b9c0152518726505a5eec80a945199b55132b278-datasource-replace-en.png",
        "Replace the data source",
        "Replace the data source"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> When you change the data source, the changes are not applied in the editor. To view the actual message, select the _View message_ icon on the top panel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/419457c1b3bad7dcbb5db73829c7a409735913450e069dd004c19b4229f8d4c0-view-message-en.png",
        "View message",
        "View message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the _Go to_ _data sources_ button to create a new one.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0e94edfd087c9ecb61974fc90ea0bcabc7de281e2f6a3f4728d0abebaa4726a6-goto-datasources-en.png",
        "Go to data sources",
        "Go to data sources"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the _Save_ button on the editor's top panel to save the email changes.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e40689b9d69acec934f634f8694d45aea4e8217132a4cd6bd6cd2d9179b6c7b-products-19.webp",
        "Go to data sources",
        "Save the email changes"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> - To display the product's old and new costs in the cards, we recommend using [the additional _Price_ component](https://docs.yespo.io/docs/using-the-price-block), which synchronizes the price data from the site with the data in the email.
> - [This instruction](https://docs.yespo.io/docs/editing-cards-products-block) describes editing and saving product cards of blocks in the module library.