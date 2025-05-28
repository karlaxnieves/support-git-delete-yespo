---
title: iOS Recommendations
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
You can personalize the user experience and increase sales by adding recommendations of your goods and services to an app.\
The passed recommendations are based on the customer activity data and include the following options:

* **Out of stock.** A selection based on similar items.
* **Cross-selling**. Offer of related products. The selected items are based on those added to the cart.
* **Upselling.** Offering based on more expensive and complementary goods and services to increase the order value.
* **Potential purchase.** The selected items are based on the orders of users who have purchased this product.
* **Personal recommendations** based on the customer's purchase and browsing history.
* **Other.** An offer is created individually if the required algorithm is not available among our platform's pre-configured algorithms.

> 📘 Note
>
> Each type of recommendation uses different requests having their own algorithms and rules since they take data from different sources.

> 📘 Note
>
> SDK Version Recommendations are available in version **1.3.0** and later.

***

## Reteno Recommendations

To get an instance of the `Recommendations` object, you need to use the `Reteno.recommendations()` call which you can see below:

```swift
let recoms: Recommendations = Reteno.recommendations()
```

## Get recommendations

Before starting using recommendations you have to meet the following conditions:

* Set up web tracking or tracking for mobile apps.
* Create a data source with a required algorithm for each recommendation type to use its ID when calling an API.

```swift
/// Get product recommendations
///
/// - Parameter recomVariantId: recommendations variant identificator. 
/// - Parameter productIds: product IDs for product-based algorithms
/// - Parameter categoryId: product category ID for category-based algorithms
/// - Parameter filters: additional algorithm filters array
/// - Parameter fields: response model fields keys
public func getRecoms<T: RecommendableProduct>(
    recomVariantId: String,
    productIds: [String],
    categoryId: String,
    filters: [RecomFilter]?,
    fields: [String]?,
    completionHandler: @escaping (Result<[T], Error>) -> Void
)
```

To get `recomVariantId` parameter, copy ID from JS script example in the recom Parameters screen. It is in r\{recomId}v\{variantId} format. Where recomId and variant Id are integer identifiers.

There are three types of recommendations algorythms:

* Personal based recommendations. In this case you don't need to pass `productIds` and `categoryId` parameters.
* Category based recommendations. In this case `categoryId` parameter is required.
* Product based recommendations. This algorithm requres passing `productIds` parameter.

Filter model structure:

```swift
public struct RecomFilter {
    let name: String // attribute name
    let values: [String] // array of attribute values
}
```

In the `fields` parameter pass recommended product model fields you want to receive in the response.

> 📘 Note
>
> SDK returns all product fields if a request does not contain `fields` parameter and only `productId` if `fields` array in a request is empty.

## Usage example

### 1. Create recommended product model

```swift
struct Recommendation: Decodable, RecommendableProduct {
    
    let productId: String
    let name: String
    let description: String?
    let imageUrl: URL?
    let price: Float
    
    enum CodingKeys: String, CodingKey {
        case productId, name, description = "descr", imageUrl, price
    }
    
}
```

> 📘 Note
>
> Model should confirm `RecommendableProduct` protocol. This protocol describes required `productId` property.

```swift
import Foundation

public protocol RecommendableProduct: JSONInitable {
    
    var productId: String { get }
    
}
```

> 📘 **Tip:** To understand what product fields you can request, make request without `fields` parameter (provide `nil`) at first and see what properties will be in the response model.

### 2. Make a request

Function works with generic response type, so you need to specify result type in the closure `(result: Result<[Recommendation], Error>)`, set the model type you've created in the previous step.

```swift
Reteno.recommendations().getRecoms(
    recomVariantId: "r1105v1480",
    productIds: ["240-LV09", "24-WG080"],
    categoryId: "Default Category/Training/Video Download",
    filters: [],
    fields: ["productId", "name", "descr", "imageUrl", "price"]
) { [weak self] (result: Result<[Recommendation], Error>)  in
    switch result {
    case .success(let recoms):
        self?.recoms = recoms
        // handle success
         
    case .failure(let error):
        // handle error
    }
}
```

## Send recommendation events

Send events about showing user specific product recommendations or user clicks on recommended products via next SDK method:

```swift
/// Log recommendation event
///
/// - Parameter recomVariantId: recommendation identificator
/// - Parameter impressions: events describing that a specific product recommendation was shown to a user
/// - Parameter clicks: events describing that a user clicked a specific product recommendation
/// - Parameter forcePush: indicates if event should be send immediately or in the next scheduled batch.
public func logEvent(recomVariantId: String, impressions: [RecomEvent], clicks: [RecomEvent], forcePush: Bool = false)
```

Usage example:

```swift
Reteno.recommendations().logEvent(
    variantId: recomVariantId,
    impressions: [RecomEvent(date: Date(), productId: productId)],
    clicks: [[RecomEvent(date: Date(), productId: productId)]]
)
```
