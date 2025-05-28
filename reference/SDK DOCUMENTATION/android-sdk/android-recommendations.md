---
title: Android Recommendations
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
You can personalize the user experience and increase sales by adding recommendations of your goods and services to an app. The passed recommendations are based on the customer activity data and include the following options:

* **Out of stock** - a selection based on similar items.
* **Cross-selling** - offer of related products. The selected items are based on those added to the cart.
* **Upselling** - offering based on more expensive and complementary goods and services to increase the order value.
* **Potential purchase** - The selected items are based on the orders of users who have purchased this product.
* **Personal recommendations** - based on the customer's purchase and browsing history.
* **Other** - an offer is created individually if the required algorithm is not available among our platform's pre-configured algorithms.

> 📘 Note
>
> Each type of recommendation uses different requests having their own algorithms and rules since they take data from different sources.

> 📘 Note
>
> Recommendations are available in SDK starting from version **1.3.0**.

#### Reteno Recommendations

To get an instance of the `Recommendations` object, you need to use the `Reteno.recommendation` property.

```java
reteno.getRecommendation();
```

```kotlin
reteno.recommendation
```

E.g.

```kotlin
val recommendation = reteno.recommendation
```

## Get recommendations

Before starting using recommendations you have to meet the following conditions:

* Set up web tracking or tracking for mobile apps.
* Create a data source with a required algorithm for each recommendation type to use its ID when calling an API.

Method signature:

```swift
/**
 * Obtain Recommendations.
 *
 * @param recomVariantId recommendation variant id. It is in r{recomId}v{variantId} format. Where recomId and variant Id are integer identifiers
 * @param recomRequest [com.reteno.core.domain.model.recommendation.get.RecomRequest] model
 * @param responseClass Class type to cast response to
 * @param responseCallback Type-safe [com.reteno.core.recommendation.GetRecommendationResponseCallback]
 *
 * @see [com.reteno.core.domain.model.recommendation.get.RecomRequest]
 * @see [com.reteno.core.recommendation.GetRecommendationResponseCallback]
 */
fun <T : RecomBase> fetchRecommendation(
    recomVariantId: String,
    recomRequest: RecomRequest,
    responseClass: Class<T>,
    responseCallback: GetRecommendationResponseCallback<T>
)
```

To get `recomVariantId` parameter, copy ID from JS script example in the recom Parameters screen. It is in r\{recomId}v\{variantId} format. Where recomId and variant Id are integer identifiers.

<Image align="center" width="80%" src="https://files.readme.io/69cf8bf-RecomVariantId.png" />

There are three types of recommendations algorythms:

* Personal based recommendations. In this case you don't need to pass `productIds` and `categoryId` parameters.
* Category based recommendations. In this case `categoryId` parameter is required.
* Product based recommendations. This algorithm requres passing `productIds` parameter.

`RecomRequestModel`

```kotlin
/**
 * This class describes the paramter model for getting Recommendations from Reteno SDK
 *
 * Return all product fields if a request does not contain fields parameter.
 *
 * Return only productId if fields array in a request is empty.
 *
 * @property products product IDs for product-based algorithms
 * @property category product category key for category-based algorithms
 * @property fields fields to return in response. If fields is null - all fields in the model returned
 * @property filters additional algorithm filters map. Filters are not supported yet. Reserved for the future.
 */
data class RecomRequest @JvmOverloads constructor(
    val products: List<String>?,
    val category: String?,
    val fields: List<String>? = null,
    val filters: RecomFilter? = null
)
```

In the `fields` parameter pass recommended product model fields you want to receive in the response.

> 📘 Note
>
> SDK returns all product fields if a request does not contain `fields` parameter and only `productId` if `fields` array in a request is empty.

`RecomFilter`

```kotlin
data class RecomFilter(
    val name: String,
    val values: List<String>
)
```

You should provide the class your wish the response to be casted to in `responseClass: Class<T>` argument. If response casting is failed you will receive plain response in String format and then you can operate it as you wish.

Also provide the callback where you will receive the response:

```kotlin
interface GetRecommendationResponseCallback<T : RecomBase> {

    /**
     * @param response Response casted to a provided type
     */
    fun onSuccess(response: Recoms<T>)

    /**
     * @param response This callback is invoked if casting to a provided type fails. Provides raw JSON String
     */
    fun onSuccessFallbackToJson(response: String)

    /**
     * @param statusCode Rest status code (500, 400, etc)
     * @param response response message from the server
     * @param throwable exception thrown returned in this parameter if any
     */
    fun onFailure(statusCode: Int?, response: String?, throwable: Throwable?)
}
```

In the end you will receive recommendations either in the `onSuccess(response: Recoms)` callback method (if casting to provided model is successful) or in `fun onSuccessFallbackToJson(response: String)` if casting failed. If there is any problem with the server or if the request was created incorrectly you will receive all the information in the callback `fun onFailure(statusCode: Int?, response: String?, throwable: Throwable?)`.\
Note the possible errors from the server:

<Table>
  <thead>
    <tr>
      <th>
        <div style="width:350px">**Case**</div>
      </th>

      <th>
        Status
      </th>

      <th>
        Message
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Invalid request parameters
      </td>

      <td>
        400
      </td>

      <td>
        `recomVariantId` <br/>- must be specified<br/>- Invalid format: %s. Must be **r\{recomId}v\{variantId}**
      </td>
    </tr>

    <tr>
      <td>
        `recomVariantId`

         doesn’t exist
      </td>

      <td>
        422
      </td>

      <td>
        Unknown recomVariantId 

        `r1105v148`
      </td>
    </tr>

    <tr>
      <td>
        `product`

         is empty for product-based algorithms
      </td>

      <td>
        400
      </td>

      <td>
        product ids must be set
      </td>
    </tr>

    <tr>
      <td>
        `category`

         is empty for category-based algorithms
      </td>

      <td>
        400
      </td>

      <td>
        category id must be set
      </td>
    </tr>
  </tbody>
</Table>

## Usage example

#### 1\. Create recommended product model.

Make sure to extend your model from RecomBase as it should always contain at least `productId` field

````kotlin
data class RecommendationResponse(
    @SerializedName("productId")
    override val productId: String,
    @SerializedName("descr")
    val descr: String?
) : RecomBase
```
`RecomBase`:

```kotlin
interface RecomBase {
    val productId: String
}
````

```java
public class RecommendationResponse implements RecomBase {

    @SerializedName("productId")
    private String productId;
    @SerializedName("descr")
    private String descr;

    public RecommendationResponse(String productId, String descr) {
        this.productId = productId;
        this.descr = descr;
    }

    @NonNull
    @Override
    public String getProductId() {
        return productId;
    }

    public String getDescr() {
        return descr;
    }
}
```

> 📘
>
> **Tip:** at first and see what properties will be in the response model.

#### 2\. Make a request

Function works with generic response type, so you need to specify result type as follows:

```kotlin
val request = RecomRequest(
    products = listOf("product1", "product2"),
    category = null,
    fields = listOf("productId", "descr", "date_created_as", "date_created_es"),
    filters = null
)

reteno.recommendation.fetchRecommendation<RecommendationResponse>(
    "r123v123",
    request,
    RecommendationResponse::class.java,
    object : GetRecommendationResponseCallback<RecommendationResponse> {
        override fun onSuccess(response: Recoms<RecommendationResponse>) {
            // handle success
        }

        override fun onSuccessFallbackToJson(response: String) {
            // handle success when casting failed
        }

        override fun onFailure(statusCode: Int?, response: String?, throwable: Throwable?) {
            // handle error
        }
    })
```
```java
RecomRequest request = new RecomRequest(
    List.of("prodcut1", "product2"), 
    category, 
    List.of("productId", "descr", "date_created_as", "date_created_es"), 
    null
);


getReteno().getRecommendation().fetchRecommendation("r123v123", request, RecommendationResponse.class, new GetRecommendationResponseCallback<RecommendationResponse>() {
    @Override
    public void onSuccess(@NonNull Recoms<RecommendationResponse> response) {
        // handle success
    }

    @Override
    public void onSuccessFallbackToJson(@NonNull String response) {
        // success when casting failed
    }

    @Override
    public void onFailure(@Nullable Integer statusCode, @Nullable String response, @Nullable Throwable throwable) {
        // handle error
    }
});
```

> 📘 Note
>
> The Recoms model, where T is the model you wish to receive (`RecommendationResponse`):

```kotlin
data class Recoms<T: RecomBase>(
    val recoms: List<T>,
)
```

## Send recommendation events

Send events are cached locally and are sent to the server regularly in a batch of backend requests. So offline mode is supported.

Send events about showing user specific product recommendations or user clicks on recommended products via next SDK method:

```kotlin
/**
 * Log recommendation events
 * @param recomEvents - recommendation event to be logged
 *
 * @see [com.reteno.core.domain.model.recommendation.post.RecomEvents]
 */
fun logRecommendations(recomEvents: RecomEvents)
```

`RecomEvents` model:

```kotlin
/**
 * Model to log Recommendation events
 *
 * @param recomVariantId REQUIRED. Recommendation variant id. It is in r{recomId}v{variantId} format. Where recomId and variant Id are integer identifiers
 * @param recomEvents list of [com.reteno.core.domain.model.recommendation.post.RecomEvent]
 */
data class RecomEvents(
    val recomVariantId: String,
    val recomEvents: List<RecomEvent>?
)
```

`RecomEvent` model:

````kotlin
/**
 * Recommendation event
 *
 * @property recomEventType REQUIRED. Can be either IMPRESSIONS or CLICKS
 * @property occurred REQUIRED. Time in [java.time.ZonedDateTime]. Usually
 * ```
 * ZoneDateTime.now()
 * ```
 * @property productId REQUIRED. Id of the product
 *
 * @see [com.reteno.core.domain.model.recommendation.post.RecomEventType]
 */
data class RecomEvent(
    val recomEventType: RecomEventType,
    val occurred: ZonedDateTime,
    val productId: String
)
````

`RecomEventType` model:

```kotlin
enum class RecomEventType {
    IMPRESSIONS, CLICKS
}
```

#### Usage example:

```kotlin
val recomEvent1 = RecomEvent(RecomEventType.CLICKS, ZonedDateTime.now(), "product1")
val recomEvent2 = RecomEvent(RecomEventType.IMPRESSIONS, ZonedDateTime.now(), "product2")
val eventList: List<RecomEvent> = listOf(recomEvent1, recomEvent2)

val recomEvents = RecomEvents("r123v123", eventList)
reteno.recommendation.logRecommendations(recomEvents)
```
```java
RecomEvent recomEvent1 = new RecomEvent(RecomEventType.CLICKS, ZonedDateTime.now(), "product1");
RecomEvent recomEvent2 = new RecomEvent(RecomEventType.IMPRESSIONS, ZonedDateTime.now(), "product2");
List<RecomEvent> eventList = new ArrayList<>();
eventList.add(recomEvent1);
eventList.add(recomEvent2);

RecomEvents recomEvents = new RecomEvents("r123v123", eventList);
getReteno().getRecommendation().logRecommendations(recomEvents);
```
