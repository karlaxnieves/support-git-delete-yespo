---
title: Segmentation by Web Tracking Events
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Segmentation by Web Tracking Events | Yespo Guide
  description: >-
    The document explains using web tracking data for dynamic segmentation,
    covering events like store, product, and predicted actions, with an example
    of segmenting by user actions.
  robots: index
next:
  description: ''
---
Use data about the online behavior of your website visitors for flexible segmentation and targeting.

[Learn more about the possibilities and settings of web tracking >](https://docs.yespo.io/docs/web-tracking-overview)

Specify the period, and the system will analyze the activity of all contacts who visited your online store at a certain time. A combination of activity parameters will help build an accurate target segment that changes in real-time. [Learn more about working with dynamic segments >](https://docs.yespo.io/docs/how-add-dynamic-segment) 

## Segmentation Parameters

After enabling web tracking, 3 additional categories will appear in the contact parameters:

### 1. Online Store Event

The category includes the following events:

* Page viewed,
* Category page viewed,
* Added to cart,
* Online orders,
* Offline orders.
* Search request,
* Added to wishlist,
* Probability.

### 2. Product Event

The category includes the following events:

* Abandoned carts,
* Abandoned browses.
* Viewed item is in a stock,
* Item from wishlist is in stock,
* Regular demand,
* Price drop.

Some features may depend on your plan, [see details >](https://yespo.io/tarif-universum)

<Image align="center" width="80% " src="https://files.readme.io/2c05b5898c3b52b862011c68ff46f0ed2e086676c438f7874d4d0e29331e88d9-Web_tracking_segmentation_1.webp" />

### 3. Predicted Event

The ***Purchase likelihood*** parameter uses machine learning models to select contacts who are most likely to purchase within the next 30 days. This segmentation method allows you to interact only with the most potential buyers, so you do not waste your budget on those with a low chance of buying.

<Image align="center" width="80% " src="https://files.readme.io/47650b2fcbee81a4be8236ecef92fa39997335fb10a594374a6ee3362c94be21-purchase-likelihood.webp" />

* **Sure buyers** are contacts with the highest purchase likelihood.
* **Potential buyers** — contacts with a high purchase likelihood (excluding *Sure* buyers).
* **Unlikely buyers** are contacts with a low purchase likelihood.
* **Undecided buyers** — contacts with a very low purchase likelihood (excluding *Unlikely* buyers).
* The ***Recall***  parameter allows you to manually define what percentage of purchase probability to take into account when building a segment. For example, a recall value of 80% means that the segment will include 80% of potential buyers. Reducing the recall value also decreases the size of the segment, but it will include contacts who are more likely to make a purchase.

> 📘 Recommendation
>
> Use purchase possibility segmentation when you want to reduce the cost of your messaging without losing the potential revenue it should generate. By leaving only the most likely buyers in the target segment, you will reduce the number of messages sent, but at the same time retain as many possible orders as possible.

## Characteristics of Segmentation Parameters

Most of the parameters have 2 groups of characteristics:

1. **Required fields** — characteristics of pages and products viewed, ordered or added to the cart.

<Image align="center" width="80% " src="https://files.readme.io/72234e797ac8a453aec6ad3bd879f0e9dfbe9c55e37f143ba6405aadba08a6bb-Web_tracking_segmentation_2.webp" />

2. **Audience** — characteristics of traffic sources, devices of your site visitors, etc.

<Image align="center" width="80% " src="https://files.readme.io/d4746e9bb37a30e0580432ee1a8c38cac87df9a64b28cad3a37a3b91a8131743-Web_tracking_segmentation_3.webp" />

In addition, you can use segmentation by any custom fields from your product feed (**Additional fields**).

## Segmentation Conditions

Each characteristic has a number of conditions. For example, here are the required page view fields and their conditions:

* ID (equals, does not equals, one of);  
* Product name, product brand, product URL, product category  (contains, equals, does not equal, one of, one of); 
* Price (equals, greater than, less than);
* Product in stock (no/yes).

## Example of Creating a Conditional Group Based on Web Tracking Data

**Task:** to build a segment of those who have added the Beginner’s Yoga course to their favorites within the last 12 hours.

**Building the segment:**

1. When creating the dynamic segment, click the *Add card* button.

<Image align="center" width="80% " src="https://files.readme.io/837007bbb12324433b65ebb01412074646dc394a9e94c56bf31d83b9830bb555-Web_tracking_segmentation_4.webp" />

2. In the *Added to wishlist* parameter → required *Name* field, specify: *Equals* → Beginner’s Yoga.

<Image align="center" width="80% " src="https://files.readme.io/0d8d46117e13276669cafe849294aa61cd07910530f3b945ca7066bd75067300-Web_tracking_segmentation_5.webp" />

3. The condition will appear in the contact card — enter during 12 last hours.

<Image align="center" width="80% " src="https://files.readme.io/b00bc6c4ad51a8f426a53588d5ab1cdf536a37198348249a30fd8e7b5c908a91-Screenshot_8.webp" />

4. Click the *Done* button.

<Image align="center" width="80% " src="https://files.readme.io/975e43592e69affe4ca9df7c8b99dde1baacbda08e4b0745f5d736f85b63851d-Screenshot_7.webp" />
