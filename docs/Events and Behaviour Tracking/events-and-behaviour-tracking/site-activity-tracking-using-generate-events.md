---
title: Site Activity Tracking Using Generate Event
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Site Activity Tracking Using Generate Event | Yespo Guide
  description: >-
    Learn how to track site activity effectively using the Generate Event
    feature. Discover step-by-step guidance to monitor user interactions, gain
    valuable insights, and optimize your website’s performance.
  robots: index
next:
  description: ''
---
You can pass and save events from your website from your backend system directly to our system using the [Generate event v2](https://docs.yespo.io/reference/registerevent_1) method. Also, if you configured integration with a recommendation system, you can save the data in both services.

To make a request, send the following parameters in the request body to `https://yespo.io/api/v2/event`:

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Description",
    "0-0": "eventTypeKey",
    "0-1": "Required parameter. Event type ID key. If no such event type exists with such a key, a new one is created.",
    "1-0": "keyValue",
    "1-1": "Optional. The key of the event, which determines its uniqueness. If you don't pass a keyValue's value in the event, it is automatically taken from the request's Params object with such a priority:  \n• contactId;  \n• externalCustomerId;  \n• email;  \n• phone;  \n• pushToken (web or mobile).  \n  \nAn event without one of these parameters or a passed keyValue value is not accepted.",
    "2-0": "params",
    "2-1": "List of event parameters represented as an array of \"key\" - \"value\" pairs. The parameter keys are arbitrary."
  },
  "cols": 2,
  "rows": 3,
  "align": [
    "left",
    "left"
  ]
}
[/block]


You can pass the following events:

| Event                  | Description                                             |
| :--------------------- | :------------------------------------------------------ |
| pageViewed             | View of the page.                                       |
| productViewed          | View of the product card.                               |
| productCategoryViewed  | View of the product category.                           |
| cartUpdated            | Change of the cart items.                               |
| productImpressions     | Product recommendations displayed to your site visitor. |
| productAddedToWishlist | Your site visitor added a product to the wishlist.      |
| searchRequest          | Data about product searches.                            |

### pageViewed

The event is sent when a contact views any page or opens a mobile deep link.

The request example is given below. It contains the following parameters:

| Parameter | Type   | Description                                                                     |
| :-------- | :----- | :------------------------------------------------------------------------------ |
| phone     | String | Phone number in the international format. Locator to map an event to a contact. |
| email     | String | Email address. Locator to map an event to a contact.                            |
| page      | String | Page location. Required to create an event.                                     |
| location  | String | Page URL or deep link. Required to create an event.                             |

**Example:**

```json
{
  "eventTypeKey": "pageViewed",
  "keyValue": "example@email.com",
  "params": [
    {
      "name": "phone",
      "value": "380501234567"
    },
    {
      "name": "email",
      "value": "example@email.com"
    },
    {
      "name": "page",
      "value": "{"location":"https://example.com"}"
    }
  ]
}
```

### productViewed

The event is sent when a contact views a specific product. Such activity can be used in the recommendations algorithms.

The request example is given below. It contains the following parameters:

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "phone",
    "0-1": "String",
    "0-2": "Phone number in the international format. Locator to map an event to a contact.",
    "1-0": "email",
    "1-1": "String",
    "1-2": "Email address. Locator to map an event to a contact.",
    "2-0": "product",
    "2-1": "String",
    "2-2": "Required. Product data.",
    "3-0": "productId",
    "3-1": "String",
    "3-2": "Required. Product ID.",
    "4-0": "price",
    "4-1": "Double",
    "4-2": "Required. Price of a product item.",
    "5-0": "",
    "5-1": "",
    "5-2": "Optional parameter.  \nProduct availability.  \nTwo possible values:  \n• 0 - out of stock  \n• 1 - in stock",
    "6-0": "someProductProperty",
    "6-1": "Array of strings",
    "6-2": "Optional parameter.  \nComma separated product property values.",
    "7-0": "currencyCode",
    "7-1": "String",
    "7-2": "Optional. Currency code in the ISO 4217 format. If not set, the organization's default is used."
  },
  "cols": 3,
  "rows": 8,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


**Example:**

```json
{
  "eventTypeKey": "productViewed",
  "keyValue": "example@email.com",
  "params": [
    {
      "name": "phone",
      "value": "411786452"
    },
    {
      "name": "email",
      "value": "example@email.com"
    },
    {
      "name": "product",
      "value": "{"productId":"WS01-L-Green","price":45.5,"isInStock":1,"someProductProperty":["green"]}]}"
    },
    {
      "name": "currencyCode",
      "value": "USD"
    }
  ]
}
```

### productCategoryViewed

The event is sent when a contact views a list of products in the specified category.

The request example is given below. It contains the following parameters:

| Parameter         | Type   | Description                                                                     |
| :---------------- | :----- | :------------------------------------------------------------------------------ |
| phone             | String | Phone number in the international format. Locator to map an event to a contact. |
| email             | String | Email address. Locator to map an event to a contact.                            |
| category          | String | Category description. Required to create an event.                              |
| productCategoryId | String | Category ID. Required to create an event.                                       |

**Example:** 

```json
{
  "eventTypeKey": "productCategoryViewed",
  "keyValue": "example@email.com",
  "params": [
    {
      "name": "phone",
      "value": "7411324763"
    },
    {
      "name": "email",
      "value": "example@email.com"
    },
    {
      "name": "category",
      "value": "{"productCategoryId":"Mugs"}"
    }
  ]
}
```

### cartUpdated

The event is sent when a contact changes products in the cart. The full list of products in a cart is passed with every request. If a cart is cleaned up, then the list of products is empty.

The request example is given below. It contains the following parameters:

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "phone",
    "0-1": "String",
    "0-2": "Phone number in the international format. Locator to map an event to a contact.",
    "1-0": "email",
    "1-1": "String",
    "1-2": "Email address. Locator to map an event to a contact.",
    "2-0": "products",
    "2-1": "Array of strings",
    "2-2": "Required parameter if the cart is not empty.",
    "3-0": "productId",
    "3-1": "String",
    "3-2": "Required. Product ID.",
    "4-0": "quantity",
    "4-1": "Double",
    "4-2": "Required. Quantity of items in the cart.",
    "5-0": "price",
    "5-1": "Double",
    "5-2": "Required. Price of an item.",
    "6-0": "name",
    "6-1": "String",
    "6-2": "Optional. Product name.",
    "7-0": "category",
    "7-1": "String",
    "7-2": "Optional. Product category.",
    "8-0": "discount",
    "8-1": "String",
    "8-2": "Optional. Discount applied to a single item.",
    "9-0": "someProductProperty",
    "9-1": "Array of strings",
    "9-2": "Optional. Comma separated product property values.",
    "10-0": "currencyCode",
    "10-1": "String",
    "10-2": "Optional. Currency code in the ISO 4217 format. If not set, the organization's default is used.",
    "11-0": "recycleStateId",
    "11-1": "String",
    "11-2": "Required. A unique ID connecting the cart events and purchases.  \nGenerated as a set of random numbers and Latin letters."
  },
  "cols": 3,
  "rows": 12,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


**Example:** 

```json
{
  "eventTypeKey": "cartUpdated",
  "keyValue": "example@email.com",
  "params": [
    {
      "name": "phone",
      "value": "73456712"
    },
    {
      "name": "email",
      "value": "example@email.com"
    },
    {
      "name": "products",
      "value": "[{"productId":"WS01-L-Green","quantity":1,"price":45.5}]"
    },
    {
      "name": "currencyCode",
      "value": "USD"
    },
    {
      "name": "recycleStateId",
      "value": "d59c6e6d-4123-4b0e-8c32-15f0656a8c60"
    }
  ]
}
```

### productImpressions

The event passes the data about the product block displayed at the site. It’s sent by default through JS API. You don’t need to send it additionally.

The request example is given below. It contains the following parameters:

| Parameter      | Type   | Description                                                                     |
| :------------- | :----- | :------------------------------------------------------------------------------ |
| phone          | String | Phone number in the international format. Locator to map an event to a contact. |
| recomVariantId | String | Required. The recommendation variant in the r{recomId}v{variantId} format.      |
| products       | String | Required. Contains the product list in the JSON format.                         |
| productId      | String | Required. Product ID.                                                           |

**Example:** 

```json
{
    "eventTypeKey": "productImpressions",
    "keyValue": "380501234567",
    "params": [
        // Locator or several locators to map an event to a contact
        {
            "name": "phone",
            "value": Phone
        },
        
        {            
            "name" : "recomVariantId"  // Required. Recom variant in r{recomId}v{variantId} format  
            "value" : string           // Mer: container_type
        },
        {
            "name": "products",  // Required. Mer: ProductImpression.Products
            "value": "[          // string contains JSON for a list                
                {
                    // Required product fields
                    "productId": string          // Mer: product_id
                },
                ...
            ]"
        }
    ]
}
```

### productAddedToWishlist

The event passes the data about the products added to the wish list (favorites).

It is used for calculating and displaying recommendations and sending triggers related to the wish list.

The request example is given below. It contains the following parameters:

| Parameter           | Type    | Description                                                                                     |
| :------------------ | :------ | :---------------------------------------------------------------------------------------------- |
| phone               | String  | Phone number in the international format. Locator to map an event to a contact.                 |
| product             | String  | Required. Contains the list of products added to the wish list in the JSON format.              |
| productId           | String  | Required. Product ID.                                                                           |
| price               | Decimal | Required. Product price.                                                                        |
| isInStock           | Int     | Optional. Stock availability. Can be either 0 (not available) or 1 (available).                 |
| someProductProperty | String  | Product property values. Additional product field.                                              |
| currencyCode        | String  | Optional. Currency code in the ISO 4217 format. If not set, the organization's default is used. |

**Example:** 

```json
{
    "eventTypeKey": "productAddedToWishlist",
    "keyValue": "380501234567",
    "params": [
        // Locator or several locators to map an event to a contact
        {
            "name": "phone",
            "value": Phone
        },
        
        {
            "name": "product",   // Required. Mer: AddToWishlist.Product
            "value": "{          // string contains JSON for a product
                            
                // Product fields
                "productId": string,       // Required. Mer: product_key
                "price": decimal,          // Required. Mer: price
                "isInStock": int,          // Optional. 0 or 1; Mer: isInStock                        

                // Extended product fields
                "someProductProperty": [ string, ... ],  // Mer: tag_someProductProperty
                ...
            }"
        }
        {
            "name": "currencyCode",       // Optional
            "value": CurrencyCode               
        }
    ]
}
```

### searchRequest

The event passes the data about search queries sent from the search line.

This event is used for triggers. Send it when the search returns no results. In the trigger, such contacts will receive personal recommendations (at the moment, recommendations are not based on a value entered in the search box).

The request example is given below. It contains the following parameters:

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "phone",
    "0-1": "String",
    "0-2": "Phone number in the international format. Locator to map an event to a contact.",
    "1-0": "search",
    "1-1": "String",
    "1-2": "Required. A value entered in the search box.",
    "2-0": "isFound",
    "2-1": "Int",
    "2-2": "Optional.  \nIf a search returns no results, then the value is 0. If a search returns some results, the value is 1.  \nThe default value is 0."
  },
  "cols": 3,
  "rows": 3,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


**Example:** 

```json
{
    "eventTypeKey": "searchRequest",
    "keyValue": "380501234567",
    "params": [
        // Locator or several locators to map an event to a contact
        {
            "name": "phone",
            "value": Phone
        },
        
        {
            "name": "search",    // Required. Mer: SearchRequest.search
            "value": string
        },
        {
            "name": "isFound",    // 0 or 1. Optional, default 0. Mer: SearchRequest.isFound
            "value": int
        }
    ]
}
```