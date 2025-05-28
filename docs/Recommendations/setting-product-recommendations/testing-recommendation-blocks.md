---
title: A/B Testing of Recommendation Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: A/B Testing of Recommendation Blocks | Yespo Guide
  description: >-
    A/B testing helps optimize recommendation blocks by evaluating different
    data sources, appearances, and placements based on CTR and conversions, with
    detailed settings and status indicators to identify the most effective
    options.
  robots: index
next:
  description: ''
---
A/B testing allows you to automatically determine the best result when displaying a recommendation block based on CTR and conversions.

You can test:

* data sources — for recommendations [in mobile applications](https://docs.yespo.io/docs/recommendations-in-mobile-app) and [received via JavaScript API](https://docs.yespo.io/docs/getting-api-recommendations), 
* names, data sources, appearance, and block placement — for [*Out the box*](https://docs.yespo.io/docs/product-recommendations-website) recommendations.

Identify the most effective options and create new blocks based on test results.

## A/B Testing Settings

1\. Go to the *Site → Recommendations* section and click on the desired recommendation.

<Image align="center" width="80% " src="https://files.readme.io/be062f720b51b3c9dd9cfbf4f1c1fe7de36ea3858fba145f6a65330b02fa7355-e-15.webp" />

2\. Go to the *A/B testing* tab and click the *Start A/B testing* button.

<Image align="center" width="80% " src="https://files.readme.io/39be08482ccb8ca2986c568f152e7e952ecb9edbfc5c93d208cc3cb5308c7015-e-11.webp" />

### Testing Parameters

1\. Select the number of variants to be tested — by default, this is two; to add more, click the corresponding button (the maximum number is 8).

2\. Specify the percentage weight of each variant or distribute it evenly by clicking the corresponding button.

3\. Add a description of the variants so that in the future, you can easily recognize the key differences between the variants being tested (optional).

<Image align="center" width="80% " src="https://files.readme.io/fd6feba7889c3eb0b2c9f68747b84b4d86d87241f51b791b695d32e8c00585e8-e-16.webp" />

Below, select the parameters you will test. Testing one parameter at a time is better to understand which factors influence the results.

**[Data source](https://docs.yespo.io/docs/create-data-source-recommendations)**. Specify which algorithm will generate recommendations. To change it, click the option and select the desired one from the list.

<Image align="center" width="80% " src="https://files.readme.io/bb9385a642e5451073fbf32e2c64fae80ca1aba87a3997f676b1f595519ae052-e-6.webp" />

**Placement**: Specify where you want to place the recommendations on the page.

<Image align="center" width="80% " src="https://files.readme.io/a4c74fd84101d32fe05927cea7dda65253dc2c93d0bb94e56c1bdf25adf24187-e-5.webp" />

**Appearance**: Specify the variants that will be included in the test.

<Image align="center" width="80% " src="https://files.readme.io/00e0c57f695ab723411e2fddf77883bc5afd1a7b3016cef67acedae0a6cf3e24-e-14.webp" />

**Titles**. Write down different options to see which one is more attractive.

<Image align="center" width="80% " src="https://files.readme.io/15b55c08ea623fb7bb8f5a2952b4eb3373e0efc4579e651314b3ddc06dc202fd-e-10.webp" />

After making your settings, click the *Save* button at the top of the page.

<Image align="center" width="80% " src="https://files.readme.io/7663a853d99d3a8fa796df2a50de1235c8653765c24ba279227f4f71d330b6c7-e-7.webp" />

## Testing Status and Its Assessment

In the general list of created recommendations, each recommendation that has been A/B tested has a corresponding mark in the form of a button.

<Image align="center" width="80% " src="https://files.readme.io/e4d5ad59a7d9cdbab592439fab80d1b54eaf0fee2c4f65aae78dc6d64d7e185b-e-3.webp" />

The button is colored differently depending on the current status (completed/not completed) and key results (by CTR and achieved conversions). When you hover over it, a short report opens. Click the *View test* button to view the results in detail.

<Image align="center" width="80% " src="https://files.readme.io/d4a192af1c40359c193d9e33672c625cf19295f77a5cdbb20b989c4da98b5681-e-1.webp" />

Color coding:

* The green button – testing is complete; there is a winner by CTR and conversion.
* The gray-yellow button indicates insufficient data to determine the winner by CTR; the conversion is the same.
* The yellow button – CTR and conversion statistics are the same, and testing continues.
* The green-yellow button indicates a winner by CTR, and conversion statistics are the same. Testing continues.
* The yellow-green button – there is a winner by conversion, and CTR results are the same.
* The grey button – there is insufficient data to determine the winner by any indicator.

## Test Results Report

The winner is displayed with the results obtained on the first screen of the test viewing.

<Image align="center" width="80% " src="https://files.readme.io/97272cd464e9600ff86a354352743d7e54dadcea9e5bb962f81390c171304f5f-e-12.webp" />

To determine a winner, one of the variants must be in the lead with a probability of at least 90%, and the difference in probability between the variants must be more than 5%. Testing will continue until this minimum threshold is reached.

If there is enough data, you can stop the test by clicking the *Choose Variant and finish test* button (the variant that performed better will be written in bold text).

If the winners by CTR and conversion are different variants, then only the winner by conversion can be the best since sales are more important than the click-through rate.

After describing the preferred option, a report with the testing results for each option is presented.

The green frame shows the winning variant's CTR and conversion rates.

<Image align="center" width="80% " src="https://files.readme.io/68deff0a060607751b1c72ef264e8faf9381c7695a1b257f3efe70d0b18aa427-e-2.webp" />

In the last block of the report (*Activity dynamics*), graphs visualize the results obtained compared to other test variants.

<Image align="center" width="80% " src="https://files.readme.io/b78aa2ef42401778584b73bf58e93db762677dd038026026b5fdffda4fbcc468-e-8.webp" />

To see the number of indicators for a certain period, hover over the graph:

<Image align="center" width="80% " src="https://files.readme.io/eede17e17c599bb5cf2abc6d0cd8d863391d1a86fecb56a9da87968751b90708-e-13.webp" />

The history of completed tests is displayed at the bottom of the page:

<Image align="center" width="80% " src="https://files.readme.io/f3b137a9c185f87a075634c3e1c5dcaf7021cdfa7a2a58698f447830d719ac52-e-9.webp" />
