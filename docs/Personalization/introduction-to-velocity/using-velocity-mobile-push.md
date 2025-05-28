---
title: Using Velocity in Mobile Push
excerpt: >-
  See how to create mobile push with dynamic variables. Similarly you can use
  variables in SMS and web push notifications.
deprecated: false
hidden: false
metadata:
  title: Using Velocity in Mobile Push | Yespo Guide
  description: >-
    The document explains creating mobile push notifications with dynamic order
    details using Velocity, showing how to extract data from arrays like
    orderData and recommendationsData, with tips on character limits.
  robots: index
next:
  description: ''
---
As an example, we’ll use an order confirmation mobile push message and add dynamic order details to it.

## Creating mobile push

1. Go to _Messages → Messages_ and open the necessary mobile push or create a new one.
2. Use Velocity to add dynamic variables to content where personal contact data should be substituted. The number of variables and their names will depend on your copy.

To get access to the array data, the structure of the foreach cycle built in velocity has to be used in the message. Having `orderData` array as an example, the velocity code looks as follows:

```json
// Inside the structure, the data are extracted in a sequence from every element of the array
#foreach($order in $!data.get('orderData'))
  // To extract the value from the name field of the order 
  $!order.get('name') 
  // For the price field
  $!order.get('price')
#end
```

Similarly, for an array transmitting `recommendationsData`:

```json
// Inside the structure, the data are extracted in a sequence from every element of the array
#foreach($recomm in $!data.get('recommendationsData'))
  $!recomm.get('name')
  $!recomm.get('price')
#end
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f367e0b3a8d3d1322703ea3d21f44d79c9eccef9fe77783e1c9af7f674a7a108-6d96f73-0e9a0c7-Velocity_in_Mobile_Push_1.webp",
        null,
        "Use Velocity to add dynamic variables"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The following content is the result of substitution, the design of the notification may differ depending on the OS version:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e590f1b7ac64e43c83a7709af97b128a6bfb6b18d32983c213d31fdc071be6b9-917d1e8-20d8025-Velocity_in_Mobile_Push_2.webp",
        null,
        "Order notification"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The mobile push notification will be displayed differently on different devices, but we recommend writing no more than 40 characters. That’s why it is not always rational to display the entire contents of the array using the foreach loop. Instead you can refer to a specific array element. Then velocity construction for `orderData` array will look like: `$!data.get('orderData').get(0).get(' name')`, where the first element of the array is accessed (numbered from 0).