---
title: Popular Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Popular blocks | Yespo Guide
  description: >-
    Explore the Popular Blocks in marketing automation workflows, including End,
    Timer, Task, Condition, and Check Point. Learn how these commonly used
    blocks streamline workflow creation and enhance campaign efficiency.
  robots: index
next:
  description: ''
---
Popular — common blocks. There are five blocks in the group:

- End
- Timer
- Task
- Condition
- Check point

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/025d023fc2cedcf5a1e95ec24b175b85a796381d52c8d865a6ebac646b2466b5-popular-blocks-01.webp",
        "Popular blocks",
        "Popular blocks"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## End

We recommend using the _End_ block at the end of the workflow and all its paths. Adding this block will help visually understand the logic of the workflow and actions before the end. This is especially useful when the workflow has a path structure and a significant number of other blocks.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5f8ccea74bbd86f7e07cf705680234cdabe01379e2ea5af62ee4bf2c43c93d3-popular-blocks-02.webp",
        "End block",
        "End block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Timer

[More detailed information >](https://docs.yespo.io/docs/time-blocks#timer)

## Task

The block is used to set for the workflow one of the following tasks:

- Create contact
- Update contact
- Get contact
- Confirm contact
- Send obligatory (transactional) email
- Send transactional Viber message
- Send transactional SMS message
- Get order
- Create promo code
- Get promo code
- Launch Event

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/efcea00f9b4b4e46f72eec2deafaa166b43bc20327d50c2c0afc8147740b03e1-popular-blocks-03.webp",
        "Task blok",
        "Task blok"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can select the necessary task from the drop-down menu on the right.

### Create Contact

The task is to create a contact in the system. If the contact with this email address already exists in the system, it will be updated. If not, a new contact will be created.

> 📘 Important
> 
> Use this task only when the contact data is passed via the API method [Generate event](https://docs.yespo.io/reference/registerevent_1), and only a part of the data needs to be specified when a contact is created. For example, you sent the event via _Generate event_ for a new contact.

With this block, you add this contact to the system. For all other methods, this block is not needed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/564794dd86c65712496d0497ec06ce1627abcefd01096c84c74658fd64f62461-popular-blocks-04.webp",
        "Update contact",
        "Update contact"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has 3 parameters:

- **Email**: required field if you create a contact by email.
- **Phone**: required field if you create a contact by phone number.
- **JSON**: field contains a line or a variable with a line in JSON format with contact data (phone number, name, surname, city, additional fields). Email address is specified by default; if needed, specify other additional data.

You can pass the _contactJson_ variable in the _JSON_ field. In this case, REST API will validate the values passed together with this parameter. In case of passing the contact’s parameters with mistakes, the warning returns the invalid and valid values.

Request body for the _JSON_ field:

```json
{"firstname":"...","lastname":"...","sms":"...","town":"...","timeZone":"Etc/GMT+03","languageCode":"uk","profileInputs": [{"profileInputId":10001,"value":"..."}],"confirmed":false}
```

where

- _profileInputs_ - additional field array;
- _profileInputId_ - additional field ID;
- _value_ - additional field value;
- _confirmed_ - contact email address status (confirmed/unconfirmed)

> 📘 Important
> 
> To create an unconfirmed contact, add _"confirmed":false_ to the request body:

```json
{"firstname":"...","lastname":"...","sms":"...","town":"...","profileInputs": [{"profileInputId":10001,"value":"..."}],"confirmed":false}
```

To create a contact with a value in the date field, use the format YYYY-MM-DD:

```json
{"profileInputs": [{"profileInputId":10001,"value":"2023/11/06"}]}
```

To create a contact with a value in the date with time field, use the format YYYY-MM-DDThh:mm":

```json
{"profileInputs": [{"profileInputId":10001,"value":"2023/11/06 16:42"}]}
```

### Update Contact

The task is to update the contact information. If the contact exists in the system, their info will be updated; if the contact doesn’t exist, the system will skip them.

Use this task to update the contact data from an event sent via the API method [Generate event](https://docs.yespo.io/reference/registerevent_1), or to set a fixed value of the additional field in the workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/82b4785617191e187ad74bbebc24fb6037a5b33ac4450532470be3990f7f7586-popular-blocks-05.webp",
        "Get contact",
        "Get contact"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has 4 parameters:

- **Contact ID**: contact ID in the system. If you want to update a contact not by email but by ID in the system, specify the name of the variable that contains the contact ID. For example, _${contactId}_ or _123345_.
- **Email**: required field. For example, _${emailAddress}_ or _`test@test.com`_. If your event has a different variable, specify it in the field. In the system events, the variable is called EmailAddress. System events are the events generated within the system (click on an email CTA, regular workflow launch, filled subscription form, reactivation with RFM analysis). For them, enter _${emailAddress}_ in the field.
- **Phone**: required field if you update a contact by phone number. For example, _${phoneNumber}_. If you have a different name for the variable in the event, specify it in the field.
- **JSON**: field contains a line or a variable with a line in JSON format with contact data (phone number, name, surname, city, additional fields). Email address is specified by default; if needed, specify other additional data. The parameter confirmed is ignored.

### Get Contact

The task is to get contact data and pass it to the message or to the _[Condition](https://docs.yespo.io/docs/blocks-description-conditions-group)_ block. For example, you want to send a notification email with contact data every time a new subscriber is added to the database, or send the subscriber registration details after registration.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1260070f689ee6d7842c755a97d8605130406ecbc7383ad1964812ad636d9684-popular-blocks-06.webp",
        "Get contact",
        "Get contact"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task works as follows:

1. The event that contains contact data is created (registered) in the system.
2. The task extracts out all available contact data stored in the database.
3. Block passes this data to the email.

The task has 4 parameters:

- **Contact ID**: contact ID in the system;
- **Email**: email address of the contact;
- **Phone**: phone number of the contact;
- **Token**: mobile token of the contact.

_Email_, _Contact ID_, _Phone_, and _Token_ are used to identify a contact. One of these fields must be filled with relevant data.

For example, if you want to identify a contact not by email but by ID in the system, specify the name of the variable that contains the contact ID. By default, it's _${contactId}_.  
You can use these variables in the message:

- _$!data.get('firstName')_ - name;
- _$!data.get('lastName')_ - surname;
- _$!data.get('email')_ - email address;
- _$!data.get('sms')_ - phone number;
- _$!data.get('contactKey')_ - contact key;
- _$!data.get('id')_ - contact ID in the system;
- _$!data.get('createdDate')_ - creation date;
- _$!data.get('updatedDate')_ - date of the last contact update;
- _$!data.get ('confirmed')_ - contact’s email address status (true - confirmed, false - not confirmed);
- _$!data.get('fields').get('12345')_ - additional fields. Insert an ID of the additional field instead of 12345.

For _Get contact_ task, you can activate the _Search only contact ID_ checkbox to search contact only by _contact ID_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b48afee37dce99452a102052489b470590e9e7828064af88c4b4d43afb64d835-popular-blocks-07.webp",
        "Search only contact ID",
        "Search only contact ID"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Confirm Contact

The task is to confirm the email address of the subscriber, add them to the system and make available for receiving.

For example, a person fills in a [subscription form](https://docs.yespo.io/docs/subscription-form-configuration), their email address gets to the system and they receive a confirmation email. They can not receive promotional campaigns until they confirm subscription. A successful confirmation link triggers the _Confirm contact_ task and starts the corresponding workflow.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7092a3d8e84f06aef60bdfdc89fb7b457f96968d1bc907bf7c57a861dd0d00a8-popular-blocks-308.webp",
        "Confirm contact",
        "Confirm contact"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has _Advanced parameters_.

[More about advanced workflow block parameters >](https://docs.yespo.io/docs/advanced-workflow-block-parameters)

> 📘 Important
> 
> When searching contacts for _Create contact_, _Update contact_, _Get contact_ tasks, the following rules apply:
> 
> - _Contact ID_ has the highest priority among all parameters
> - If _externaiCustomerId_ is specified, contact search will be performed by _externaiCustomerId_.
> - If _externaiCustomerId_ is not specified, contact search will be performed by email address or phone number.

### Send Obligatory (transactional) Email

The task is to send an email to the contact regardless of their status in the system (confirmed, unconfirmed, unsubscribed, spam report) except for blacklisted contacts.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/20402c9b3b97e51c29a5c1c1308218d765ec9d77e06f6eab0496e1f702d815b9-popular-blocks-309.webp",
        "Send Obligatory (transactional) Email",
        "Send Obligatory (transactional) Email"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Important
> 
> Use this task only if absolutely necessary. It ignores the contact status which may result in spam reports and harm sender reputation.
> 
> Use the task only to send a transactional email (subscription confirmation, order confirmation, change in a pricing plan) to a new unconfirmed contact.
> 
> In all other cases, use the _Email_ task from the _Message_ or the _Message to segment_ blocks.

The task has one basic  parameter — _Message_. In this field, select a pre-created message that will be sent to the user. The task also has advanced parameters.

[More about advanced workflow block parameters >](https://docs.yespo.io/docs/advanced-workflow-block-parameters)

### Send Transactional Viber Message

The task is to send a Viber message to the contact regardless of their status in the system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8901f89ac1918a77179e10efbe4c7364631c42736a37975aa3fa52367c877afd-popular-blocks-310.webp",
        "Send Transactional Viber Message",
        "Send Transactional Viber Message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has two basic parameters:

- Message
- TTL —  Set the period after which the message will not be displayed if it has not been delivered to the contact by that time. By default, 1 day is set. The minimum value is 2 minutes, and the maximum is 28 days.

The task also has advanced parameters.

[More about advanced workflow block parameters >](https://docs.yespo.io/docs/advanced-workflow-block-parameters)

### Send Transactional SMS Message

The task is to send an SMS message to the contact regardless of their status in the system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f0d57351faa8af3232f433c09e6610cc5e9b342ae19a74028136742a068feeaf-popular-blocks-311.webp",
        "Send Transactional SMS Message",
        "Send Transactional SMS Message"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has one basic parameter — _Message_, and contains advanced parameters.

[More about advanced workflow block parameters >](https://docs.yespo.io/docs/advanced-workflow-block-parameters)

### Get Order

The _Task_ block extracts the data from an order and passes it to the message. For example, order status – order confirmation, order delivery.

Use this task only if you send the order data to our platform using the [Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1) API method.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9cc29470bbdf6de88e5fa46d568ca3bb801e95a9576f3b7005bf2e2f3b4c41b-popular-blocks-12.webp",
        "Get Order",
        "Get Order"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To configure the _Get order_ task block:

Click the _Get order by_ dropdown list and select one of the following options:

- **Order ID**. Choose this option when you wish to get the order data by the ID generated by our system.
- **External Order ID**. Choose this option when you wish to get the order data using the order ID that you pass to our system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8134478e046f89bf35dbf3ff9bcd4e7e97ad51c4447b785805f5e4dc31d4a7aa-popular-blocks-13.webp",
        "Get order by options",
        "Get order by options"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You don’t have to fill in the _Order ID/External order ID_ field. The task extracts automatically all the parameters from the order event.

The task works as follows:

1. The system receives the order information.
2. The task extracts all the data from the order and passes it to the email as [variables](https://docs.yespo.io/docs/introduction-to-velocity).

Read more about the _Task_ block in the [Order automation](https://docs.yespo.io/docs/orders-1) article.

### Create Promo Code

The task is to generate a promo code and pass it to a message that goes next in the chain. The algorithm encrypts the parameters by your key, and the reverse algorithm decrypts it when a promo code is entered on the website. [Learn more](https://docs.yespo.io/docs/promocodes).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/86496355be171f21b85b4d522c5954a9e575875e59073923b3e355c42f6e9371-popular-blocks-14.webp",
        "Create Promo Code",
        "Create Promo Code"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has 4 parameters:

- **Days**: number of days until the promo code is expired. The system will add them to the current date, and the resulting expiration date will be encrypted into the promo code. The variable _${days}_ is specified by default.
- **Type**: promo code type. You can set up 32 promo code types. For example, assign type 0 to a subscription promo code, type 1 to a birthday code, type 3 to reactivation code, etc. Pass in the variable the number from 0 to 31 that corresponds to the right type. The variable _${type}_ is specified by default.
- **Discount**: size of the discount. Used to generate a promo code when a discount is given as a % off the order cost. It is always a double-digit number, so discounts of up to 10% should go with zero ahead. For example, specify 05 for an email with a 5% discount. The variable _${discount}_ is specified by default.
- **Key**: encryption key. You can leave the default value. The variable _${key}_ is specified by default.

> 📘 Note
> 
> All parameter fields are required.

In a workflow, this block is followed by one of the _Message_ blocks (Email, SMS, Viber, etc.).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6412678b8a9851363538cdde8c2e6745384fc212021ab6d750e2fbf726e127b4-popular-blocks-35.webp",
        "Workflow to create a promo code",
        "Workflow to create a promo code"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


For example, in the email template, you can put a variable _$!data.get ('promocode')_ in the place intended for a promo code.

![Promo code variable](https://cdn.yespo.io/photos/shares/Support/Images/Popular-blocks/popular-blocks-15.webp "Promo code variable")

### Get Promo Code

The task is to pass a promo code from the base to the email. More about uploaded [promo codes](https://docs.yespo.io/docs/promocodes).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/57cd3f3d65361f2fc7073370179e8bfe94c0cab245027e1c8e931077c69e541b-popular-blocks-36.webp",
        "Get promo code",
        "Get promo code"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has three required parameters:

- **Days**: number of days after the current date during which the promo code is valid;
- **Type**: promo code type;
- **Discount**: discount size from 01 to 99.

The system selects promo codes from the downloaded database based on the specified parameters.

Let's look at an example. Enter the following values in the parameters: _days - 10_, _type - newyear_, _discount - 25_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18575044f6099bc13d7bb31edf3d32807eee117e872c2e958358040abf2aafaa-popular-blocks-37.webp",
        "Get Promo Code example",
        "Get Promo Code example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The workflow will extract from the database a promo code with a 25% discount, identified by the type _newyear_ and having a validity period of at least 10 days. If several promo codes meet the specified parameters, the system will automatically choose one of them.

After the _Get Promo Code_ block, you place the block for sending messages (Email, SMS, Viber, etc.).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/31d5ebe38999ce15816756c5d102db3b2851ab1d6c530013060657ccf1f1b841-popular-blocks-38.webp",
        "Workflow to get a promo code",
        "Workflow to get a promo code"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the email template, put a variable _$!data.get ('promocode')_ in the place intended for a promo code.

### Launch Event

The task is to launch any event from the workflow. For example, one workflow can trigger the launch of another. To use the task, you need to previously create the [event](https://docs.yespo.io/docs/creating-events) you plan to launch.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/793c4b5bd2aa5bff050dca68f84e35f162a5961a565f1311b11988250ff32448-popular-blocks-16.webp",
        "Launch event",
        "Launch event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has 3 parameters:

- **Event**: required field. Select the type of the event to launch.
- **Unique key**: key of the event you’re launching, for example, a variable with an email address. If the field is not filled, the key from the event that triggered the current workflow will be used.
- **Parameter**: array of parameters we want to pass to a launched event. If the field is not filled, the parameters from the event that triggered the current workflow will be passed.

The format of the parameters:

```json
[{"name":"paramName,"value":"parameter value"}]
```

## Condition

The block is used to check whether certain workflow conditions are met or not. Depending on this, the workflow is further split into two paths - _Yes_ or _No_ - with separate downstream tasks.

The block has one _Start_ block and two _End_ blocks (for _Yes/No_ paths).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58ffce7c4fe3e790b2d5c8c25632225fa1b850833e3df9f98961414f9e836508-condition.webp",
        "Condition block",
        "Condition block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The _Condition_ block has 8 tasks:

- Check event
- Variable matches regular expression
- Contact confirmed
- Contact exists
- Check parameter by date/time value
- Verify contact field matches event parameter
- Check the checkbox list fields
- Check values.

_Check event_ is a default task. When needed, choose the necessary task from the drop-down menu.

### Check Event

The task is to check whether a particular event occurred since the workflow was launched. Events are searched by keys.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0f15c56dc4f0a6180d17a4100aeb3af3de26fe5deb2e53c666fe532e13a95973-popular-blocks-18.webp",
        "Check event",
        "Check event"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has 3 parameters:

- **Unique key**: event key. For example, it can be an email address; thus, this field should contain a parameter with an email address. This is a parameter from the event that launched the current workflow. If it's _emailAddress_, enter _${emailAddress}_ in the field.
- **Event**: event type. This is a required field without which the workflow will not start.
- **Period**: you can set the time before the start of the workflow, during which the event must be checked. By default, the block checks for events since the activation of the workflow.

### Variable Matches Regular Expression

The task is to check a certain variable from the event or the data received from other blocks.

For example, you can check if your recipient is a male or a female and send them different messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7876b4851fd5ca0b2274c7c6df78c6ac9426e69cc1dafa289bcdeaaa0fa3bbd4-popular-blocks-19.webp",
        "Variable matches regular expression",
        "Variable matches regular expression"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has 2 parameters:

- **Name**: variable name. It could be an event parameter. The parameter name is entered in this field without ${}. If you check the data obtained by other workflow blocks (for example, _Get contact_), specify the system variable _smartMessageJson_ in the field.
- **Pattern**: regular value checked for compliance. For example, to check whether the event parameter address contains the word “London”, specify _London_ in the _Pattern_ parameter.

### Contact Confirmed

The task is to check whether the contact's email has been confirmed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e85b119750180b666ccc2d007664696b2853a6b0a0ac28592664199b149cbe4-popular-blocks-20.webp",
        "Contact confirmed",
        "Contact confirmed"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


For example, a person has subscribed to your newsletter, and you want to send a welcome email.

The task works as follows:

1. The contact is added to the Yespo database but has an unconfirmed status.
2. A confirmation email is sent to the contact.
3. The task checks whether the subscription is confirmed.
4. If it is confirmed, the _Yes_ path is triggered, and a welcome email is sent.
5. If it isn’t confirmed, the _No_ path is triggered.

The task has 2 parameters:

- **Email**: contact’s email address;
- **Contact ID**: contact’s ID in the system.

By default, the system checks whether the contact is confirmed by email. Specify the name of the variable or the email address in the _Email_ field. For example, _${emailAddress}_ or _`test@test.com`_.

If you want to use a contact ID for confirmation, specify _${ContactId}_ in the _Contact ID_ field.

One of the parameters must be specified.

### Contact Exists

The task is to check whether the contact exists. It works similarly to _Contact confirmed_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09c896b2e965be0bb0e80ab0174c712d0b20bff41257d81644acd531a916aa32-popular-blocks-21.webp",
        "Contact exists",
        "Contact exists"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task has 3 parameters:

- **Email**;
- **Phone**;
- **Contact ID**.

By default, the system uses an email address. If you want to use a contact ID, specify _${contactId}_ in the _Contact ID_ field. To identify a contact by phone number, specify _${phoneNumber}_ in the _Phone_ field.

### Check Parameter by Date/Time

The purpose of the task is to check the date from the event parameter.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d7b9dd939817c593c7294e06b616dbb59267f45f39c590783689a9ac17a21b0-popular-blocks-22.webp",
        "Check parameter by date/time",
        "Check parameter by date/time"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When creating a workflow, the user's time zone is taken into account. Time will be saved in UTC.

For example, The date and time being checked is 2020-07-30 13.00. The user's time zone is GMT +3 (Europe/Kyiv). The following value will be passed to the event: "2020-07-30T13:00 + 03:00".

The task contains 2 parameters:

- **Parameter**. It is required to state the parameter's value passed in the parameter. By default, this is a variable _${parameter}_. The date is in ISO 8601 format.
- **Date**. Select an option from the list for a single date, time or the date/time range.

#### Parameter

The _Parameter_ field accepts the parameter name in the system.

Enter the parameter name as a variable or a string. The format example: _${userId}_ or _123abc_.

#### Selecting the Date and/or Time Settings

To select the date and/or time settings:

1. Click the down arrow and select one of the options from the list:
   - Date
   - Date with time
   - Date range
   - Time range
   - Date/time range
   - Date before
   - Date after
   - Date and time is greater that current by

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/875a6430aaede84cac8bf3d5a2c513defcd51035c45b9fa9b15a27eda9da1e3c-popular-blocks-23.webp",
        "Date and/or time settings",
        "Date and/or time settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Configure the required date and time settings for the selected parameter as explained below.

##### Configuring the Date settings

When you select the Date parameter, the Condition block checks if the event date matches the selected date for this parameter.

To select the _Date_ settings:

- Click the calendar icon and select the required date.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f51a0a33007e99a79b49fb0d0be74565cc443060876a720fa77ecf891569f056-popular-blocks-24.webp",
        "Calendar icon",
        "Calendar icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Top Tip
> 
> Click the left or right-pointing arrows to change the month, or click the section of the calendar to switch to the month or year selection.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/27a17ff69c9f77b9b7562858d23284398468036802184760c4e1297ba5fc7638-popular-blocks-25.webp",
        "Month or year selection",
        "Month or year selection"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Configuring the Date with time settings

When you select the Date with the time parameter, the _Condition_ block checks if the event date matches the selected date and time for this parameter.

To select the _Date with time_ settings:

1. Click the calendar icon and select the required date in the date selection window.
2. In the hour selection window, select the required hour.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e073ff59f8aadf766baa66f87129e0e9e30f36eb91c155dd26523f4c1aa97168-popular-blocks-26.webp",
        "Date with time settings",
        "Date with time settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Configuring the Date range settings

When you select the _Date range parameter_, the _Condition_ block checks if the event date matches the selected date range for this parameter.

To select the _Date range settings_:

1. Click the date beside the left field and select the initial date of the range.
2. Click the date beside the right field and select the final date of the range.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3476b9aa9a6800e616a68ad090ec0067a09d10f263b948daf82fdb481d463a90-popular-blocks-27.webp",
        "Date range settings",
        "Date range settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Configuring the Time range settings

When you select the _Time range_ parameter, the _Condition_ block checks if the event time range matches the selected time range for this parameter.

To select the _Time range_ settings:

1. Click the time beside the left field and select the initial time from the time selection window.
2. Click the time beside the right time field and select the end time from the time selection window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dd38112f18e041e9f3f1e8a24b03e0017bf164d69f5b2acddb18e41ae1f7628b-popular-blocks-28.webp",
        "Time range settings",
        "Time range settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Configuring the Date/time range settings

When you select the _Date/time range_ parameter, the _Condition_ block checks if the event date and time range match the selected date and time range for this parameter.

To select the _Date/time range_ settings:

1. Click the left date and select the required initial date in the date selection window.
2. In the hour selection window, select the required hour.
3. In the minute selection window, select the precise time. The time values in this window are within the range of 1 hour with an increment of 5 minutes.
4. Click the right date and select the final date, hour and minutes, the same as for the initial ones.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3b9ef4777772327ce6cc3d2afab851d81f39548aae82a30a156edaebdd3576f-popular-blocks-31.webp",
        "Date/time range settings",
        "Date/time range settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Configuring the Date before settings

When you select the _Date before_ parameter, the _Condition_ block checks if the event date received as a parameter is within the date range before the selected date.

To select the _Date before_ settings:

- Click the calendar icon beside the date field and select a date.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bfed51e422838f9479e4260ac0242e7c245a2e090c76e264b75dd3b3f77bdeae-popular-blocks-29.webp",
        "Date before settings",
        "Date before settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Configuring the Date after settings

When you select the _Date after_ the parameter, the _Condition_ block checks if the event date received as a parameter is within the date range after the selected date.

To select the _Date after_ settings:

- Click the _calendar_ icon beside the date field and select a date.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b702e889d6f8dec9e1c851d3af8143f2595ee5707bf846a4e12a569420c00102-popular-blocks-30.webp",
        "Date after settings",
        "Date after settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The selected date for the _Date before_ and _Date after_ parameters is not included in the period.

##### Configuring the Date and time is greater than current by settings

When you select the _Date and time is greater than current by_ option, the _Condition block_ checks if the event date and time received as a parameter are greater than the current date and time by N minutes/hours/days.

Example:

The date and time of your webinar is 2022-10-10, 16:00.

You have configured to send 3 messages to the registered persons: 30, 10 and 5 minutes before the webinar start.

The person’s registration date and time is 2022-10-10, 15:52 (the current date and time).

The _Condition_ block compares the current time and the time from the event parameter. As the result of the comparison:

1. Sending the first message is cancelled because the condition for sending the message (30 minutes before the event) is false.
2. Sending the second message is cancelled because the condition for sending the message (10 minutes before the event) is false.
3. The third message will be sent as scheduled because the condition for sending the message (5 minutes before the event) is true.

To configure the _Date and time is greater than current by_ option:

- Enter the required value in the field and select its format from the dropdown list: minutes, hours or days.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8358240b0375ff659d5f5bbda20a1d0949e6d980528aec15ef20b21d466b5b1a-popular-blocks-32.webp",
        "Date and time is greater than current by settings",
        "Date and time is greater than current by settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Verify Contact Field Matches Event Parameter

The task allows checking if the contact field matches the passed value in the event parameter.

For example, you want to check if the subscriber's city matches the city value passed in the event. If that is not true, you can place the contact update block downstream.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/37795ea510bb83fe99c7425aceb27066d6da89e5fd5bdd746eba3ca1fd73b5ff-popular-blocks-333.webp",
        "Verify contact field matches event parameter",
        "Verify contact field matches event parameter"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The task contains two basic parameters described in the table below.

[block:parameters]
{
  "data": {
    "h-0": "Parameter",
    "h-1": "Description",
    "0-0": "Contact field",
    "0-1": "The field from the contact information that has to be verified.  \nClick the down arrow to select a field from the dropdown list or enter the field’s name in the box.  \nYou can compare the following field types:  \n  \n- Text box\n- Text area\n- Number\n- Fractional number\n- Dropdown list",
    "1-0": "Parameter",
    "1-1": "The event parameter. The task checks if the contact’s field matches this parameter.  \nYou can enter the value as a variable in the format of  `${parameterName}` (the parameter’s name in an event, for example, `${city}`), and in this case the contact’s field is compared with the value of the parameter in the event.  \nUsing the `123abc` format is acceptable (for example, Kyiv), in this case the contact’s field is compared with the specific value in the parameter (`Contact's field 123abc?`). Select case sensitive if this operation is case-sensitive."
  },
  "cols": 2,
  "rows": 2,
  "align": [
    "left",
    "left"
  ]
}
[/block]


The task also has advanced parameters.

[More about advanced workflow block parameters >](https://docs.yespo.io/docs/advanced-workflow-block-parameters)

### Check the Checkbox List Fields

The purpose of the task is to check for empty or specific checkboxes in the contact card.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c47e64e187a8f802050d77acf393fac0f573c124737568fff8d052e1e714829-check-checkbox.webp",
        "Check the checkbox list fields",
        "Check the checkbox list fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The list of checkboxes displays checkboxes created in the _Additional fields_ section.

The following checking options are available:

- Check for empty checkbox fields options
- Check for specific checkbox field options
- Check for the presence of one of the specific checkbox field options

<br />

### Check Values

The condition allows you to check

- Values ​​in contact fields: for example, subscriber city.
- Values ​​in event context parameters: for example, promo code type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c7fa25e2d73259558dc21634ad8956e7c72a86d4cec1c8c3765863c21bafb414-check_values.webp",
        "",
        "Check values"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To check a value, click the _Select a rule_ button and specify an event parameter, or select a contact field from the list. Then specify the value you want to check the parameter or field for, and one of the checking options:

- equals,
- is set,
- is empty,
- contains,
- starts with,
- ends with,
- one of,
- matches.

> 📘 Note
> 
> The parameter name does not need to be surrounded by special characters **${}**.

If necessary, you can add a check for other fields (AND/OR conditions; their number is not limited). This allows you to avoid creating conditional segments to check in the workflow.

More about:

- [Events and behavior tracking](https://docs.yespo.io/docs/events-and-behaviour-tracking)
- [System contact fields](https://docs.yespo.io/docs/how-import-and-match-contact-fields-in-the-system)
- [Creating additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields)

## Check Point

If you have a complex workflow with paths, you can add this block at any point and then check in the workflow launch history if it followed a specific path. A _Check point_ can also bridge multiple paths. Not all blocks allow connection to several paths, but this block solves that task.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/99c104831d2afdd2d8a5710e46f75a1fd0952aa5bac664a986d4e84fe8536c4d-popular-blocks-34.webp",
        "Check values",
        "Check Point"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The block has one parameter: **Name**.