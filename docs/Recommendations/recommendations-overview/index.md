---
title: Recommendations for Website
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Recommendations for Website | Yespo Guide
  description: >-
    Product recommendations enhance user experience and increase sales by
    suggesting relevant products based on product data, user behavior, and
    general patterns, with implementation options via JS API for custom setups
    or through the Yespo dashboard for templated sites.
  robots: index
next:
  description: ''
---
Product recommendations are a tool that helps online store visitors find the right products, and businesses — to increase the average check and income.

Depending on the goals, the algorithm for generating recommendations can be based on data about products, users, or specific patterns in the behavior of online store customers.

* **Product data** includes characteristics from the product feed: color, size, price, stock status, rating, etc. 
* **User data** is based on browsing and purchase history, demographic characteristics, and behavioral patterns.
* **Data on general user behavior patterns:** information about which products are more often bought together or which are viewed before purchasing a particular item.

Product recommendations are used on different pages of the site for various purposes. Below are the types of product recommendations that can be placed on the home page, category page, product page, and checkout page.

**1. Home page:**

* Recommendations based on user preferences (for example, views and purchases).
* Bestsellers and novelties.
* Special offers or discounts.

**2. Category pages:**

* The most popular products from the category.
* Bestsellers in the category.
* New arrivals or discounted items.
* Personalized recommendations based on browsing history, orders, user demographics, and product reviews.

**3. Product page:**

* Recommendations of similar products based on product characteristics.
* Recommendations of products that are often bought together.
* Personalized recommendations based on the user's browsing and purchase history.

**4. Checkout page:**

* Recommendations based on the contents of the cart (for example, additional items that may be of interest to the user).
* Recommendations based on discounts and promotions (for example, the *Buy Together* or *Get Free Shipping* offer).
* Personalized recommendations.

The purpose of displaying product recommendations on the website can be:

1. **Sales increment:** offer additional items that users may want to purchase along with the selected item, which increases the overall purchase cost.
2. **User experience improvement:** helping to find the right products, which makes the shopping experience more convenient and attractive.
3. **Customer loyalty development:** displaying exciting products for each visitor extends the retention time on the site and returns to the online store in the future.

## Ways to Set Up Recommendations in Yespo

We provide you with two ways to set up recommendations on the website: through the JS API or in the Yespo dashboard. The filtering logic for recommendation results in both options is set in Yespo. Still, the JS API allows you to customize the design of blocks and their placement using code and not through the admin panel.

### JS API: settings features

Since you can access your site logic, its internal handlers, adaptability settings, and complete product information, we recommend using settings via the JS API as a more accessible and reliable way (except for websites based on templating engines).

### Yespo account: settings features

Recommendations for websites based on templating engines (WordPress, Wix, etc.) should be fully customized in Yespo.

In other cases, this option may be used for projects that do not have the resources to develop in-house. Then our specialists are engaged in the design of recommendations. But remember that we will always have limited access to critical information on your part. This can lead to specific problems — for example, updating the site template is likely to break the display of recommendations.

## Guidelines for Setting Up Recommendations

Before starting the settings, [upload a product feed](https://docs.yespo.io/docs/importing-product-feed) to Yespo and [install the web tracking script](https://docs.yespo.io/docs/how-set-web-tracking-your-website) on your site.

### 1. JS API

Use the JavaScript API to get product recommendations. Calling the API and setting up the appearance of recommendation blocks and their placement will take place on your side. Implementation steps:

* [Set up the recommendation algorithm in Yespo](https://docs.yespo.io/docs/getting-api-recommendations).
* [Install a JS function on your website](https://docs.yespo.io/docs/recommendations-using-javascript-api) and call it to get recommendation data from Yespo.
* Create a recommendation block design on your side.

### 2. Yespo account

You can set up all the recommendation block functionality directly in Yespo. Implementation steps:

* [Create a recommendation block](https://docs.yespo.io/docs/product-recommendations-website).
* [Set up recommendation placements](https://docs.yespo.io/docs/placement-recommendations-webpage).
