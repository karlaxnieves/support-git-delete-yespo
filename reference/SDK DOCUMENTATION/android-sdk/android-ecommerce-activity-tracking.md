---
title: Android Ecommerce Activity Tracking
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
Reteno's e-commerce activity tracking helps to learn about the customer journey and use this data in your analytics. 

The list of supported events:

| **Event type**         | **Description**                                                                                                                                                             |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| productViewed          | Tracking the product cards visited by a user. The event is used for ranking items / categories and sending triggers for browse abandonment.                                 |
| productCategoryViewed  | Tracking the product categories viewed by a user. The event is used for the triggers like *Website visit with a category view* and *Website visit without a category view*. |
| productAddedToWishlist | Tracking products added to the wishlist. The event is used for processing and displaying recommendations and sending the wishlist related triggers.                         |
| cartUpdated            | Tracking updates of the shopping cart. The event is used for the shopping cart related triggers.                                                                            |
| orderCreated           | An order creation event.                                                                                                                                                    |
| orderUpdated           | An order updating event.                                                                                                                                                    |
| orderDelivered         | The existing order status changes to DELIVERED.                                                                                                                             |
| orderCancelled         | The existing order status changes to CANCELLED.                                                                                                                             |
| searchRequest          | Tracking the search requests. The event is used for the triggers like *Abandoned search*.                                                                                   |

Use the following method for activity tracking:

```kotlin
Reteno.logEcommerceEvent(ecomEvent: EcomEvent)
```
```java
Reteno.logEcommerceEvent(EcomEvent ecomEvent)
```

Provide all the required parameters for the EcomEvent model.

## Base EcomEvent model

```kotlin
sealed class EcomEvent(open val occurred: ZonedDateTime)
```

This means that any child EcomEvent must contain the information about the time of event occurrence.

## Product Viewed

Fire this event when a user views a product card. 

The `ProductViewed` event model:

```kotlin
data class ProductViewed @JvmOverloads constructor(
    val product: ProductView,
    val currencyCode: String? = null,
    override val occurred: ZonedDateTime = ZonedDateTime.now()
) : EcomEvent(occurred)
```

`CurrencyCode` must be in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217 "\{rel='nofollow'}") format. Supported currencies: USD, EUR, UAH. If the currency is not set, the organization's default currency is used.

The `ProductView` model:

```kotlin
data class ProductView(
    val productId: String,
    val price: Double,
    val isInStock: int,
    val attributes: List<Attributes>? = null
)
```

`Attributes` is a list of the arbitrary parameters that may be added to the `ProductView` model:

```kotlin
data class Attributes(
    val name: String,
    val value: List<String?>
)
```

#### Usage example

```kotlin
val attributes = listOf(Attributes("key", listOf("parameterValue")))
val productView = ProductView("productId", 123.33, true, attributes)
val ecomEvent: EcomEvent = EcomEvent.ProductViewed(productView, "USD")
getReteno().logEcommerceEvent(ecomEvent)
```
```java
List<Attributes> attributes = new ArrayList<>();
attributes.add(new Attributes("key", Collections.singletonList("parameterValue")));
ProductView productView = new ProductView("productId", 123.33, true, attributes);
EcomEvent ecomEvent = new EcomEvent.ProductViewed(productView, "USD");
getReteno().logEcommerceEvent(ecomEvent);
```

## Product Category Viewed

Fire this event when a user views a category. 

The `ProductCategoryViewed` event model:

```kotlin
data class ProductCategoryViewed @JvmOverloads constructor(
    val category: ProductCategoryView,
    override val occurred: ZonedDateTime = ZonedDateTime.now()
) : EcomEvent(occurred)
```

The `ProductCategoryView` model:

```kotlin
data class ProductCategoryView(
    val productCategoryId: String,
    val attributes: List<Attributes>? = null
)
```

`Attributes` is a list of the arbitrary parameters that may be added to the `ProductCategoryView` model:

```kotlin
data class Attributes(
    val name: String,
    val value: List<String?>
)
```

#### Usage example

```kotlin
val attributes = listOf(Attributes("key", listOf("parameterValue")))
val productCategoryView = ProductCategoryView("productCategoryId", attributes)
val ecomEvent: EcomEvent = EcomEvent.ProductCategoryViewed(productCategoryView)
getReteno().logEcommerceEvent(ecomEvent)
```
```java
List<Attributes> attributes = new ArrayList<>();
attributes.add(new Attributes("key", Collections.singletonList("parameterValue")));
ProductCategoryView productCategoryView = new ProductCategoryView("productCategoryId", attributes);
EcomEvent ecomEvent = new EcomEvent.ProductCategoryViewed(productCategoryView);
getReteno().logEcommerceEvent(ecomEvent);
```

## Product Added to Wishlist

Fire this event when a user adds a product to the wishlist.

The `ProductAddedToWishlist` event model:

```kotlin
data class ProductAddedToWishlist @JvmOverloads constructor(
    val product: ProductView,
    val currencyCode: String? = null,
    override val occurred: ZonedDateTime = ZonedDateTime.now()
) : EcomEvent(occurred)
```

`CurrencyCode` must be in [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217 "\{rel='nofollow'}") format. Supported currencies: USD, EUR, UAH. If the currency is not set, the organization's default currency is used.

The `ProductView` model:

```kotlin
data class ProductView(
    val productId: String,
    val price: Double,
    val isInStock: int,
    val attributes: List<Attributes>? = null
)
```

`Attributes` is a list of the arbitrary parameters that may be added to the `ProductView` model:

```kotlin
data class Attributes(
    val name: String,
    val value: List<String?>
)
```

#### Usage example

```kotlin
val attributes = listOf(Attributes("key", listOf("parameterValue")))
val productView = ProductView("productId", 123.33, true, attributes)
val ecomEvent: EcomEvent = EcomEvent.ProductAddedToWishlist(productView, "USD")
getReteno().logEcommerceEvent(ecomEvent)
```
```java
List<Attributes> attributes = new ArrayList<>();
attributes.add(new Attributes("key", Collections.singletonList("parameterValue")));
ProductView productView = new ProductView("productId", 123.33, true, attributes);
EcomEvent ecomEvent = new EcomEvent.ProductAddedToWishlist(productView, "USD");
getReteno().logEcommerceEvent(ecomEvent);
```

## Cart Updated

Fire this event when a user updates a shopping cart.

The `cartUdpated` event transmits not the fact of adding a specific product to the cart, but the current state of the cart. If the first product is added to the cart, then an array with one product is passed in the `cartUdpated` event. If a second, third, etc. product is added, then an array of two, three, etc. products is transmitted in the `cartUdpated` events. The same logic works when removing products from the cart.

In each `cartUdpated` event, the `cartId` parameter must be passed. This is a unique identifier of the current state of the cart. Each time you send the `cartUdpated` event, you must pass a new `cartId` value that will be different from the previous ones.

The `cartUpdated` event model:

```kotlin
data class CartUpdated @JvmOverloads constructor(
    val cartId: String,
    val products: List<ProductInCart>,
    val currencyCode: String? = null,
    override val occurred: ZonedDateTime = ZonedDateTime.now()
) : EcomEvent(occurred)
```

`CurrencyCode` must be in the [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217 "\{rel='nofollow'}") format. Supported currencies: USD, EUR, UAH. If the currency is not set, the organization's default currency is used.

The `ProductInCart` model:

```kotlin
data class ProductInCart(
    val productId: String,
    val quantity: Int,
    val price: Double,
    val discount: Double? = null,
    val name: String? = null,
    val category: String? = null,
    val attributes: List<Attributes>? = null
)
```

`Attributes` is a list of the arbitrary parameters that may be added to the `ProductView` model:

```kotlin
data class Attributes(
    val name: String,
    val value: List<String?>
)
```

#### Usage example

```kotlin
val attributes = listOf(Attributes("key", listOf("parameterValue")))
val productInCart = ProductInCart(
    "productId",
    12,
    11.05,
    0.05,
    "productName",
    "productCategory",
    attributes
)
val products = listOf(productInCart)
val ecomEvent: EcomEvent = EcomEvent.CartUpdated("cartId", products, "USD")
getReteno().logEcommerceEvent(ecomEvent)
```
```java
List<Attributes> attributes = new ArrayList<>();
attributes.add(new Attributes("key", Collections.singletonList("parameterValue")));
ProductInCart productInCart = new ProductInCart(
        "productId",
        12,
        11.05,
        0.05,
        "productName",
        "productCategory",
        attributes);
List<ProductInCart> products = Collections.singletonList(productInCart);
EcomEvent ecomEvent = new EcomEvent.CartUpdated("cartId", products, "USD");
getReteno().logEcommerceEvent(ecomEvent);
```

## Order Сreated

Fire this event when a user creates an order.

The `OrderCreated` event model:

```kotlin
data class OrderCreated @JvmOverloads constructor(
    val order: Order,
    val currencyCode: String? = null,
    override val occurred: ZonedDateTime = ZonedDateTime.now()
) : EcomEvent(occurred)
```

`CurrencyCode` must be in the [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217 "\{rel='nofollow'}") format. Supported currencies: USD, EUR, UAH. If the currency is not set, the organization's default currency is used.

The `Order` model:

```kotlin
data class Order(
       // The order ID in the external system (required).
    val externalOrderId: String,
    // The ID of a customer in the external system
    val externalCustomerId: String?,
    // The total cost of an order (required).
    val totalCost: Double,
    // The status of an order (required). Possible values: DELIVERED, IN_PROGRESS, CANCELLED, INITIALIZED. Only DELIVERED orders are used in the RFM analysis.
    val status: OrderStatus,
    // The date and time of an order (required).
    val date: ZonedDateTime,
    // The shopping cart ID. Allows to match an order with the shopping cart related events. *Important optional parameter*
    val cartId: String? = null,
    // The customer email address.
    val email: String? = null,
    // The customer phone number.
    val phone: String? = null,
    // The customer first name.
    val firstName: String? = null,
    // The customer last name.
    val lastName: String? = null,
    // Shipping cost.
    val shipping: Double? = null,
    // Discount.
    val discount: Double? = null,
    // The tax amount.
    val taxes: Double? = null,
    // The link to the order.
    val restoreUrl: String? = null,
    // The order status description.
    val statusDescription: String? = null,
    // The store ID (if you manage several stores in one Yespo account).
    val storeId: String? = null,
    // "Online" \ "offline" values for segmentation. If the field is empty or contains any other value, the default value is "online".
    val source: String? = null,
    // Delivery method.
    val deliveryMethod: String? = null,
    // Payment method.
    val paymentMethod: String? = null,
    // Delivery address.
    val deliveryAddress: String? = null,
    // Array of ordered products.
    val items: List<OrderItem>? = null,
    // Additional fields.
    val attributes: List<Attributes>? = null
)
```

Note: `items` is a required parameter

Alternatively, you may use the `Order.Builder` class, as convenient:

```kotlin
data class OrderBuilder(
    val externalOrderId: String,
    val externalCustomerId: String?,
    val totalCost: Double,
    val status: OrderStatus,
    val date: ZonedDateTime
) {
    var cartId: String? = null
    var email: String? = null
    var phone: String? = null
    var firstName: String? = null
    var lastName: String? = null
    var shipping: Double? = null
    var discount: Double? = null
    var taxes: Double? = null
    var restoreUrl: String? = null
    var statusDescription: String? = null
    var storeId: String? = null
    var source: String? = null
    var deliveryMethod: String? = null
    var paymentMethod: String? = null
    var deliveryAddress: String? = null
    var items: List<OrderItem>? = null
    var attributes: List<Attributes>? = null

    fun build(): Order = Order(
        externalOrderId = externalOrderId,
        externalCustomerId = externalCustomerId,
        totalCost = totalCost,
        status = status,
        date = date,
        cartId = cartId,
        email = email,
        phone = phone,
        firstName = firstName,
        lastName = lastName,
        shipping = shipping,
        discount = discount,
        taxes = taxes,
        restoreUrl = restoreUrl,
        statusDescription = statusDescription,
        storeId = storeId,
        source = source,
        deliveryMethod = deliveryMethod,
        paymentMethod = paymentMethod,
        deliveryAddress = deliveryAddress,
        items = items,
        attributes = attributes
    )
}
```

The `OrderItem` model:

```kotlin
data class OrderItem(
    // ID of product in the external system (required).
    val externalItemId: String,
    // Product name (required).
    val name: String,
    // Product category (required).
    val category: String,
    // Number of items (required).
    val quantity: Double,
    // Product price (required).
    val cost: Double,
    // Link to product page (required).
    val url: String,
    // Link to a product image.
    val imageUrl: String? = null,
    // Short description of product.
    val description: String? = null
)
```

`Attributes` is a list of the arbitrary parameters that may be added to the `ProductView` model:

```kotlin
data class Attributes(
    val name: String,
    val value: List<String?>
)
```

#### Example of usage with `Order.Builder` and `Order`

```kotlin
val attributes: MutableList<Attributes> = ArrayList<Attributes>()
attributes.add(Attributes("key", listOf("parameterValue")))

val orderItem = OrderItem(
    "externalItemId",
    "name",
    "category",
    12.0,
    11.23,
    "https://url.com",
    "https://image.url.com",
    "description"
)
val orderItems = listOf(orderItem)

val order = Order(
    externalOrderId = "externalOrderId",
    externalCustomerId = "externalCustomerId",
    totalCost = 123.44,
    status = OrderStatus.INITIALIZED,
    date = ZonedDateTime.now(),
    cartId = "CartId",
    email = "Email",
    phone = "Phone",
    firstName = "FirstName",
    lastName = "LastName",
    shipping = 12.22,
    discount = 0.05,
    taxes = 0.15,
    restoreUrl = "RestoreUrl",
    statusDescription = "StatusDescription",
    storeId = "StoreId",
    source = "Source",
    deliveryMethod = "DeliveryMethod",
    paymentMethod = "PaymentMethod",
    deliveryAddress = "DeliveryAddress",
    items = orderItems,
    attributes = attributes
)

val ecomEvent: EcomEvent = EcomEvent.OrderCreated(order, "USD")
getReteno().logEcommerceEvent(ecomEvent)
```
```java
List<Attributes> attributes = new ArrayList<>();
attributes.add(new Attributes("key", Collections.singletonList("parameterValue")));

OrderItem orderItem = new OrderItem(
        "externalItemId",
        "name",
        "category",
        12,
        11.23,
        "https://url.com",
        "https://image.url.com",
        "description");
List<OrderItem> orderItems = Collections.singletonList(orderItem);

OrderBuilder orderBuilder = new OrderBuilder(
        "externalOrderId",
        "externalCustomerId",
        123.44,
        OrderStatus.INITIALIZED,
        ZonedDateTime.now()
);
orderBuilder.setCartId("CartId");
orderBuilder.setEmail("Email");
orderBuilder.setPhone("Phone");
orderBuilder.setFirstName("FirstName");
orderBuilder.setLastName("LastName");
orderBuilder.setShipping(12.22);
orderBuilder.setDiscount(0.05);
orderBuilder.setTaxes(0.15);
orderBuilder.setRestoreUrl("RestoreUrl");
orderBuilder.setStatusDescription("StatusDescription");
orderBuilder.setStoreId("StoreId");
orderBuilder.setSource("Source");
orderBuilder.setDeliveryMethod("DeliveryMethod");
orderBuilder.setPaymentMethod("PaymentMethod");
orderBuilder.setDeliveryAddress("DeliveryAddress");
orderBuilder.setItems(orderItems);
orderBuilder.setAttributes(attributes);

EcomEvent ecomEvent = new EcomEvent.OrderCreated(orderBuilder.build(), "USD");
getReteno().logEcommerceEvent(ecomEvent);
```

## Order Updated

Fire this event when a user updates the order. This event is very similar to `OrderCreated`. The only difference is that if an order already exists in the Reteno database, it is updated with the provided parameters. Otherwise, a new order is created using the provided parameters. This is an `Upsert` method. 

#### Usage example

```kotlin
val ecomEvent: EcomEvent = EcomEvent.OrderUpdated(order, "USD")
getReteno().logEcommerceEvent(ecomEvent)
```
```java
EcomEvent ecomEvent = new EcomEvent.OrderUpdated(orderBuilder.build(), "USD");
getReteno().logEcommerceEvent(ecomEvent);
```

## Order Delivered

Fire this event when the status of an order changes to `DELIVERED`. If an order does not exist, the event is ignored.

The `OrderDelivered` event model:

```kotlin
data class OrderDelivered @JvmOverloads constructor(
    val externalOrderId: String,
    override val occurred: ZonedDateTime = ZonedDateTime.now()
) : EcomEvent(occurred)
```

#### Usage example

```kotlin
val ecomEvent: EcomEvent = EcomEvent.OrderDelivered("externalOrderId")
getReteno().logEcommerceEvent(ecomEvent)
```
```java
EcomEvent ecomEvent = new EcomEvent.OrderDelivered("externalOrderId");
getReteno().logEcommerceEvent(ecomEvent);
```

## Order Cancelled

Fire this event when the status of an order changes to `CANCELLED`. If an order does not exist, the event is ignored.

The `OrderCancelled` event model:

```kotlin
data class OrderCancelled @JvmOverloads constructor(
    val externalOrderId: String,
    override val occurred: ZonedDateTime = ZonedDateTime.now()
) : EcomEvent(occurred)
```

#### Usage example

```kotlin
val ecomEvent: EcomEvent = EcomEvent.OrderCancelled("externalOrderId")
getReteno().logEcommerceEvent(ecomEvent)
```
```java
EcomEvent ecomEvent = new EcomEvent.OrderCancelled("externalOrderId");
getReteno().logEcommerceEvent(ecomEvent);
```

## Search Request

Track the search requests for the triggers like *Abandoned search*.

The `SearchRequest` event model:

```kotlin
data class SearchRequest @JvmOverloads constructor(
    val search: String,
    val isFound: Boolean = false,
    override val occurred: ZonedDateTime = ZonedDateTime.now()
) : EcomEvent(occurred)
```

#### Usage example

```kotlin
val ecomEvent: EcomEvent = EcomEvent.SearchRequest("SearchThisString", true)
getReteno().logEcommerceEvent(ecomEvent)
```
```java
EcomEvent ecomEvent = new EcomEvent.SearchRequest("SearchThisString", true);
getReteno().logEcommerceEvent(ecomEvent);
```

## Unsupported Events

When you want to track the customer activity and cannot find the appropriate `EcomEvent.EventType`, you can use the `Reteno.logEvent` method:

```kotlin
val params: List<Parameter> = listOf(Parameter("key1", "value1"), Parameter("key2", null))
reteno.logEvent(Event.Custom("eventTypeKey", ZonedDateTime.now(), params))
```
```java
List<Parameter> params = new ArrayList<>();
params.add(new Parameter("key1", "value1"));
params.add(new Parameter("key2", null));

Reteno.logEvent(new Event.Custom("eventTypeKey", ZonedDateTime.now(), params));
```
