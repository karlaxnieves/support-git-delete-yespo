---
title: Testing the Products Block
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Testing the Products Block | Yespo Guide
  description: >-
    The document details testing the Products block in an email campaign by
    selecting a contact, previewing recommendations, and managing missing data
    by hiding or not sending.
  robots: index
next:
  description: ''
---
After [configuring the Products block](https://docs.yespo.io/docs/product-blocks), you can preview how the recommendations appear in the email on desktop and mobile devices.

You can test the block for an individual contact or a segment of contacts:

* If you are going to use the product block in a promo campaign, select a list of recipient contacts.
* If you are going to use the product block in a trigger campaign, select the dynamic segment on which the workflow with this email will be launched.

Consider an example of testing the **Products** block for **Abandoned view** workflow. 

## How to find out which segment is used in the workflow

1. Go to **Automation** → **Workflows**, select the **Abandoned view** workflow, and go to the **Start/Stop configuration**.

<Image align="center" width="80% " src="https://files.readme.io/44ac98c5be27b2d317fe9c3c5cfe4f2d38ed819af9d60de1caa2a69f21276f7b-testing-the-products-block-201.webp" />

2. Copy the segment’s name or its **ID** in the **Segment** parameter.

<Image align="center" width="80% " src="https://files.readme.io/61da29888becbe80899be0b73b3b32f05cd358d68927ab559d248c46e429509b-testing-the-products-block-02.webp" />

## Block Testing

1. Open the email in the editor and click **View message**.

<Image align="center" width="80% " src="https://files.readme.io/0634f2e9caeb960cbd2d8de739ec71371edf5687d817edea5eab60501a9c1907-testing-the-products-block-03.webp" />

2. Click **Select contact**.

<Image align="center" width="80% " src="https://files.readme.io/e241c24a592cf6e571ac76f7efa199ba0c2e9f430f499f1889c2e79c44579d42-testing-the-products-block-04.webp" />

3. Select **Preview contacts from selected segment** and paste the name or ID of the segment into the search field.

<Image align="center" width="80% " src="https://files.readme.io/b0500297acfe24c154d91833ecce7da61d105e0a006f5885a2a9a79a81603246-testing-the-products-block-05.webp" />

4. Select a contact for testing.

<Image align="center" width="80% " src="https://files.readme.io/10da8f8350134cd6ce2a84484ac494e8ba31de55d9ea84788fdc440ce1b24651-testing-the-products-block-06.webp" />

The message content will be generated differently depending on the following cases:

* **There is data available to display for a contact**

In this case, you will see the block content as the selected contact will see it.

<Image align="center" width="80% " src="https://files.readme.io/454313dfc6e77591a38018e2cb03ed74ea9e54688e8a2ceea6a73ad04c95e286-testing-the-products-block-07.webp" />

* **There is no data available to display for a contact**

In this case, there are two possible options:

1. The preview will display a notification about the absence of recommendations, and the system will not send the email.

<Image align="center" width="80% " src="https://files.readme.io/05c50cd82dc8952f141faeccf0af1fd5b59b04457d1e4ef2410326d9f6bfaab4-testing-the-products-block-08.webp" />

2. The product block will be hidden, but the system will send the email.

<Image align="center" width="80% " src="https://files.readme.io/510fb80e400ffe23282cf0209199ea5c42462e6eda38ec34d89d9c65e17533b7-testing-the-products-block-09.webp" />

> 📘 Note
>
> The display of the first or second option depends on the [If there are no products to show](https://docs.yespo.io/docs/using-the-products-block#if-there-are-no-products-to-show) setting in the **Products** block.

If you deactivate the **Message for** switcher, the recommendations will always display bestsellers from the general recommendation algorithms.

<Image align="center" width="80% " src="https://files.readme.io/0c038e80aca7474198dfd336e32ffd3f367597e941ab0baa2692174282b557de-testing-the-products-block-10.webp" />

Click the **Back** button to return to the editor window.

<Image align="center" width="80% " src="https://files.readme.io/7304e988e7953c51ab9b52390f66eef98a334abb63d77f83cda6eb9629917b91-testing-the-products-block-11.webp" />