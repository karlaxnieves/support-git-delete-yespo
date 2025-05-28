---
title: Substituting Email Blocks According to Contact Profile Data
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Substituting Email Blocks According to Contact Profile Data | Yespo Guide
  description: >-
    The document explains using Velocity to create dynamic email content based
    on profile data, like gender, with conditional structures for women's,
    men's, and common product segments.
  robots: index
next:
  description: ''
---
[The Velocity code](https://docs.yespo.io/docs/introduction-to-velocity) allows you to create an email with content depending on the data in the contact's profile, e.g., gender. Men will see a selection of products for men, women — for women, and those contacts whose gender is not specified — a common product selection.

## Setting Up Dynamic Blocks

1. Place three structures with content for different segments in the template: women's clothing, men's clothing, and a common product selection.

<Image align="center" src="https://files.readme.io/aa66bb7b4ecc271790e41235c4ebf21d6e703159e26dde86ff94f330e189f751-velocity_1.webp" />

2. Select the structure with women's products and open its code editor.

<Image align="center" width="80% " src="https://files.readme.io/3646ca59ab21d097012ab9b614b275eeba6bd78441ebaadc0b14826ccfa21b72-velocity_2.webp" />

3. Declare a variable from the contact profile above the first `tr` tag. In our case, this is an additional contact field `%PERSONAL.GENDER%`.

<Image align="center" width="80% " src="https://files.readme.io/362d271df3a577a568331d18038d4accaad7e301a029efab22214d527936c9c0-image1.webp" />

> 🚧 Important
>
> The variable's name in the template must match the name of the additional contact field, which you can see in the account settings on the *Additional fields* tab. Read more about contact fields [in the manual](https://docs.yespo.io/docs/how-import-and-match-contact-fields-in-the-system).

4. Add a conditional statement to the code. Use the following format:

```json
<!--#if($data.get('parameter name')=='value1')-->
```

In our case, the operator will be like this:

```json
 <!--#if($data.get('PERSONAL.GENDER')=='F')-->
```

<Image align="center" width="80% " src="https://files.readme.io/6f0ef1fa97fc6a8dc88c92b75284cf539f62c2d5dec39c823e33669169c83999-velocity_4.webp" />

5. Select the structure with men's products. You will see the structure’s code in the editor.

<Image align="center" width="80% " src="https://files.readme.io/3fc701c62771f4c7717d70221f06deb5fe03ae5052811cdd97ae96be7b78782b-velocity_5.webp" />

6. Add a conditional statement to the code above the `tr` tag. Use the following format:

```json
<!--##elseif($data.get('parameter name')=='value2')-->
```

In our case, the operator will be like this:

```json
 <!--#elseif($data.get('PERSONAL.GENDER')=='M')-->
```

<Image align="center" width="80% " src="https://files.readme.io/7e2ba82c31d5a40633b2526a00cf11899f432b5c072e67d9ad54936b34e70600-velocity_6.webp" />

7. Select the structure with the common products.

<Image align="center" width="80% " src="https://files.readme.io/00726417bb4b514b053e82d7a36885e5d5d1247502925454efd0a4031685ec26-velocity_7.webp" />

8. Add a conditional statement to the code above the `tr` tag. Use the following format:

```json
<!--#else-->
```

<Image align="center" width="80% " src="https://files.readme.io/1742ec6ecf0b105e20df16803edd00f6f8e7cb55709a75868223135a714209ad-velocity_8.webp" />

9. Add an `end` statement after the `tr` tag that closes the structure.

```json
<!--#end-->
```

<Image align="center" width="80% " src="https://files.readme.io/325b885f9b5f74e5403ac7793def885ee3075015d27b304fd2124b204ac86b6e-velocity_9.webp" />

You can make a more complex check in case the fields have different cases: "M" or "m", "F" and "f":

```json
#if($data.get('PERSONAL.GENDER')=='m') and $data.get('PERSONAL.GENDER')=='M')
```

You can also use such option:

```json
#if($data.get('PERSONAL.GENDER').equalsIgnoreCase('m'))
```

Similar articles: 

* [Welcome Series Segmented by Category](https://docs.yespo.io/docs/welcome-series-segmented-by-category)
* [Splitting the Workflow Depending on the Event Parameters](https://docs.yespo.io/docs/splitting-workflow-depending-event-parameters)
