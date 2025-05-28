---
title: iOS Ecommerce Activity Tracking
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Reteno's e-commerce documentation helps define the journey for a customer as they visit a product page or a product category page, add a product to wishlist, update a shopping cart, create or update an order.

Here is a list of supported events:

| **Event type**         | **Description**                                                                                                                                |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| productViewed          | Track a product card a user is viewing to rank items / categories and send triggers for abandoned browses.                                     |
| productCategoryViewed  | Track a product category a user is viewing for triggers like *Website visit with a category view* and *Website visit without a category view*. |
| productAddedToWishlist | Track adding product to a wishlist to calculate and display recoms and send triggers related to a wishlist.                                    |
| cartUpdated            | Track updating a shopping cart for triggers.                                                                                                   |
| orderCreated           | Create an order.                                                                                                                               |
| orderUpdated           | Update an order.                                                                                                                               |
| orderDelivered         | Change an existing order status to DELIVERED.                                                                                                  |
| orderCancelled         | Change an existing order status to CANCELLED.                                                                                                  |
| searchRequest          | Track search requests for triggers like *Abandoned search*.                                                                                    |

Track activity via `Reteno.ecommerce().logEvent(type: Ecommerce.EventType, date: Date, forcePush: Bool)` method. Provide appropriate event type, event date and forcePush flag (if you want to send event immediatelly).

### Product Viewed

Fire this event when a user views a product card.

This event supports the following properties:

| **Parameter** | **Type**          | **Comment**                                                                                                                                          |
| ------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| product       | Ecommerce.Product | Required parameter                                                                                                                                   |
| currencyCode  | String?           | Currency in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) format. Supported currencies: USD, EUR, UAH. If is not set then org's default is used |

Example:

```swift
let product = Ecommerce.Product(
    productId: "Product_ID",
    price: 20.0,
    isInStock: 1,
    attributes: ["size": ["23", "42"], "color": ["white", "orange"]]
)
Reteno.ecommerce().logEvent(type: .productViewed(product: product, currencyCode: "UAH"))
```

### Product Category Viewed

Fire this event when a user views a category.

This event supports the following properties:

| **Parameter** | **Type**                  | **Comment**        |
| ------------- | ------------------------- | ------------------ |
| category      | Ecommerce.ProductCategory | Required parameter |

Example:

```swift
let productCategory = Ecommerce.ProductCategory(
    productCategoryId: "CATEGORY_ID",
    attributes: ["size": ["M", "L"]]
)
Reteno.ecommerce().logEvent(type: .productCategoryViewed(category: productCategory))
```

### Product Added to Wishlist

Fire this event when a user adds a product to a wishlist.

This event supports the following properties:

| **Parameter** | **Type**          | **Comment**                                                                                                                                          |
| ------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| product       | Ecommerce.Product | Required parameter                                                                                                                                   |
| currencyCode  | String?           | Currency in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) format. Supported currencies: USD, EUR, UAH. If is not set then org's default is used |

Example:

```swift
let product = Ecommerce.Product(
    productId: "PRODUCT_ID",
    price: 20.0,
    isInStock: 1,
    attributes: ["size": ["23", "42"], "color": ["white", "orange"]]
)
Reteno.ecommerce().logEvent(type: .productAddedToWishlist(product: product, currencyCode: "EUR"))
```

### Cart Updated

Fire this event when a user updates a shopping cart.

The `cartUpdated` event transmits not the fact of adding a specific product to the cart, but the current state of the cart. If the first product is added to the cart, then an array with one product is passed in the `cartUpdated` event. If a second, third, etc. product is added, then an array of two, three, etc. products is transmitted in the `cartUpdated` events. The same logic works when removing products from the cart.

In each `cartUpdated` event, the `cartId` parameter must be passed. This is a unique identifier of the current state of the cart. Each time you send the `cartUpdated` event, you must pass a new `cartId` value that will be different from the previous ones.

This event supports the following properties:

| **Parameter** | **Type**                  | **Comment**                                                                                                                                          |
| ------------- | ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| cartId        | String                    | Required parameter                                                                                                                                   |
| products      | [Ecommerce.ProductInCart] | Required parameter                                                                                                                                   |
| currencyCode  | String?                   | Currency in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) format. Supported currencies: USD, EUR, UAH. If is not set then org's default is used |

`Ecommerce.ProductInCart` model parameters:

| **Parameter** | **Type**             | **Comment**                                                                                 |
| ------------- | -------------------- | ------------------------------------------------------------------------------------------- |
| productId     | String               | Product ID (required).                                                                      |
| price         | Float                | Product price (required).                                                                   |
| quantity      | Int                  | Product quantity (required).                                                                |
| discount      | Float?               | Disount                                                                                     |
| name          | String?              | Product name                                                                                |
| category      | String?              | Product category                                                                            |
| attributes    | \[String: [String]]? | Additional attributes, for example, \["size": \["23", "42"], "color": \["white", "orange"]] |

Example:

```swift
let productsInCart = [
    Ecommerce.ProductInCart(productId: "uut", price: 20.0, quantity: 1),
    Ecommerce.ProductInCart(productId: "lk", price: 100.0, quantity: 3)
]
Reteno.ecommerce().logEvent(type: .cartUpdated(cartId: "CART_ID", products: productsInCart, currencyCode: "UAH"))
```

### Order Сreated

Fire this event when a user creates an order.

This event supports the following properties:

| **Parameter** | **Type**                 | **Comment**                                                                                                                                                              |
| ------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| order         | Ecommerce.Order          | Required parameter                                                                                                                                                       |
| currencyCode  | String?                  | Currency in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217 "\{rel='nofollow'}") format. Supported currencies: USD, EUR, UAH. If is not set then org's default is used |
| parameters    | Array of Event.Parameter | Extend event parameters with non-standard order attributes if necessary.                                                                                                 |

`Ecommerce.Order` model parameters:

| **Parameter**     | **Type**                  | **Comment**                                                                                                                                |
| ----------------- | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| externalOrderId   | String                    | ID of order in the external system (required).                                                                                             |
| totalCost         | Float                     | Total cost of order (required).                                                                                                            |
| status            | Status                    | Order status (required). Possible values: DELIVERED, IN\_PROGRESS, CANCELLED, INITIALIZED. Only DELIVERED orders are used in RFM analysis. |
| date              | Date                      | Order date and time (required).                                                                                                            |
| cartId            | String?                   | Shopping cart ID. Allows to match an order with shopping cart actions.                                                                     |
| email             | String?                   | Customer email address.                                                                                                                    |
| phone             | String?                   | Customer phone number.                                                                                                                     |
| firstName         | String?                   | Customer first name.                                                                                                                       |
| lastName          | String?                   | Customer last name.                                                                                                                        |
| shipping          | Float?                    | Shipping cost.                                                                                                                             |
| discount          | Float?                    | Discount.                                                                                                                                  |
| taxes             | Float?                    | Amount of tax.                                                                                                                             |
| restoreUrl        | String?                   | Link to order.                                                                                                                             |
| statusDescription | String?                   | Order status description.                                                                                                                  |
| storeId           | String?                   | Store ID (if you work with several stores in one Reteno account).                                                                          |
| source            | String?                   | "Online" \\ "offline" values for segmentation. If the field is empty or some other value, by default the order will be accepted as online. |
| deliveryMethod    | String?                   | Delivery method.                                                                                                                           |
| paymentMethod     | String?                   | Payment method.                                                                                                                            |
| deliveryAddress   | String?                   | Delivery address.                                                                                                                          |
| items             | [Item]?                   | Array of ordered products (required)                                                                                                       |
| attributes        | \[String: [String: Any]]? | Additional attributes. Provide additional parameter name as key and parameter JSON as value.                                               |

`Ecommerce.Order.Item` model parameters:

| **Parameter**  | **Type** | **Comment**                                      |
| -------------- | -------- | ------------------------------------------------ |
| externalItemId | String   | ID of product in the external system (required). |
| name           | String   | Product name (required).                         |
| category       | String   | Product category (required).                     |
| quantity       | Double   | Number of items (required).                      |
| cost           | Float    | Product price (required).                        |
| url            | String   | Link to product page (required).                 |
| imageUrl       | String?  | Link to a product image.                         |
| description    | String?  | Short description of product.                    |

Example:

```swift
let order = Ecommerce.Order(
    externalOrderId: "ORDER_ID",
    totalCost: 300.0,
    status: .INITIALIZED,
    date: Date(),
    cartId: "idid"
)
Reteno.ecommerce().logEvent(type: .orderCreated(order: order, currencyCode: "UAH"))
```

### Order Updated

Fire this event when a user updates an order.

This event supports the following properties:

| **Parameter** | **Type**        | **Comment**                                                                                                                                          |
| ------------- | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| order         | Ecommerce.Order | Required parameter                                                                                                                                   |
| currencyCode  | String?         | Currency in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) format. Supported currencies: USD, EUR, UAH. If is not set then org's default is used |

`Ecommerce.Order` and `Ecommerce.Order.Item` models parameters are described in Order created event.

Example:

```swift
let order = Ecommerce.Order(
    externalOrderId: "ORDER_ID",
    totalCost: 300.0,
    status: .IN_PROGRESS,
    date: Date(),
    cartId: "idid"
)
Reteno.ecommerce().logEvent(type: .orderUpdated(order: order, currencyCode: "UAH"))
```

### Order Delivered

Fire this event when an order status is changed to delivered. If an order does not exist then an event is ignored.

This event supports the following properties:

| **Parameter**   | **Type** | **Comment**        |
| --------------- | -------- | ------------------ |
| externalOrderId | String   | Required parameter |

Example:

```swift
Reteno.ecommerce().logEvent(type: .orderDelivered(externalOrderId: "ORDER_ID"))
```

### Order Cancelled

Fire this event when an order status is changed to cancelled. If an order does not exist then an event is ignored.

This event supports the following properties:

| **Parameter**   | **Type** | **Comment**        |
| --------------- | -------- | ------------------ |
| externalOrderId | String   | Required parameter |

Example:

```swift
Reteno.ecommerce().logEvent(type: .orderCancelled(externalOrderId: "ORDER_ID"))
```

### Search Request

This event supports the following properties:

| **Parameter** | **Type** | **Comment**                           |
| ------------- | -------- | ------------------------------------- |
| query         | String   | Required. Order ID in external system |
| isFound       | Bool?    | Flag if search returned results       |

Example:

```swift
Reteno.ecommerce().logEvent(type: .searchRequest(query: "iphone", isFound: true))
```

### Unsupported Events

If you want to track user activity and could not find appropriate `Ecommerce.EventType`, you always can use `Reteno.logEvent` method:

```swift
Reteno.logEvent(
    eventTypeKey: "test_event_type",
    date: Date(),
    parameters: [Event.Parameter(name: "Parameter name", value: "some parameter value")],
    forcePush: false
)
```
