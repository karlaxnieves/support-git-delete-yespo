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

* [install the script](https://docs.yespo.io/docs/how-set-web-tracking-your-website) on the site to track the behavior of site visitors;
* [upload product data feed](https://docs.yespo.io/docs/importing-product-feed) to your Yespo account;
* [set up the recommendation algorithm](https://docs.yespo.io/docs/getting-api-recommendations) in your Yespo account.

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

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
      </th>

      <th>
        Type
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        variantId
      </td>

      <td>
        Required\
        String
      </td>

      <td>
        r262v361
      </td>

      <td>
        The unique ID of the recommendation variation in the Yespo account.
      </td>
    </tr>

    <tr>
      <td>
        productId
      </td>

      <td>
        Optional\
        String
      </td>

      <td>
        MX-1512\\42
      </td>

      <td>
        To pass the product ID from the page the user is on.  

        Required parameter for recommendations using the product algorithm (similar products, products that were bought together with some items); for other types of algorithms, it is not necessary to pass.
      </td>
    </tr>

    <tr>
      <td>
        productIds
      </td>

      <td>
        Optional\
        List
      </td>

      <td>
        ['123', '543534']
      </td>

      <td>
        To pass a product ID or an array of cart product IDs.  

        Required parameter for recommendations using the product algorithm (similar products, products that were bought together with some items); for other types of algorithms, it is not necessary to pass.
      </td>
    </tr>

    <tr>
      <td>
        categoryKey
      </td>

      <td>
        Optional\
        String
      </td>

      <td>
        Jackets
      </td>

      <td>
        To pass the key of the category the user is in.  

        Required parameter for recommendations using a categorical algorithm (personally for you in this category); for other types of algorithms, it is not necessary to pass.
      </td>
    </tr>

    <tr>
      <td>
        allFields
      </td>

      <td>
        Optional Boolean
      </td>

      <td>
        true\\false
      </td>

      <td>
        Parameter for determining which product attributes will be in the recommendation request: *All* (which are available in the product data feed) or only *Required:*\
          • *product\_id*\
          • *url*\
          • *container\_type*\
        Default parameter setting = false
      </td>
    </tr>
  </tbody>
</Table>

## Response Example

Upon successful submission of the request, you will receive a response similar to the following:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Response body
      </th>

      <th>
        Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **JavaScript**  

        ```
        [  
         {  
         "product_id": "02G439",  
         "container_type": "19534_r24v435",  
         "url": "https://…?sc_content=19534_r24v435"  
          // and other product attributes from the feed  
          }  
        ]
        ```
      </td>

      <td>
        `List<object>`
      </td>

      <td>
        •  product\_id - recommended product ID\
        • container\_type must be used when passing the event ProductImpression\
        • URL contains a link to the product, with an additional parameter for proper web tracking
      </td>
    </tr>
  </tbody>
</Table>

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

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
      </th>

      <th>
        Type
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        filters
      </td>

      <td>
        Optional\
        Object
      </td>

      <td>
         A parameter that includes filtering rules.
      </td>
    </tr>

    <tr>
      <td>
        include
      </td>

      <td>
        Optional\
        List
      </td>

      <td>
        Strict filtering: recommend only products according to the given parameters. For example, show only products of a certain brand.
      </td>
    </tr>

    <tr>
      <td>
        exclude
      </td>

      <td>
        Optional\
        List
      </td>

      <td>
        Strict filtering: products with specified parameters are not shown. For example, do not show discount items.
      </td>
    </tr>

    <tr>
      <td>
        should
      </td>

      <td>
        Optional\
        List
      </td>

      <td>
        Non-strict filtering: products with specified parameters\
        shown in priority, others by default\
        (if there should be 20 recommendations in the search results, 5 products with the specified parameters will be shown, the remaining 15 — without applying the filter). For example, include products from a new collection in recommendations.
      </td>
    </tr>

    <tr>
      <td>
        name
      </td>

      <td>
        Required\
        String
      </td>

      <td>
        The name of the product parameter from the product feed.
      </td>
    </tr>

    <tr>
      <td>
        values
      </td>

      <td>
        Required List
      </td>

      <td>
        List of values to filter. The comma in values is the OR operator (values: ['Kiev','Kharkiv']).
      </td>
    </tr>
  </tbody>
</Table>

You can also define a field (parameter) by which product categories will be filtered in the feed for display in recommendations. To do this, specify the desired *categoryField* value in the request.

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