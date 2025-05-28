---
title: Receiving Recommendations to a Mobile App
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Receiving Recommendations to a Mobile App | Yespo Guide
  description: >-
    Enhance user experience and boost sales by integrating personalized
    recommendations via API, using customer activity data for cross-selling,
    upselling, and tailored suggestions.
  robots: index
next:
  description: ''
---
You can personalize the user experience and increase sales by adding recommendations of your goods and services to an app.

The passed recommendations are based on the customer activity data and include the following options:

* **Out of stock.** A selection based on similar items.
* **Cross-selling.** Offer of related products. The selected items are based on those added to the cart.
* **Upselling.** Offering based on more expensive and complementary goods and services to increase the order value.
* **Potential purchase.** The selected items are based on the orders of users who have purchased this product.
* **Personal recommendations** based on the customer's purchase and browsing history.
* **Other.** An offer is created individually if the required algorithm is not available among our platform's pre-configured algorithms.

> 📘 Note
>
> Each type of recommendation uses different requests, having their own algorithms and rules since they take data from different sources.

## Preconditions

Before starting using recommendations, you have to meet the following conditions:

* Subscribe to one of the Extra features pricing plans.
* [Set up web tracking](https://docs.yespo.io/docs/how-set-web-tracking-your-website) or tracking for mobile apps.
* Create a [data source](https://docs.yespo.io/docs/create-data-source-recommendations) with a required algorithm for each recommendation type to use its ID when calling an API.

Setting up recommendation transmission includes the following steps, as detailed below:

1. Getting an authentication token
2. Getting recommendations via `v1/recoms/{dataSourceId}` request

### Getting authentication token

To get a user authentication token (authToken), send a request via your application from your server to our API.

| Request address                     | Request method |
| :---------------------------------- | :------------- |
| `https://api/v1/auth/contact/token` | POST           |

Authenticate the request using one of the methods described in the [API](https://yespo.io/api/) instructions. For example, using [API keys](https://docs.yespo.io/reference/api-keys).\
The request shall pass the known user fields listed in the table (at least one field is required). 

| Field              | Value  | Description                                                                                  |
| :----------------- | :----- | :------------------------------------------------------------------------------------------- |
| email              | string | Contact’s email                                                                              |
| phone              | string | Contact’s phone number                                                                       |
| externalCustomerId | string | Contact’s external ID                                                                        |
| userPseudoId       | string | Firebase ID for tracking the contact’s behavior                                              |
| cookie             | string | cookie sc – You can generate the cookie file using the tracking script installed on the site |

**Request example:**

```json
{
    "email": string,
    "phone": string,
    "externalCustomerId": string,
    "userPseudoId": string, 
    "cookie": string 
}
```

**Response example:**

```json
{
"token": string
}
```

Further on, authToken authenticates requests to get recommendations. It shall be passed in the `ES-TOKEN` request header. The current token gets invalidated after every request, and the `ES-TOKEN` response header contains a new one used for the next request.

When you receive the 401 status, repeat the token request.

### Getting recommendations

Send the following request to get personalized recommendations based on customer behavior:

| Request address                                | Request method |
| :--------------------------------------------- | :------------- |
| `https://contact-api/v1/recoms/{dataSourceId}` | GET            |

**Request parameters:**

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Field
      </th>

      <th>
        Value
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        dataSourceId
      </td>

      <td>

      </td>

      <td>
        Data source ID.\
        Required parameter\*
      </td>
    </tr>

    <tr>
      <td>
        products
      </td>

      <td>
        string
      </td>

      <td>
        Array of products. The required field for algorithms based on product data
      </td>
    </tr>

    <tr>
      <td>
        category
      </td>

      <td>
        string
      </td>

      <td>
        Array of categories. The required field for algorithms based on category data
      </td>
    </tr>

    <tr>
      <td>
        request header
      </td>

      <td>

      </td>

      <td>
        `ES-TOKEN`: authToken
      </td>
    </tr>

    <tr>
      <td>
        response header
      </td>

      <td>

      </td>

      <td>
        `ES-TOKEN`: authToken
      </td>
    </tr>
  </tbody>
</Table>

\* To find out the data source ID, go to *Account* → *Settings* → *Data sources*.

<Image align="center" width="80% " src="https://files.readme.io/9ececd3b64cb597c9c6931c70888a9482453641600e3def0a1a6e385156ada2d-finding-data-source-id.webp" />

The response contains every field filled with the data.

**Response example:**

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

After you receive recommendations from our platform, you can display them in the customer’s mobile app.

You have to configure the parameters of recommendations in the app itself (design, placement, and others).
