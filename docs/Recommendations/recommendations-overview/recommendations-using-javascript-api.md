---
title: JS API Requests for Different Site Page Types
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: JS API Requests for Different Site Page Types | Yespo Guide
  description: >-
    To use Yespo's product recommendations, install a tracking script, upload a
    product feed, and configure algorithms in Yespo, with options to customize
    filters via the JavaScript API.
  robots: index
next:
  description: ''
---
In order to use Yespo product recommendation algorithms and customize their display on your side (appearance of blocks, display pages, etc.), follow these steps:

- [install the script](https://docs.yespo.io/docs/how-set-web-tracking-your-website) on the site to track the behavior of site visitors;
- [upload product data feed](https://docs.yespo.io/docs/importing-product-feed) to your Yespo account;
- [set up the recommendation algorithm](https://docs.yespo.io/docs/getting-api-recommendations) in your Yespo account.

## Examples of Requests

### On the Home Page and 404 Page

```javascript
eS('getRecommendations', {
  'variantId': 'r554v778'
  }, function(error, products) {

  if (error) {
            console.error(error);
            return ;
        }

});
```

### On the Product Page

```javascript
eS('getRecommendations', {
  'variantId': 'r554v778',
  'productId': 'MX-1512\42'
  }, function(error, products) {

  if (error) {
            console.error(error);
            return ;
        }

});
```

### On the Cart Page

```javascript
eS('getRecommendations', {
  'variantId': 'r554v778',
  'productIds': ['123', '543534']
  }, function(error, products) {

  if (error) {
            console.error(error);
            return ;
        }

});
```

### On the Cart Pop-up

Use the StatusCartPage event to determine the page type and display recommendations on the cart pop-up. Example:

```javascript
eS('sendEvent', 'StatusCartPage');
```

### On the Categories Page

```javascript
eS('getRecommendations', {
  'variantId': 'r554v778',
  'categoryKey': 'cK'
  }, function(error, products) {


  if (error) {
            console.error(error);
            return ;
        }
});
```

The JS API method is asynchronous, which allows not to wait for the execution of other functions on the site.

## Request Parameters

[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Type",
    "h-2": "Example",
    "h-3": "Description",
    "0-0": "variantId",
    "0-1": "Required  \nString",
    "0-2": "r262v361",
    "0-3": "The unique ID of the recommendation variation in the Yespo account.",
    "1-0": "productId",
    "1-1": "Optional  \nString",
    "1-2": "MX-1512\\\\42",
    "1-3": "To pass the product ID from the page the user is on.  \n  \nRequired parameter for recommendations using the product algorithm (similar products, products that were bought together with some items); for other types of algorithms, it is not necessary to pass.",
    "2-0": "productIds",
    "2-1": "Optional  \nList",
    "2-2": "['123', '543534']",
    "2-3": "To pass a product ID or an array of cart product IDs.  \n  \nRequired parameter for recommendations using the product algorithm (similar products, products that were bought together with some items); for other types of algorithms, it is not necessary to pass.",
    "3-0": "categoryKey",
    "3-1": "Optional  \nString",
    "3-2": "Jackets",
    "3-3": "To pass the key of the category the user is in.  \n  \nRequired parameter for recommendations using a categorical algorithm (personally for you in this category); for other types of algorithms, it is not necessary to pass.",
    "4-0": "allFields",
    "4-1": "Optional Boolean",
    "4-2": "true\\\\false",
    "4-3": "Parameter for determining which product attributes will be in the recommendation request: _All_ (which are available in the product data feed) or only _Required:_  \n  • _ product_id_  \n  • _ url_  \n  • _container_type_  \nDefault parameter setting = false"
  },
  "cols": 4,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


## Response Example

Upon successful submission of the request, you will receive a response similar to the following:

[block:parameters]
{
  "data": {
    "h-0": "Response body",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "**JavaScript**  \n  \n`[  \n {  \n \"product_id\": \"02G439\",  \n \"container_type\": \"19534_r24v435\",  \n \"url\": \"https://…?sc_content=19534_r24v435\"  \n  // and other product attributes from the feed  \n  }  \n]`",
    "0-1": "List<object>",
    "0-2": "•  product_id - recommended product ID  \n• container_type must be used when passing the event ProductImpression  \n• URL contains a link to the product, with an additional parameter for proper web tracking"
  },
  "cols": 3,
  "rows": 1,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


> 📘 Important
> 
> Don’t edit the return value in the URL field for web tracking to work correctly.

### Error Example

| Example                                    | Type   | Description                                          |
| :----------------------------------------- | :----- | :--------------------------------------------------- |
| variantId r262v361 was not found in config | String | No such recommendation variant identifier was found. |

> 📘 Important
> 
> Send the [ProductImpressions](https://docs.yespo.io/docs/transferring-website-behavior-data-via-javascript-requests) event after calling and displaying the recommendations block for proper tracking.

## Filtering Recommendations

Filtering recommendations through the JavaScript API allows you to show products on your site by filtering recommendations based on data from the feed or contact information stored on your side. For example, you can filter recommendations by the city of residence, clothing size, favorite brand, promotional offer, etc.

Filtering recommendations through JS API saves you from changing the filtering rules in the data source in Yespo account every time.

Request format:

```javascript
eS('getRecommendations', {
    variantId: 'r362v614',
                'filters': {
                       'include': [{'name': 'city', values: ['Kiev','Kharkiv']}]
                }
  },
  function(error, products) {
    if (error) {
      console.error(error);
      return;
    }
  }
);
```

Request parameters:

[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "filters",
    "0-1": "Optional  \nObject",
    "0-2": " A parameter that includes filtering rules.",
    "1-0": "include",
    "1-1": "Optional  \nList",
    "1-2": "Strict filtering: recommend only products according to the given parameters. For example, show only products of a certain brand.",
    "2-0": "exclude",
    "2-1": "Optional  \nList",
    "2-2": "Strict filtering: products with specified parameters are not shown. For example, do not show discount items.",
    "3-0": "should",
    "3-1": "Optional  \nList",
    "3-2": "Non-strict filtering: products with specified parameters  \nshown in priority, others by default  \n(if there should be 20 recommendations in the search results, 5 products with the specified parameters will be shown, the remaining 15 — without applying the filter). For example, include products from a new collection in recommendations.",
    "4-0": "name",
    "4-1": "Required  \nString",
    "4-2": "The name of the product parameter from the product feed.",
    "5-0": "values",
    "5-1": "Required List",
    "5-2": "List of values to filter. The comma in values is the OR operator (values: ['Kiev','Kharkiv'])."
  },
  "cols": 3,
  "rows": 6,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


You can also define a field (parameter) by which product categories will be filtered in the feed for display in recommendations. To do this, specify the desired _categoryField_ value in the request.

Example request:

```javascript
eS('getRecommendations', {
    variantId: 'r1673v2111',
		categoryKey: 'BATHROOM',
    categoryField:'tags_all_category_names'
  },
  function(error, products) {
    if (error) {
      console.error(error);
      return;
    }
  }
);
```

where `tags_all_category_names` guarantees a search across all values in the category tree.

To set the appearance of recommendation blocks in Yespo, please read [this guide](https://docs.yespo.io/docs/creating-recommendation-block).