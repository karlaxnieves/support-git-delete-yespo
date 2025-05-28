---
title: Promo Code from Data Base
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Promo Code from Data Base | Yespo Guide
  description: >-
    The document explains how to upload and manage a promo code database: create
    files with set parameters, track active/sent codes, and use variables to add
    codes to messages.
  robots: index
next:
  description: ''
---
Upload the promo code database, specify the variable in the message, and the system will automatically insert them.

> 📘
>
> This type is suitable for both single and bulk campaigns.

## Create and import a file with promo codes

To see the file example, go to your profile → *Settings → Promo codes → File example*.

<Image align="center" width="80% " src="https://files.readme.io/b7d925b800c762f0c9d6cb36fb63e942bd3c0b62e0fae3d4e0ad0f0fc59b2b70-4645e87-promocodes8.webp" />

Promo Code from Data Base

It should include the following parameters:

* **code** - promo code;
* **expirationDate** - promo code expiration date in one of the formats: yyyy-MM-dd, yyyy-MM-dd'T'HH:mm:ss, yyyy-MM-dd'T'HH:mm, yyyy.MM.dd;
* **discount** - discount;
* **type** - promo code type (letters and numbers).

> 📘 Important
>
> If you need to use only promo codes without other parameters, upload a file only with a code column.

If you upload only promo codes, tick the corresponding checkbox.

<Image align="center" width="80% " src="https://files.readme.io/86d129ee1dbcd255f9132d948951c8f94e133552bed1b9249c8592064635df95-1af9cf1-promocodes4.webp" />

A file entitled General will be uploaded into the system. All promo codes uploaded in this way will be displayed in this file.

<Image align="center" width="80% " src="https://files.readme.io/0643fefe97dd3f8913a3298c3035e899dd02a2c1ece030c5daf5434faba9ffb6-110aac2-promocodes16.webp" />

After downloading the file with *Type, Discount* and *Expired* parameters, you will see *Active, Sent* and *Upload history* tabs.

* On the *Active* tab, you can track the number of current and expired promo codes at the selected date:

<Image align="center" width="80% " src="https://files.readme.io/7b6bbe42a0e2ac3dc66300143f3819fcc50570e1149ac2979ae2912b664d2fda-1_6.webp" />

* On the *Sent* tab, you can select a specific period and see the number of sent promotional codes of various types.

> 📘 Note
>
> Data on sent promotional codes are collected from 18:20 2023-02-17.

<Image align="center" width="80% " src="https://files.readme.io/6397930d8e79c65013ba4b5c642ee4bda3fe7f6bac5167896abcc51e14a5a1f8-1_3.webp" />

* To delete the promo codes list, go to the Upload history tab, click "..." → *Delete*:

<Image align="center" width="80% " src="https://files.readme.io/a59452f9d3a6abf7953eae2281766bbf31dd673ffadfc3ea497dcc299ea1f433-1_4.webp" />

## Create an email

### For promo codes only

Insert the variable `%PC_GENERAL%` where you want your promo code in the email. At the moment of the campaign launch, the system will automatically replace it with the first valid promo code in the list.

<Image align="center" width="55% " src="https://files.readme.io/1f94e2c59404c744b93e06cbb9db4ba6702f6106f38930142cd89de6cbf489d2-1beaa3d-promocodes12.webp" />

### For promo codes with additional parameters

Insert the variable `%_PC_TYPE_EXPARATIONDATE_DISCOUNT%`, where you want your promo code in the email. It may look as follows: `%PC_NewYear_1_7%` where: ***NewYear*** is a promo code type, ***1*** is the minimum number of days the promo code is valid, and ***7*** is the discount.

> 📘 Note
>
> We recommend setting a minimum validity period for the promo code to 1 day so that the sending of promo codes continues until there are active promo codes in the file.

<Image align="center" width="40% " src="https://files.readme.io/08d3f9d022bab613130bc0bde0cd5c33079e7ce91e042fc822d547906bf4cb34-61716a1-promocodes15.webp" />
