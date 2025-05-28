---
title: Setting Up the JS API Recommendation Algorithm in Yespo
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up the JS API Recommendation Algorithm in Yespo | Yespo Guide
  description: >-
    The document guides on integrating product recommendations via Yespo JS API,
    covering installation, data feed upload, display setup, and handling API
    functions with event transmissions.
  robots: index
next:
  description: ''
---
Receive product recommendations via API and use the resulting list of products to display them in recommendation blocks on your site.

To use the API recommendations:

1. Install the JavaScript API on your site.
2. [Upload a product data feed](https://docs.yespo.io/docs/importing-product-feed) to your Yespo account.
3. Request recommendations from the required pages using the JavaScript API.
4. After receiving an array of products, set up the display of blocks on your side (appearance, placements, headings).

## Connecting API Recommendations

1. Go to the *Site → Recommendations* tab and click the *New recommendation* button.

<Image align="center" width="80% " src="https://files.readme.io/06e82d18aef2c966cf58de15d540fbf3d91fe40c51a79432874881119def32df-01_recom_en.webp" />

2. Select the *Product data for API* usage option

<Image align="center" width="80% " src="https://files.readme.io/5259a19fdfa0a45b1e960ff4d8b2ccef61023e238644c51cd37490fc49721e94-image5.webp" />

3. Each type has different algorithms for product selections, for example, bestsellers for the main page or personalized recommendations for the category page. *Any page* type is suitable for a wishlist, blog, promotions, etc.

<Image align="center" width="80% " src="https://files.readme.io/6ac20db336326126d98ab4192fb04fc842ee906b9217d59cf142fe8927a0c700-image6.webp" />

4. Specify [data source](https://docs.yespo.io/docs/creating-a-data-source-for-recommendations).

<Image align="center" width="80% " src="https://files.readme.io/c0e6bbebfadcbdda322445ba2c7053db40c1db6e68cbc3ef13a06da7e9127e1d-image3.webp" />

5. The system will generate a JavaScript function:

* Copy it to your JavaScript.
* Call the function when you need to get product recommendations.
* Use product data in your response at your discretion.
* Set up [*ProductImpression*](https://docs.yespo.io/docs/how-set-web-tracking-sending-events-java-scipt-request#impressions) event transmission.

<Image align="center" width="80% " src="https://files.readme.io/cdc9743d1dc0215a96d3adb9adf7059b0fe000b03890e8b9fd7fc1a164927b84-image2.webp" />

> 📘 Important
>
> In this recommendation type, the *ProductImpression* event is not automatically sent. Pass it when site visitors actually view the recommendation block. As parameters in the request, you need to pass the product ID and *container\_type*, which were returned in the *getRecommendations* response.

In the general list of recommendations, API recommendations will be marked with the corresponding icon.

<Image align="center" width="80% " src="https://files.readme.io/03cbcff048c584f85b9e09074989306055be4b53de98590a06b3bd640d9ea4ee-04_recom_en.webp" />

[Examples of JS API requests for different types of site pages >](https://docs.yespo.io/docs/recommendations-using-javascript-api)
