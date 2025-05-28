---
title: Flutter Ecommerce Activity Tracking
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Flutter Ecommerce Activity Tracking | Yespo Guide
  description: >-
    The document provides a guide on tracking e-commerce activities in a Flutter
    application using Reteno's SDK.
  robots: index
next:
  description: ''
---
Reteno's e-commerce activity tracking helps to learn about the customer journey and use this data in your analytics.

This guide shows how to track e-commerce activity in your Flutter application using a single entry-point method:

```dart Dart
Future<void> logEcommerceEvent(RetenoEcommerceEvent event)
```

***

## Supported Events

| **Event class**                         | **When to fire it**                                                |
| --------------------------------------- | ------------------------------------------------------------------ |
| `RetenoEcommerceProductViewed`          | A user opens a product card                                        |
| `RetenoEcommerceProductCategoryViewed`  | A user opens a product-category (listing) page                     |
| `RetenoEcommerceProductAddedToWishlist` | A user adds a product to a wishlist                                |
| `RetenoEcommerceCartUpdated`            | Items in the shopping cart change (add / remove / quantity update) |
| `RetenoEcommerceOrderCreated`           | A new order is created                                             |
| `RetenoEcommerceOrderUpdated`           | An order is updated after creation                                 |
| `RetenoEcommerceOrderDelivered`         | Order status becomes **DELIVERED**                                 |
| `RetenoEcommerceOrderCancelled`         | Order status becomes **CANCELLED**                                 |
| `RetenoEcommerceSearchRequest`          | A catalogue search request is performed                            |

All event classes are defined in `reteno_ecommerce_event.dart` and extend the sealed base class `RetenoEcommerceEvent`.

***

## Usage Pattern

1. Construct the appropriate event object.
2. Pass it to `logEcommerceEvent()` and **await** the result.
3. Repeat this process for every interaction you want to track.

> The SDK automatically timestamps events, so you do **not** need to provide a `date` parameter.

```dart Dart
final product = RetenoEcommerceProduct(
  productId: 'PRODUCT_ID',
  price: 20.0,
  inStock: true,
  attributes: {
    'size': ['23', '42'],
    'color': ['white', 'orange'],
  },
);

await logEcommerceEvent(
  RetenoEcommerceProductViewed(
    product: product,
    currency: 'UAH',
  ),
);
```

***

## Event Reference

### Product Viewed

Fire when a user sees a product card.

| Parameter | Type                     | Description                                          |
| --------- | ------------------------ | ---------------------------------------------------- |
| product   | `RetenoEcommerceProduct` | **Required.** Product being viewed                   |
| currency  | `String?` (ISO-4217)     | Optional (USD, EUR, UAH). Uses org default if `null` |

#### RetenoEcommerceProduct

| Property     | Type                         | Description                                                                             |
| ------------ | ---------------------------- | --------------------------------------------------------------------------------------- |
| `productId`  | `String`                     | Unique identifier of the product in **your** catalog.                                   |
| `price`      | `double`                     | Current product price including taxes and discounts.                                    |
| `inStock`    | `bool`                       | `true` if the product is available for purchase.                                        |
| `attributes` | `Map<String, List<String>>?` | Arbitrary attribute map for segmentation (e.g. `{ 'size': ['M'], 'color': ['blue'] }`). |

***

### Product Category Viewed

Fire when a user opens a category or listing page.

```dart Dart
final category = RetenoEcommerceCategory(
  productCategoryId: 'CATEGORY_ID',
  attributes: {
    'gender': ['kids'],
  },
);

await logEcommerceEvent(
  RetenoEcommerceProductCategoryViewed(category: category),
);
```

| Property            | Type                         | Description                                                  |
| ------------------- | ---------------------------- | ------------------------------------------------------------ |
| `productCategoryId` | `String`                     | Category identifier (slug, code or UUID).                    |
| `attributes`        | `Map<String, List<String>>?` | Additional category metadata (e.g. `{ 'gender': ['men'] }`). |

***

### Product Added to Wishlist

```dart Dart
await logEcommerceEvent(
  RetenoEcommerceProductAddedToWishlist(
    product: product,
    currency: 'EUR',
  ),
);
```

#### RetenoEcommerceProduct

| Property     | Type                         | Description                               |
| ------------ | ---------------------------- | ----------------------------------------- |
| `productId`  | `String`                     | Product identifier                        |
| `price`      | `double`                     | Unit price **before** discount.           |
| `quantity`   | `int`                        | Number of units in the cart.              |
| `discount`   | `double?`                    | Discount per unit (absolute, optional).   |
| `name`       | `String?`                    | Human‑readable product name (optional).   |
| `category`   | `String?`                    | Product category name or ID (optional).   |
| `attributes` | `Map<String, List<String>>?` | Extra attributes (e.g. selected options). |

***

### Cart Updated

Track any changes to the shopping cart contents.

```dart Dart
final cartProducts = [
  const RetenoEcommerceProductInCart(
    productId: 'uut',
    price: 20.0,
    quantity: 1,
  ),
  const RetenoEcommerceProductInCart(
    productId: 'lk',
    price: 100.0,
    quantity: 3,
  ),
];

await logEcommerceEvent(
  RetenoEcommerceCartUpdated(
    cartId: 'CART_ID',
    products: cartProducts,
    currency: 'UAH',
  ),
);
```

#### RetenoEcommerceProductInCart

| Property     | Type                         | Description                               |
| ------------ | ---------------------------- | ----------------------------------------- |
| `productId`  | `String`                     | Product identifier                        |
| `price`      | `double`                     | Unit price **before** discount.           |
| `quantity`   | `int`                        | Number of units in the cart.              |
| `discount`   | `double?`                    | Discount per unit (absolute, optional).   |
| `name`       | `String?`                    | Human‑readable product name (optional).   |
| `category`   | `String?`                    | Product category name or ID (optional).   |
| `attributes` | `Map<String, List<String>>?` | Extra attributes (e.g. selected options). |

***

### Order Created or Updated

Both `RetenoEcommerceOrderCreated` and `RetenoEcommerceOrderUpdated` use the same payload.

```dart Dart
final order = RetenoEcommerceOrder(
  externalOrderId: 'ORDER_ID',
  totalCost: 300.0,
  status: RetenoEcommerceOrderStatus.initialized,
  date: DateTime.now().toIso8601String(),
  cartId: 'CART_ID',
);

await logEcommerceEvent(
  RetenoEcommerceOrderCreated(
    order: order,
    currency: 'UAH',
  ),
);
```

#### RetenoEcommerceOrder

| Property             | Type                         | Description                                                                  |
| -------------------- | ---------------------------- | ---------------------------------------------------------------------------- |
| `externalOrderId`    | `String`                     | Order ID from your commerce back‑end.                                        |
| `totalCost`          | `double`                     | Grand total amount charged to the customer.                                  |
| `status`             | `RetenoEcommerceOrderStatus` | Current order state (`initialized`, `inProgress`, `delivered`, `cancelled`). |
| `date`               | `String` (ISO‑8601)          | Date/time when the order was placed.                                         |
| `externalCustomerId` | `String?`                    | Customer ID in your system (optional).                                       |
| `cartId`             | `String?`                    | Shopping cart identifier that generated the order (optional).                |

***

## RetenoEcommerceOrderStatus (enum)

| Value         | Meaning                                       |
| ------------- | --------------------------------------------- |
| `initialized` | Order was created but not paid yet.           |
| `inProgress`  | Payment confirmed / order is being processed. |
| `delivered`   | Order delivered to the customer.              |
| `cancelled`   | Order was cancelled or refunded.              |

***

### Order Delivered or Cancelled

```dart Dart
await logEcommerceEvent(
  const RetenoEcommerceOrderDelivered(externalOrderId: 'ORDER_ID'),
);

await logEcommerceEvent(
  const RetenoEcommerceOrderCancelled(externalOrderId: 'ORDER_ID'),
);
```

***

### Search Request

```dart Dart
await logEcommerceEvent(
  const RetenoEcommerceSearchRequest(
    query: 'iphone',
    isFound: true,
  ),
);
```

***

## Custom Events

If your use case doesn’t match a predefined `RetenoEcommerceEvent`, use the generic logging API:

```dart Dart
await Reteno.logEvent(
  eventTypeKey: 'custom_event_type',
  parameters: {
    'parameter_name': 'value',
  },
);
```

***

## Currency Codes

Use valid <a rel="nofollow" href="https://en.wikipedia.org/wiki/ISO_4217" target="_blank"> ISO‑4217</a> codes: **USD**, **EUR**, or **UAH**. If no `currency` is provided, your organization’s default is used.
