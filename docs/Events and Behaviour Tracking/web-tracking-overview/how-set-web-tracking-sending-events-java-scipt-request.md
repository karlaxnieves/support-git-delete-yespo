---
title: Transferring Website Behavior Data via JavaScript Requests
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Transferring Website Behavior Data via JavaScript Requests | Yespo Guide
  description: >-
    Learn how to transfer website behavior data using JavaScript requests.
    Explore techniques for capturing user actions and sending data for
    analytics, personalization, and optimization of your online strategies.
  robots: index
next:
  description: ''
---
To transfer website data to our platform, you need to install the web tracking script on your site. After, you’ll be able to send the user behavior data and use it to create personalized product recommendations for the site and for your emails.

We encrypt and safely store in our system the contact data received in events, like email addresses, phone numbers, and others.

You can send events through one of the methods:

* Using eS.JS;
* [Using REST API.](https://docs.yespo.io/docs/how-transfer-website-behavior-data-through-rest-api)

> 📘 Note
>
> 1. Pay special attention to the transfer of contact data
> 2. There is no need to configure all the events below — select only those included in your tariff plan

## List of Events

1. Basic (Advanced plan):

* ProductPage
* StatusCart
* PurchasedItems
* CustomerData

2. Advanced (Professional plan):

* ProductPage
* StatusCart
* PurchasedItems
* CustomerData
* CategoryPage
* SearchRequest
* AddToWishlist

3. Recommendations on the site:

* ProductPage
* StatusCart
* PurchasedItems
* CustomerData
* CategoryPage
* MainPage
* NotFound
* ProductImpression

Check the sending of events and their parameters in the browser console on the Network tab. Tracking events are called *webevent*.

<Image align="center" width="80% " src="https://files.readme.io/cc7e750f5eaaa4b6aeffbeb51d12cf77ad13ad8deef401470c11fbb633583ac3-annotate-a-local-image.webp" />

## Script

Script eS

### Purpose

The script tracks what page a visitor is browsing and allows to send events from any page where it is installed.

### Installation

The script should be installed on all pages of your site before the closing tag **body.**

It can be installed by using GTM but it can result in traffic loss as almost all content filters block GTM.

* **GTM** (Google Tag Manager) is a tag management system that allows you to install user scripts on the site pages without interfering with its code.
* **Content filters** (content-control software or web filtering software) is a tool or software that filters sites by content and blocks access to certain sites with content unavailable for viewing.

### Example

```javascript
<script>
!function(t, e, c, n) {
    var s = e.createElement(c);
    s.async = 1, s.src = 'https://cdn.esputnik.com/scripts/' + n + '.js';
    var r = e.scripts[0];
    r.parentNode.insertBefore(s, r);
    var f = function() {
        f.c(arguments);
    };
    f.q = [];
    f.c = function() {
        f.q.push(arguments);
    };
    t['eS'] = t['eS'] || f;
}(window, document, 'script', '000000000000000000');

eS('init', {
    TRACKING: false,
    RECOMS: true
});
</script>
```

### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
      </th>

      <th>
        Example
      </th>

      <th>

      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        script
      </td>

      <td>
        "00000000000000000"\
        Required\
        Type: string
      </td>

      <td>
        Static parameter with a store's ID
      </td>
    </tr>

    <tr>
      <td>
        TRACKING
      </td>

      <td>
        true\
        Optional (true by default)\
        Type: boolean
      </td>

      <td>
        When sending events via es.JS, the value should be set as **false**, while the automatic dispatch of the PageView event on page reload remains
      </td>
    </tr>

    <tr>
      <td>
        RECOMS
      </td>

      <td>
        true\
        Optional (true by default)\
        Type: boolean
      </td>

      <td>
        Recommendation display through configuration (can work without TRACKING, but crawler config should be described)
      </td>
    </tr>
  </tbody>
</Table>

## Page View

**PageView**

### Description

Sending the PageView event - occurs automatically when the page is reloaded, if you have a one-page site and when you go to other sections of the site, the page does not reload, you can configure the event transmission yourself.

### Example

```javascript
eS('sendEvent', 'PageView', {
 'PageView': { }
});
```

## Site Visitor Data

In all events (optional, not mandatory)

### Description

Sending events from all pages with a visitor ID (email, phoneNumber, contactId).

Necessary to match contacts with Cookies.

### Example

```javascript
{
	"GeneralInfo": {
		"externalCustomerId": "1234509876",
		"user_email": "example@email.com",
		"user_phone": "380501234567",
		"user_es_contact_id": 100500
	},
	"ProductPage": {
		"productKey": "24-WG02"
	}
}
```

### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        externalCustomerId
      </td>

      <td>
        "1234509876"\
        Optional\
        Type: string
      </td>

      <td>
        External identifier generated in your system
      </td>
    </tr>

    <tr>
      <td>
        user\_email
      </td>

      <td>
        "`example@email`"\
        Optional\
        Type: string
      </td>

      <td>
        Contact’s email
      </td>
    </tr>

    <tr>
      <td>
        user\_phone
      </td>

      <td>
        "380501234567"\
        Optional\
        Type: string
      </td>

      <td>
        Contact’s phone number
      </td>
    </tr>

    <tr>
      <td>
        user\_es\_contact\_id
      </td>

      <td>
        "100500"\
        Optional\
        Type: string
      </td>

      <td>
        With connected web push token collection, this contact identifier is located in the browser’s internal storage: Local Storage > esWebPushContactId
      </td>
    </tr>
  </tbody>
</Table>

## Basic segmentation events (Advanced Tariff)

### Product Card

ProductPage

#### Description

Sending a ProductPage event, a product card with availability, price and code of the product.

Necessary to calculate and display recommendations and send abandoned views.

#### Example

```javascript
eS('sendEvent', 'ProductPage', {
        'ProductPage': {
            'productKey': '24-MB02',            
            'price': '153',
            'isInStock': 1,
            'tag_some_field': ['123'],
            'tag_another_field': ['321', '213']
        }});
```

> 📘 Note
>
> productKey must match the **`g:id`** parameter in the feed. If the product ID is passed in another parameter in the feed, coordinate this with [support@yespo.io](mailto:support@yespo.io).
>
> Also pay attention to the data type in the price and isInStock parameters. If in the recommendation block a product is immediately added to the cart when the "Buy" button is clicked, you need to send an additional ProductPage event, and pass the "sc\_content" parameter to GeneralInfo in "s\_location", which can be obtained from the target product link received in the recommendations.

#### Example

```javascript
eS('sendEventWithTags', 'ProductPage', {  
  "ProductPage": {  
    "Product": {  
      "productKey": "72354",  
      "price": "754 USD",  
      "isInStock": "1",  
      "tag\_something": \[  
        "abc",  
        "bca"  
      \]  
    },  
    "Tags": {  
      "some\_tags": \[  
        "some\_tag1",  
        "some\_tag2"  
      \]  
    }  
  }  
});
```

#### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        productKey
      </td>

      <td>
        “24-MB02”\
        Required\
        Type: string
      </td>

      <td>
        • Any product ID from the feed\
        • Should match the productKey of the StatusCart event
      </td>
    </tr>

    <tr>
      <td>
        price
      </td>

      <td>
        “153”\
        Optional\
        Type: string
      </td>

      <td>
        • The price per item can be sent with the currency value
      </td>
    </tr>

    <tr>
      <td>
        isinStock
      </td>

      <td>
        “1”\
        Optional\
        Type: int
      </td>

      <td>
        • Indicates if items are in stock\
        • Can have two values:\
                "0" – items are out of stock\
                "1" – items are in stock
      </td>
    </tr>

    <tr>
      <td>
        Tags
      </td>

      <td>
        Optional\
        Type: object
      </td>

      <td>
        Additional fields
      </td>
    </tr>
  </tbody>
</Table>

### Cart

StatusCart

#### Description

The cart is sent as an array of data. The event must be sent every time:

* when adding a product to the cart from the category, product and home pages
* when deleting an item from the cart in a pop-up window or on the cart/checkout page
* when emptying the cart (if possible)

The StatusCart event does not convey the fact of adding a specific product to the cart, but the current state of the cart. If the first product is added to the cart, then an array with one product is sent in the StatusCart event. If a 2nd, 3rd, etc. products are added, then an array of 2, 3, etc. products is transmitted in the StatusCart events. The same logic works when removing items from the cart.

GUID parameter. In each StatusCart event, a GUID parameter must be passed. This is a unique identifier of the current state of the cart. Every time you send a StatusCart event, you need to send a new GUID value that will be different from the previous ones.

#### Example (cart with added items)

```javascript
eS('sendEvent', 'StatusCart', {
   'StatusCart': [
       {
           'productKey': '24-MB02',
           'price': '153',
           'quantity': '1',
           'currency': 'USD',
           "tag_something": [
               "aaa",
               "bbb"
           ]
       }, {
           'productKey': '123-321',
           'price': '450.00',
           'quantity': '3',
           'currency': 'USD'
       }
   ],
   'GUID': '2b914e9c-43ee-bf41-6f80-b97db1e8ab7e'
});
```

If you need to send additional event parameters, use a different construction

#### Example

```javascript
eS('sendEventWithTags', 'StatusCart', {  
  "StatusCart": {  
    "GUID": "6F9619FF-8B86-D011-B42D-00CF4FC964FF",  
    "Products": \[  
      {  
        "productKey": "430738",  
        "price": 201.95,  
        "discount": 180,  
        "quantity": 1,  
        "price\_currency\_code": "UAH",  
        "tag\_something": \[  
          "aaa",  
          "bbb"  
        \]  
      },  
      {  
        "productKey": "902339",  
        "price": 596,  
        "discount": 590,  
        "quantity": 1,  
        "price\_currency\_code": "UAH",  
        "tag\_something": \[  
          "aaa",  
          "bbb"  
        \]  
      }  
    \],  
    "Tags": {  
      "some\_tags": \[  
        "1",  
        "a2"  
      \],  
      "some\_tags1": \[  
        "4",  
        "gg"  
      \]  
    }  
  }  
});
```

#### Example (empty cart)

```
eS('sendEvent', 'StatusCart', {
            'StatusCart': [],
            'GUID': '2c914e9c-43ee-bf41-6f80-b97db1e8ab7e'
        });
```

#### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        GUID
      </td>

      <td>
        “2c914e9c-43ee-bf41-6f80-b97db1e8ab7e”\
        Required\
        Type: string
      </td>

      <td>
        • Unique ID that connects two events – StatusCart and PurchasedItems;\
        • Should be identical to the <a rel="nofollow" href="https://en.wikipedia.org/wiki/Universally_unique_identifier" target="_blank">GUID</a> of the PurchasedItems event\
        • Can be generated of random numbers and Latin characters\
         • GUID is a link between the last cart and purchase\
         • Should be unique for every cart status. It’s a 128-bit ID presented as 32 hexadecimal (base-16) digits, displayed in five groups separated by hyphens
      </td>
    </tr>

    <tr>
      <td>
        productKey
      </td>

      <td>
        “24-MB02”\
        Required\
        Type: string
      </td>

      <td>
        • Any product ID from the feed\
        Should match the productKey of the ProductPage event
      </td>
    </tr>

    <tr>
      <td>
        price
      </td>

      <td>
        “153”\
        Required\
        Type: string
      </td>

      <td>
        The price per item can be sent with the currency value
      </td>
    </tr>

    <tr>
      <td>
        quantity
      </td>

      <td>
        “5”\
        Required\
        Type: string
      </td>

      <td>
        Quantity of items
      </td>
    </tr>

    <tr>
      <td>
        currency
      </td>

      <td>
        “USD"\
        Optional\
        Type: string
      </td>

      <td>
        Currency
      </td>
    </tr>

    <tr>
      <td>
        tags
      </td>

      <td>
        Optional\
        Type: object
      </td>

      <td>
        Additional fields
      </td>
    </tr>
  </tbody>
</Table>

### Purchase

PurchasedItems

#### Description

To show recommendations on the order confirmation page or to send abandoned cart triggers, you need to send a request specifying the purchased item.

If you don’t send abandoned cart triggers, you can send the items in the PurchasedItems event, without StatusCart.

#### Example (purchase in one click)

```javascript
eS('sendEvent', 'PurchasedItems', {
    "OrderNumber": "123/2017",
    "PurchasedItems": [{
        "productKey": "24-MB02",
        "price": "153",
        "quantity": "1",
        "currency": "USD"
    }],
    "Tags": {
        "blockId": ["19787_r119v224"]
    }
});
```

> 📘 Note
>
> The PurchasedItems event also contains a GUID parameter. There is no need to generate a value for this parameter. Use the GUID value from the last StatusCart event.

If you need to send additional event parameters, use a different construction

#### Example

```javascript
eS('sendEventWithTags', 'PurchasedItems', {  
  "PurchasedItems": {  
    "Products": \[  
      {  
        "product\_id": "430738",  
        "unit\_price": "201.95",  
        "quantity": 1  
      },  
      {  
        "product\_id": "211452",  
        "unit\_price": "341.80",  
        "quantity": 2  
      }  
    \],  
    "OrderNumber": "123/2017",  
    "Tags": {  
      "block\_id": \[  
        "21246\_r335v507"  
      \],  
      "some\_tags1": \[  
        "4",  
        "gg"  
      \]  
    }  
  }  
});
```

#### Example (purchase from the site)

```javascript
eS('sendEvent', 'PurchasedItems', {
    "OrderNumber": "123/2017",
    "PurchasedItems": [{
        "productKey": "24-MB02",
        "price": "153",
        "quantity": "1",
        "currency": "USD"
    }],
"GUID": "6F9619FF-8B86-D011-B42D-00CF4FC964FF"
});
```

If you need to send additional event parameters, use a different construction

#### Example

```
eS('sendEventWithTags', 'PurchasedItems', {  
  "PurchasedItems": {  
    "GUID": "6F9619FF-8B86-D011-B42D-00CF4FC964FF",  
    "OrderNumber": "123/2017",  
    "Tags": {  
      "some\_tags": \[  
        "1",  
        "a2"  
      \],  
      "some\_tags1": \[  
        "4",  
        "gg"  
      \]  
    }  
  }  
});
```

#### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        OrderNumber
      </td>

      <td>
        "1234/2017"\
        Required\
        Type: string
      </td>

      <td>
        Order number
      </td>
    </tr>

    <tr>
      <td>
        GUID
      </td>

      <td>
        "6F9619FF-8B86-D011-B42D-00CF4FC964FF”\
        Required\
        Type: string
      </td>

      <td>
        • Unique ID that connects two events – StatusCart and PurchasedItems\
        • Should be identical to the GUID of the PurchasedItems event\
        • Can be generated of random numbers and Latin characters\
        • GUID is a link between the last cart and purchase\
        • Should be unique for every cart status. It’s a 128-bit ID presented as 32 hexadecimal (base-16) digits, displayed in five groups separated by hyphens
      </td>
    </tr>

    <tr>
      <td>
        productKey
      </td>

      <td>
        Required\
        Type: string
      </td>

      <td>
        • Any product ID from the feed\
        • Should match the productkey of the ProductPage event
      </td>
    </tr>

    <tr>
      <td>
        price
      </td>

      <td>
        "21.70"\
        Required\
        Type: string
      </td>

      <td>
        The price per item can be sent with the currency value
      </td>
    </tr>

    <tr>
      <td>
        quantity
      </td>

      <td>
        “1”\
        Required\
        Type: string
      </td>

      <td>
        Quantity of items
      </td>
    </tr>

    <tr>
      <td>
        currency
      </td>

      <td>
        “USD"\
        Optional\
        Type: string
      </td>

      <td>
        Currency
      </td>
    </tr>

    <tr>
      <td>
        tags
      </td>

      <td>
        Optional\
        Type: object
      </td>

      <td>
        Additional fields
      </td>
    </tr>

    <tr>
      <td>
        blockID
      </td>

      <td>
        Optional\
        Type: string
      </td>

      <td>
        • Taken from the URL line sc\_content=\
        • If there is no parameter query in the URL, blockID and its value aren’t sent.
      </td>
    </tr>
  </tbody>
</Table>

### Customer

CustomerData

#### Description

To send abandoned cart and abandoned browse triggers, you need to send a request with the customer data. Apart from abandoned cart and abandoned browse emails, it can be used in order confirmations and registration confirmations.

CustomerData should be sent:

* when registering on the site
* when logging in to the site
* when entering personal data on the checkout page. If the user is already authorized by the time the order is placed, you do not have to send this event.
* from your personal account if the user updates information (adds/changes phone number or email)

> 📘 Note
>
> When registering a user, in addition to the CustomerData event, you must transfer a contact to the system using the [https://docs.yespo.io/reference/addcontact-1](https://docs.yespo.io/reference/addcontact-1) method, since the CustomerData event itself does not create a contact in Yespo.
>
> If, in addition to tracking on the website, tracking will be configured in the mobile application, you must additionally pass the externalCustomerId parameter (your internal contact ID) in the contact creation request.

#### Example

```javascript
eS('sendEvent', 'CustomerData', {
    'CustomerData': {
        'externalCustomerId': '1234509876',
        'user_email': 'example@email.com',
        'user_name': 'Johny',
        'user_card_id': '321',
        'user_phone': '3801111111111',
        'user_city': 'Gdańsk',
        'user_tags_gender': 'male',
    }
});
```

#### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        externalCustomerId
      </td>

      <td>
        "1234509876"  

        Optional  

        Type: string
      </td>

      <td>
        External identifier generated in your system
      </td>
    </tr>

    <tr>
      <td>
        user\_email
      </td>

      <td>
        "`example@email.com`"\
        Required\
        Type: string
      </td>

      <td>
        User’s email is necessary to send abandoned carts and browses
      </td>
    </tr>

    <tr>
      <td>
        user\_name
      </td>

      <td>
        "John”\
        Optional\
        Type: string
      </td>

      <td>
        User name
      </td>
    </tr>

    <tr>
      <td>
        user\_client\_id
      </td>

      <td>
        “123”\
        Optional\
        Type: string
      </td>

      <td>
        User card ID
      </td>
    </tr>

    <tr>
      <td>
        user\_phone
      </td>

      <td>
        "3801111111111"\
        Required\
        Type: string
      </td>

      <td>
        Phone number in the international format
      </td>
    </tr>
  </tbody>
</Table>

## Additional events for advanced segmentation (Pro plan)

### Category

CategoryPage

#### Description

To show recommendations on the category page, you need to send a request specifying what category the user is viewing.

> 📘 Note
>
> categoryKey must match the category names in the feed. If the categories in the feed are transferred like this: \<g:google\_product\_category>Shoes > Sneakers > Running Sneakers\</g:google\_product\_category>, then in the categoryKey you need to transfer Shoes, Sneakers or Running Sneakers, respectively. If the category is in the form of an identifier, then in the feed you should change it to an identifier. From a technical point of view, it does not matter which option is chosen, but from a practical point of view, it is better to use the category names.

#### Example

```javascript
eS('sendEvent', 'CategoryPage', {
    "CategoryPage": {
        "categoryKey": "509876"
    },
    "Tags": {
        "some_tags": [
            "gh",
            "a2"
        ],
        "some_tags1": [
            "4",
            "gg"
        ]
    }
});
```

If you need to send additional event parameters, use a different construction

#### Example

```
eS('sendEventWithTags', 'CategoryPage', {  
  "CategoryPage": {  
    "Category": {  
      "categoryKey": "509876"  
    },  
    "Tags": {  
      "some\_tags": \[  
        "1",  
        "a2"  
      \],  
      "some\_tags1": \[  
        "4",  
        "gg"  
      \]  
    }  
  }  
});
```

#### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        categoryKey
      </td>

      <td>
        “Babies"\
        Required\
        Type: string
      </td>

      <td>
        • Category ID\
        • Can be a category name or any other ID available in the feed
      </td>
    </tr>

    <tr>
      <td>
        Tags
      </td>

      <td>
        Optional\
        Type: object
      </td>

      <td>
        Additional fields
      </td>
    </tr>
  </tbody>
</Table>

### Wishlist

AddToWishlist

#### Description

Sending the AddToWishlist event - at the time of adding a product to the wish list (favorites).

Necessary for calculating and displaying recommendations and sending triggers related to the wish list.

#### Example

```javascript
eS('sendEvent', 'AddToWishlist', {
        'AddToWishlist': {
            'productKey': '24-MB02',            
            'price': '153',
            'isInStock': 1
        }});
```

#### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        productKey
      </td>

      <td>
        “24-MB02”\
        Required\
        Type: string
      </td>

      <td>
        • Any product ID from the feed
      </td>
    </tr>

    <tr>
      <td>
        Price
      </td>

      <td>
        “153”\
        Optional\
        Type: string
      </td>

      <td>
        • The price per item can be sent with the currency value
      </td>
    </tr>

    <tr>
      <td>
        isinStock
      </td>

      <td>
        “1”\
        Optional\
        Type: int
      </td>

      <td>
        • Indicates if items are in stock\
        • Can have two values:\
                "0" – items are out of stock\
                "1" – items are in stock
      </td>
    </tr>
  </tbody>
</Table>

### Search requests

**SearchRequest (optional)**

#### Description

To collect statistics on search queries, you need to send the value from the search line.

Use this event for triggers. Send it only if the search returned no results. In the trigger, such contacts will receive personal recommendations (at the moment, recommendations don’t depend on the value entered in the search, we will support this feature in the nearest future).

#### Example

```javascript
eS('sendEvent', 'SearchRequest', {
    "SearchRequest": {
"search":"input_value",
"isFound": 1
}
});
```

#### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        search
      </td>

      <td>
        "Coffe"\
        Required\
        Type: String
      </td>

      <td>
        Value from the search string. What we are looking for on the site.
      </td>
    </tr>

    <tr>
      <td>
        isFound
      </td>

      <td>
        1/0\
        Optional\
        Type: int
      </td>

      <td>
        If the list is empty, it returns 0 otherwise 1
      </td>
    </tr>
  </tbody>
</Table>

## Additional Events Required for Recommendations on the Site

### Product Card (Additional Settings)

ProductPage

<Image align="center" width="80% " src="https://files.readme.io/37b9aaf98d1365519b8fff68b313adc01bcbdcccff8c38f0b6d807b7e281e4f7-site-en.webp" />

If in the recommendation block the product is immediately added to the cart when the "Buy" button is clicked, it is necessary to send an additional ProductPage event, and in GeneralInfo in "s\_location" pass the "sc\_content" parameter, which can be obtained from the link of the target product received in the recommendations.

If the cart/checkout page does not send StatusCart (there were no changes to the cart), but needs to display the cart recommendation block, send an event `eS('sendEvent`, `StatusCartPage')`.

### Main Page

MainPage

#### Description

Sending the MainPage event.

Necessary to display recommendations on the site.

#### Example

```javascript
eS('sendEvent', 'MainPage');
```

### 404 Page

NotFound

#### Description

Sending the NotFound event.

Necessary to display recommendations on the site.

#### Example

```javascript
eS('sendEvent', 'NotFound');
```

### Impressions

**ProductImpression**

If you set up calling recommendations through the JS API, you must call  ProductImpressions method when recommendation appears in user’s browser viewport (when user see recommendation) so tracking could work correct. You could use <a rel="nofollow" href="https://caniuse.com/intersectionobserver" target="_blank">Intersection Observer API</a> to detect element visibility to a user or any other method of your choice. The request must contain the parameters that were returned in the getRecommendations response: product identifiers and a container\_type containing the block ID and variant\_id.

#### Description

To show impressions for recommendation blocks in Reports, you need to send a request with data on the displayed items.

#### Example

```javascript
eS('sendEvent', 'ProductImpressions', {
    "ProductImpression": [{
        "product_id": "430968",
        "container_type": "1253_r963v1317"
    }]
});
```

If you need to send additional event parameters, use a different construction

#### Example

```javascript
eS('sendEventWithTags', 'ProductImpression', {  
  "ProductImpression": {  
    "Products": \[  
      {  
        "product\_id": "430968",  
        "container\_type": "1253\_r963v1317"  
      },  
      {  
        "product\_id": "430738",  
        "container\_type": "1253\_r963v1317"  
      },  
      {  
        "product\_id": "429983",  
        "container\_type": "1253\_r963v1317"  
      }  
    \],  
    "Tags": {  
      "some\_tags": \[  
        "1",  
        "a2"  
      \],  
      "some\_tags1": \[  
        "4",  
        "gg"  
      \]  
    }  
  }  
});
```

#### Parameters

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Name
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
        product\_id
      </td>

      <td>
        “PK1"\
        Required\
        Type: string
      </td>

      <td>
        ID of the displayed item
      </td>
    </tr>

    <tr>
      <td>
        container\_type
      </td>

      <td>
        “1253”\
        Required\
        Type: string
      </td>

      <td>
        Recommendation block number
      </td>
    </tr>

    <tr>
      <td>
        Tags
      </td>

      <td>
        Optional\
        Type: object
      </td>

      <td>
        Additional fields
      </td>
    </tr>
  </tbody>
</Table>

If there are several blocks on one page, all sessions are sent in one request.
