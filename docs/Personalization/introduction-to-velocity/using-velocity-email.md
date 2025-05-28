---
title: Using Velocity in Email
excerpt: See how to create email template with dynamic variables.
deprecated: false
hidden: false
metadata:
  title: Using Velocity in Email | Yespo Guide
  description: >-
    The document guides on creating personalized order confirmation emails with
    Velocity variables, integrating them into templates, previewing results, and
    transferring order details via API.
  robots: index
next:
  description: ''
---
As an example, we’ll use an order confirmation email and add dynamic order details to it. You can create any other email using the same principles ([see how to personalize email depending on data parameters from users’ profiles](https://docs.yespo.io/docs/user-profile-variables-and-velocity-features#use-case-personalizing-message-depending-on-location-data)).

To transfer orders’ information, you must send a request using the [Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1) or [Generate event](https://docs.yespo.io/reference/registerevent_1) API methods.

Request body example:

```json
{
"orders": [{
"externalOrderId": "100500",
"externalCustomerId": "12345",
"totalCost": 1000,
"status": "INITIALIZED",
"date": "2017-03-08T09:30:00+02:00",
"email": "mail@example.com",
"phone": "380942583691",
"firstName": "John",
"lastName": "Smith",
"currency": "USD",
"shipping": 10,
"discount": 0,
"deliveryMethod": "express",
"paymentMethod": "cash",
"deliveryAddress": "First str. 1",
"items": [{
"externalItemId": "200600",
"name": "Super Device",
"category": "devices",
"quantity": 1,
"cost": 990,
"url": "http://example.com/item/200600",
"imageUrl": "http://example.com/item/200600/image.png",
"description": "High quality"
}]
}]
}
```

This request has several order parameters and their values, such as `externalItemId`, `name`, `quantity`, `cost`, `url`, `imageUrl`, etc.

To place personalized order data to the transactional campaign, put parameters’ names to the message body and set the rules for interpreting them with the help of velocity variables.

## Creating a Message

1. Go to *Messages* → *Messages* and open the necessary email or create a new one.
2. Use Velocity to add dynamic variables to blocks where personal contact data should be substituted. The number of variables and their names will depend on your copy.

For example, to show the payment method in email, place the `$!data.get(‘paymentMethod’)` variable in the corresponding template block.

<Image align="center" width="80% " src="https://files.readme.io/a918110fc53dca8be219e192b38348739122bb4c1c53fe7563366c3a901cab09-using-velocity-in-email01.webp" />

3. To mark the beginning and end of a code block with dynamic content, click the structure with variables. Open the *Code editor* and add `#foreach($item in $!data.get('items'))` and `#end` at the beginning and end of the block, correspondingly.

<Image align="center" width="80% " src="https://files.readme.io/5afe10645d917b30cff3a95b07c83299ad2a647a6c4881faec0db1dbdf9c5cef-using-velocity-in-email02.webp" />

> 📘 Note
>
> You need to add these code snippets to each structure with dynamic variables.

4. To add dynamic variables for an image, click the necessary image → URL and insert:

* `$!item.get('imageUrl')` in `Image path`;
* `$!item.get('url')` in `Link (Other)`;
* `$!item.get('name')` in `Alternate text`.

<Image align="center" width="80% " src="https://files.readme.io/8cff8d19cc34c40c6af6bf4eed4968dbc2adf7954188dc3d2510ea7ebd305ba5-using-velocity-in-email03.webp" />

To preview the email with substituted data, click *Additional settings* → *Configuring dynamic content*.

<Image align="center" width="80% " src="https://files.readme.io/c53ccc2d2ffc77ac51dd8becee0d294b5ed052abadb022b6415209295f88c899-using-velocity-in-email04.webp" />

Enter order parameters in the JSON format.

<Image align="center" width="80% " src="https://files.readme.io/1ba01d90ef426e461cfe981bbabf05c1c37a9efa3e9d60eae8bde0c7f730c142-using-velocity-in-email05.webp" />

You can take order parameters from any corresponding order event. Go to *Automation* → *Orders*, click any event, and copy the parameters.

<Image align="center" width="80% " src="https://files.readme.io/7b9c04ad98a99896b0c6a864e529349c4f4ba1fb73595287cbd3c7ca5e63e608-using-velocity-in-email07.webp" />

Click the *View message* button. You will see the corresponding error description if there are errors in the code. Dynamic content won’t be displayed if there are errors in the code.

<Image align="center" width="80% " src="https://files.readme.io/42ecbf1dca2277da4abfd9bbc3adf660dd549830d77d1048a4e5e7ea3ce8d522-using-velocity-in-email06.webp" />

If the code is correct, you will see a message with dynamic content the same way the user whose data you used for the test will see it.

<Image align="center" width="80% " src="https://files.readme.io/5ffb07d76bb80181b79a34bc50762e06a961cfc41f3c36164813eacd27bd98d1-228ba86-4a7b7cc-Velocity_in_Email_7.webp" />

You can use the same Velocity code to substitute data in other messages.

After creating the message, [build a workflow](https://docs.yespo.io/docs/workflow-management#creating-a-new-workflow) with the *Get order* task.
