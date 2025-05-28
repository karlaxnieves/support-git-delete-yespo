---
title: Creating Recommendation Block
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating Recommendation Block | Yespo Guide
  description: >-
    Product recommendations increase your website conversion by showing visitors
    the relevant items. Learn how to create product recommendations and add them
    to your website without code disruption.
  robots: index
next:
  description: ''
---
This guide describes creating a recommendation block in the Yespo account — a customization option for sites based on templating engines and projects without resources for designing on their own.

To create a block, go to _Site → Recommendations_ and click _New recommendation_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1e8ad2553ae61016b5db613290fa14bd0575e7f1e24cc652d4ec338c87f8c78e-image3.webp",
        null,
        "New recommendation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 1. Getting Recommendation

Select the _Out the box_ option.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af0dfff5693df11b66ec604e0eda7f3a5023572da3529983e1537b54a7e09dfb-image8.webp",
        null,
        "Out the box"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 2. Page Type

Choose the page type for recommendation placement:

- Main page;
- Category page;
- Product page;
- Cart page;
- 404 page;
- Any page.

Each type has specific algorithms for product selections, for example, best-selling products for the main page or personalized recommendations for the category page, etc.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/100ef2960b1d5247dd2ec2eb76cd4ac30d9aed0dbe30ee7000782f240f621cde-image4.webp",
        null,
        "Page types"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you choose no type and click _Next_, you’ll be directed to the main page settings by default.

## 3. Data Source

Data sources contain the algorithms for products that will be shown in the recommendations. Select a data source from the list. You can also [add custom filter rules](https://docs.yespo.io/docs/custom-filters-recommendation-blocks) for the block.

## 4. Recommendation Block Name

Enter the recommendation name and description. The name is used within the system to find the recommendation. Website visitors will not see it.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19ecbd875a4c47e6564bba24fa9daed0ad0119283b777d4dd761fb58d6ad7232-image12.webp",
        null,
        "Name and description of the recommendation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 5. Appearance

Set up the block appearance, which consists of the following:

- the title that will be displayed on your site;
- selections of recommendations that look like product cards.

The title is displayed above the block. Its task is to attract users' attention and tell what products are presented. Write it in the appropriate field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9693b90460fef3834ec3f132b1328514be5cbbdee7c64ba17084779de173aadb-image11.webp",
        null,
        "Product card templates"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The next step is to choose the block’s design. You can choose one of the ready-made templates or upload your HTML code with CSS styles and JS settings.

### Creating a block in your website style

So that you have a block in your website style in the available appearances, download its code in the _Site → Recommendations → Appearance_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5a11ab4affde78d3a14b52e98e8ec1e7367428fa55046b9c75ef14ca493b898-image5.webp",
        null,
        "Appearance"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the _New appearance_ button to open the code editor and customize the recommendation block. Settings are made in the HTML, CSS, and JS tabs.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2106b4fecbb46ca8e523622fcde91a1c4f14a17eb485c1e2b2114116fb2a2581-image9.webp",
        null,
        "Code editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### HTML

We recommend adding only the content of the _body_ tag to the HTML tab.

If using a limited-width template, ensure your site has enough space.

Data is rendered using [Velocity dynamic content](https://docs.yespo.io/docs/introduction-to-velocity).

To display the header, add a class with reference to `$!recom.header`, for example:

```html
$!recom.header
```

All recommendation containers must be nested inside a loop, for example:

```html
#foreach( $!product in $!products )


//recommendation container


#end
```

Source variables like `name` must be accessed via the `$!product.name` structure. The list of standard variables is displayed in the prompt if you start entering `$!pr`; all other (custom) feed fields are accessed via tags\_, for example:

```html
$!product.tags_oldprice
```

Using Velocity, you can specify a condition for displaying a value, for example, display an element only if the field's value is equal to or not equal to the specified value. For example, if the _Description field_ from the feed is not empty, to display the _Description_ button, place its structure in the construction:

```html
#if ($!product.descr != '')
$!product.get('descr')


#end
```

An example of recalculating the value of the product taking into account the old and new price:

```html
#set($saleDiff = $product.tags_oldprice – $product.price)


#if($saleDiff > 0)


– $saleDiff грн.


#end
```

An example of a product rating display – 1-5 stars (must be supported in CSS):

```html
#set($filled = '') #set($notFilled = '') #set($start = 1) #set($end = 5) #set($range = [$start..$end]) #foreach($i in $range) #if ($i <= $product.tags_rating) $filled #end #if ($i > $product.tags_rating) $notFilled #end #end
```

#### CSS

Since the recommendations will be embedded in the site, the site's styles may affect the styles of the recommendations. To avoid this, use unique classes (for example, a specific class prefix that is not used elsewhere on your site):

```html
.es-productsContainer--link
```

If this is not enough, you need to strengthen the weight of the selector with an intermediate class, for example:

```html
.es-productsContainer.es-productsContainer--link
```

Use some content when creating a new style sheet. This will help you quickly find the pieces of code you need when there is a lot of code. Example:

```html
/* Container styles start */
```

To create the same CSS rule for multiple elements, put it in a separate class.

#### JS

Use JS code to customize the recommendation block's advanced features, such as animations, sliders, etc.

## 6. Placement of the Block

By default, there are no ready places to place recommendations. First, create placements, then return to their selection ([instructions for creating placement](https://docs.yespo.io/docs/placement-recommendations-webpage)).

Therefore, select the _Create placement later_ option and click the _Done_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ee139810efeb62707d5f6088773b3da0a9db60953dcf9bcb97510073382c3975-image2.webp",
        null,
        "Choosing a placement"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## 7. Testing and Publication of the Block

Select the created recommendation. At this stage, it is visible only to you.

To publish or view the created block on the page, specify its placement in the _Placement_ field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0140324aa7852ed29d3c12ab89020c14913b2f6e2eba90c12ff19565bf38fdc9-image6.webp",
        null,
        "Placement"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


<br />

Click _View on page_ to see how the block will be displayed on the website.

When you ensure the block layout is correct and the products are pulled up correctly, change the recommendation status from _Visible only to you_ to _Visible to website visitors_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cdce751cda4a9a9866107677ab443e9e3748f9de2ed264fccbf0f9c07e0b4abb-image10.webp",
        null,
        "Publish the recommendation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


From that moment on, all website visitors see recommendations, and the system starts to collect statistics on its operation.

## 8. Block's Displaying in Account

You can use the following tools to sort out your recommendations:

1. Search by recommendation name, placement name.
2. Filtering by page type. By switching pages on the left, you see only recommendations on the selected page. The color of the placement font in the list corresponds to the color of the page marker on the left. For example, placements on the main page are in purple, on the category page – in pink, etc.
3. Filtering by date.
4. Filtering by statistics.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fc40c882e299b6108d0404fa10d0d14f7d9d72e5fd9a8fbdf20c056ff84d9fd5-creating-recommendation-block-001.webp",
        null,
        "How to sort out recommendations"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After publishing the recommendation on the site, the statistics on it will be given in the list:

- Views;
- Clicks;
- CTR (click-through rate);
- Purchases (transactions);
- Conversion rate;
- Item quantity;
- Purchase amount;
- Average order value.

[Instructions for working with analytics](https://docs.yespo.io/docs/recommendation-block-analytics)

The start icon beside the recommendation indicates it is displayed on the site. The crossed eye icon indicates that the recommendation is visible only to you.

Click the ellipsis (three dots) on the right-hand side to delete a recommendation.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/086a53fa6826963f4de6051ca7d101ec1f63fd6db9d8d348b154cc0ef196c660-creating-recommendation-block-002.webp",
        null,
        "Recommendation status and deletion"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]