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
You can personalize the user experience and increase sales by adding recommendations of your goods and services to an app.
The passed recommendations are based on the customer activity data and include the following options:

- **Out of stock.** A selection based on similar items.
- **Cross-selling**. Offer of related products. The selected items are based on those added to the cart.
- **Upselling.** Offering based on more expensive and complementary goods and services to increase the order value.
- **Potential purchase.** The selected items are based on the orders of users who have purchased this product.
- **Personal recommendations** based on the customer's purchase and browsing history.
- **Other.** An offer is created individually if the required algorithm is not available among our platform's pre-configured algorithms.
[block:callout]
{
  "type": "info",
  "body": "Each type of recommendation uses different requests having their own algorithms and rules since they take data from different sources.",
  "title": "Note"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "SDK Version Recommendations are available in version **1.3.0** and later.",
  "title": "Note"
}
[/block]
**** 

## Reteno Recommendations

To get an instance of the `Recommendations` object, you need to use the `Reteno.recommendations()` call which you can see below:


[block:code]
{
  "codes": [
    {
      "code": "let recoms: Recommendations = Reteno.recommendations()",
      "language": "swift"
    }
  ]
}
[/block]
## Get recommendations

Before starting using recommendations you have to meet the following conditions:

- Set up web tracking or tracking for mobile apps.
- Create a data source with a required algorithm for each recommendation type to use its ID when calling an API.
[block:code]
{
  "codes": [
    {
      "code": "/// Get product recommendations\n///\n/// - Parameter recomVariantId: recommendations variant identificator. \n/// - Parameter productIds: product IDs for product-based algorithms\n/// - Parameter categoryId: product category ID for category-based algorithms\n/// - Parameter filters: additional algorithm filters array\n/// - Parameter fields: response model fields keys\npublic func getRecoms<T: RecommendableProduct>(\n    recomVariantId: String,\n    productIds: [String],\n    categoryId: String,\n    filters: [RecomFilter]?,\n    fields: [String]?,\n    completionHandler: @escaping (Result<[T], Error>) -> Void\n)",
      "language": "swift"
    }
  ]
}
[/block]
To get `recomVariantId` parameter, copy ID from JS script example in the recom Parameters screen. It is in r{recomId}v{variantId} format. Where recomId and variant Id are integer identifiers.

There are three types of recommendations algorythms:

- Personal based recommendations. In this case you don't need to pass `productIds` and `categoryId` parameters.
- Category based recommendations. In this case `categoryId` parameter is required.
- Product based recommendations. This algorithm requres passing `productIds` parameter.

Filter model structure:
[block:code]
{
  "codes": [
    {
      "code": "public struct RecomFilter {\n    let name: String // attribute name\n    let values: [String] // array of attribute values\n}",
      "language": "swift"
    }
  ]
}
[/block]
In the `fields` parameter pass recommended product model fields you want to receive in the response.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "SDK returns all product fields if a request does not contain `fields` parameter and only `productId` if `fields` array in a request is empty."
}
[/block]
## Usage example

### 1. Create recommended product model
[block:code]
{
  "codes": [
    {
      "code": "struct Recommendation: Decodable, RecommendableProduct {\n    \n    let productId: String\n    let name: String\n    let description: String?\n    let imageUrl: URL?\n    let price: Float\n    \n    enum CodingKeys: String, CodingKey {\n        case productId, name, description = \"descr\", imageUrl, price\n    }\n    \n}",
      "language": "swift"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Model should confirm `RecommendableProduct` protocol. This protocol describes required `productId` property.",
  "title": "Note"
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "import Foundation\n\npublic protocol RecommendableProduct: JSONInitable {\n    \n    var productId: String { get }\n    \n}",
      "language": "swift"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "**Tip:** To understand what product fields you can request, make request without `fields` parameter (provide `nil`) at first and see what properties will be in the response model."
}
[/block]
### 2. Make a request

Function works with generic response type, so you need to specify result type in the closure `(result: Result<[Recommendation], Error>)`, set the model type you've created in the previous step.
[block:code]
{
  "codes": [
    {
      "code": "Reteno.recommendations().getRecoms(\n    recomVariantId: \"r1105v1480\",\n    productIds: [\"240-LV09\", \"24-WG080\"],\n    categoryId: \"Default Category/Training/Video Download\",\n    filters: [],\n    fields: [\"productId\", \"name\", \"descr\", \"imageUrl\", \"price\"]\n) { [weak self] (result: Result<[Recommendation], Error>)  in\n    switch result {\n    case .success(let recoms):\n        self?.recoms = recoms\n        // handle success\n         \n    case .failure(let error):\n        // handle error\n    }\n}",
      "language": "swift"
    }
  ]
}
[/block]
## Send recommendation events

Send events about showing user specific product recommendations or user clicks on recommended products via next SDK method:

[block:code]
{
  "codes": [
    {
      "code": "/// Log recommendation event\n///\n/// - Parameter recomVariantId: recommendation identificator\n/// - Parameter impressions: events describing that a specific product recommendation was shown to a user\n/// - Parameter clicks: events describing that a user clicked a specific product recommendation\n/// - Parameter forcePush: indicates if event should be send immediately or in the next scheduled batch.\npublic func logEvent(recomVariantId: String, impressions: [RecomEvent], clicks: [RecomEvent], forcePush: Bool = false)",
      "language": "swift"
    }
  ]
}
[/block]
Usage example:
[block:code]
{
  "codes": [
    {
      "code": "Reteno.recommendations().logEvent(\n    variantId: recomVariantId,\n    impressions: [RecomEvent(date: Date(), productId: productId)],\n    clicks: [[RecomEvent(date: Date(), productId: productId)]]\n)",
      "language": "swift"
    }
  ]
}
[/block]