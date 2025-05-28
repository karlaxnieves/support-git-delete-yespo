---
title: Sending Product Recommendations via API
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Sending Product Recommendations via API | Yespo Guide
  description: >-
    Learn how to send product data through the v2/contacts/recoms resource. Use
    it to offer personalized product recommendations based on customer order
    history.
  robots: index
next:
  description: ''
---
Product recommendations are an effective marketing tool. You can display personalized product [recommendations in emails](https://docs.yespo.io/docs/how-set-product-recommendations-email) and on the [site](https://docs.yespo.io/docs/product-recommendations-website) to generate repeat sales and grow customer retention.

Using the _[Contact recommendations based on web tracking](https://docs.yespo.io/reference/contactrecoms-1)_ resource, you can transfer data on customer preferences to other channels and offer recommendations based on it.

- Messengers;
- Call centers;
- Pickup points;
- Mobile apps.

## How to Use _Contact Recommendations Based on Web Tracking_

The transfer of recommendations through _Contact recommendations based on web tracking_ will allow operators/cashiers to generate repeat sales offering products based on customer shopping history.

**Example 1**

When calling the customer to confirm the order, the manager sees a list of recommendations for the bought products and personal recommendations for this customer, if any.

**Example 2**

When making an offline purchase, the customer provides their discount card or tells the phone number to earn account bonuses. The system identifies the customer and shows the additional recommendations for them.

## What Product Categories Can Be Recommended

- **Alternatives to out-of-stock products**.
- **Also bought**. Cross-sell based on items added to the cart.
- **You may also like**. Upsell of more expensive items and complementary goods to increase the order price.
- **Bestsellers**. Recommendations based on orders by other customers.
- **Personal recommendations** based on the customer’s purchase history.
- **Other**. Recommendations created not using our algorithms.

Important

You need to send requests for each recommendation type because they have different data sources.

## How to Use Recommendations

- [Set web tracking](https://docs.yespo.io/docs/how-set-web-tracking-your-website) and upload a product feed.
- [Subscribe to a pricing plan](https://yespo.io/tarif-universum) covering Advanced Segmentation.
- Create a data source and select the necessary algorithm.

You need to create a data source for each recommendation type. Its ID will be used for an API call.

## How to Send Recommendations

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "dataSourceId",
    "0-1": "",
    "0-2": "Required.  \nYou can find data source IDs in Settings > Data sources.",
    "1-0": "contactId",
    "1-1": "Long",
    "1-2": "You need to specify at least one of the parameters – contactId, email, phone, externalCustomerId, webI.",
    "2-0": "email",
    "2-1": "Email",
    "2-2": "You need to specify at least one of the parameters – contactId, email, phone, externalCustomerId, webI.",
    "3-0": "phone",
    "3-1": "Phone",
    "3-2": "You need to specify at least one of the parameters – contactId, email, phone, externalCustomerId, webI.",
    "4-0": "externalCustomerId",
    "4-1": "String",
    "4-2": "You need to specify at least one of the parameters – contactId, email, phone, externalCustomerId, webI.",
    "5-0": "webI",
    "5-1": "String",
    "5-2": "You need to specify at least one of the parameters – contactId, email, phone, externalCustomerId, webI.",
    "6-0": "products",
    "6-1": "String",
    "6-2": "Product array. Required for algorithms based on product data.",
    "7-0": "category",
    "7-1": "String",
    "7-2": "Category array. Required for algorithms based on category data."
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


> 📘 Important
> 
> - This method doesn’t include the _offset_ and _maxrows_ parameters. The number of elements isn’t expected to be large and they are configured at the data source level.
> - To receive recommendations on the site's backend, use the _webId_ identification parameter.

### Request and Response Examples

Go to your profile → _Settings → Data Sources_. Choose the data source and send a request `/api/v2/contacts/recoms/1244?contactId=162688150`,

where 1244 is a data source ID.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cc6fcc5f97f9ba1bde435175e53fe4e6c3b2ebb732b59605293addb6c2a9f2cb-sending-product-recommendations-via-api-001.webp",
        "Data source ID",
        "Data source ID"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the response, each field will be filled:

```json
{
    // Mandatory fields
    id: string
    name: string
    url: URL
    price: double
    descr: text
    brand: string
    category: string[]
    isInStock: int

    // Optional fields which depend on a customer's feed format
    // All such fields start from "tags_".
    // Examples: tags_gender, tags_clear_size, tags_universal_size

}
```