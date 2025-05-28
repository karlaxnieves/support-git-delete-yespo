---
title: Advanced Workflow Block Parameters
excerpt: Advanced Workflow Block Parameters
deprecated: false
hidden: false
metadata:
  title: Advanced Workflow Block Parameters | Yespo Guide
  description: >-
    Learn how to configure advanced block settings when using custom event
    parameters, message sending, and dynamic content insertion.
  robots: index
next:
  description: ''
---
Fill the advanced parameters in the following cases:

* When using custom event parameters
* For sending messages to an additional contact
* For inserting dynamic content

<Image align="center" width="80% " src="https://files.readme.io/7f30d22c197e1a6270d56858b4da771c7a426ae9ca37442ca06902c04e280c77-advanced-parameters-000.webp" />

List of *Additional parameters*:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Parameter
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Contact ID
      </td>

      <td>
        Contact identifier in the system or an event parameter containing it.  
      </td>
    </tr>

    <tr>
      <td>
        Email  
      </td>

      <td>
        Contact's email address or an event parameter containing the email address.
      </td>
    </tr>

    <tr>
      <td>
        Phone  
      </td>

      <td>
        Contact's phone number or an event parameter containing it.
      </td>
    </tr>

    <tr>
      <td>
        Token  
      </td>

      <td>
        Contact's token or an event parameter containing it.
      </td>
    </tr>

    <tr>
      <td>
        Language  
      </td>

      <td>
        Message language. Leave the field blank if you use a multilingual message in the workflow.  

        [Learn more about setting up multilingual campaigns >](https://docs.yespo.io/docs/creating-multilingual-campaigns)
      </td>
    </tr>

    <tr>
      <td>
        JSON
      </td>

      <td>
        Specific data from the event.
      </td>
    </tr>
  </tbody>
</Table>

Let's view each case of parameter configuration in detail.

### Using Custom Event Parameters

By default, when starting a workflow, the event should pass standard parameters for contact identification:

<br />

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Event parameters
      </th>

      <th>
        Identifiers
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ContactId
        Contact\_id
      </td>

      <td>
        Contact ID
      </td>
    </tr>

    <tr>
      <td>
        externalCustomerId
      </td>

      <td>
        External ID
      </td>
    </tr>

    <tr>
      <td>
        Email\
        EmailAddress\
        UserEmail\
        ContactEmail
      </td>

      <td>
        Email
      </td>
    </tr>

    <tr>
      <td>
        Phone\
        SMS\
        PhoneNumber
      </td>

      <td>
        Phone number
      </td>
    </tr>

    <tr>
      <td>
        PushToken\
        MobPushToken\
        TelegramBotToken
      </td>

      <td>
        Contact token
      </td>
    </tr>
  </tbody>
</Table>

> ❗️ Important
>
> 1. The primary identifier is *ContactId*. If it is not specified but at least one of the other identifiers is provided, *ContactId* will be automatically added to the event.
> 2. To start workflows, the system identifies the contact for which the event was received. The system searches for the contact using the following rules:
>
> * *​​​​​Contact ID* has the highest priority among all parameters.
> * Entered contact email, phone number, or token are used for sending.
> * If *externalCustomerId* is specified, the message is sent to the contact it belongs to; among those contacts that were found by email address, phone number or token.
> * If *externalCustomerId* is not specified, the message is sent to the contact found by email address, phone number or token.
> * If a contact is not found, a new contact will be created for sending.
>
> 3. For data consistency, provide parameter names according to the specified list.

If the parameters in the event don't match the standard values, such as using *PersonalEmail* instead of *EmailAddress*, like on the screen below

<Image align="center" width="80% " src="https://files.readme.io/4e711fe705b65be796f2c640672512529ccfebf3220e7567fcf1ae720ef3d8f3-advanced-parameters-001-2.webp" />

In this case, specify the name of the corresponding variable in the *Email* field.

<Image align="center" width="80% " src="https://files.readme.io/49b695e4758358b513be2b0bd531f29663a4606d17d2717ac8bc3d0edb0dcb0a-advanced-parameters-002.webp" />

### Sending Messages to an Additional Contact

For example, if you need to duplicate the message sent to the user and send it to the manager.

[Copy the block](https://docs.yespo.io/docs/workflow-management#copying-blocks--workflows) with the selected message in the workflow and specify the manager's contacts in the advanced parameters.

<Image align="center" width="80% " src="https://files.readme.io/fa4a6c2c3410076361d6fafec2e18bed0ebbd4c4adcba4b7cbc385ac3c4e1969-advanced-parameters-003.webp" />

### Inserting Dynamic Content

Used to display specific data from the event in the message.

For example, if the event contains JSON:

```json
{
    "eventTypeKey": "AbandonedCart",
    "keyValue": "2424925572",
    "params": [
        {
            "name": "cartItems",
            "value": [
                {
                    "name": "Conditioner for dry hair",
                    "price": "341",
                    "url": "https://site.com/conditioner-dry-hair",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Le Petit Olivier",
                    "tags_weight": "200",
                    "tags_oldprice": "467"
                },
                {
                    "name": "Magnolia Nobile Perfumed water",
                    "price": "2341",
                    "url": "https://site.com/catalog/perfumed-water-2-750-g",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Acqua Di Parma",
                    "tags_weight": "100",
                    "tags_oldprice": "4467"
                }
            ]
        },
        {
            "name": "recommendedItems",
            "value": [
                {
                    "name": "Shampoo for dry hair",
                    "price": "441",
                    "url": "https://site.com/shampoo-dry-hair",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Le Petit Olivier",
                    "tags_weight": "200",
                    "tags_oldprice": "467"
                },
                {
                    "name": "Magnolia Nobile Face cream",
                    "price": "1341",
                    "url": "https://site.com/catalog/face-cream-2-750-g",
                    "imageurl": "https://site.com/uploads/product/big/20161122/20161122_7zvb.jpg",
                    "brand": "Acqua Di Parma",
                    "tags_weight": "100",
                    "tags_oldprice": "4467"
                }
            ]
        },
        {
            "name": "emailAddress",
            "value": site@ukr.net
        }
    ]
}
```

where:

* **name** – array and field names,
* **value** – the value to be inserted into the message.

In the message, specify the variables that will display the products in the message:

* **$!data.get('recommendedItems')** — The name of the array from which the data needs to be substituted is given in brackets.
* **get(0)** — The index of the array elements is indicated in brackets (counting starts from 0);
* **get('price')** — the name of the event parameter from which data should be substituted is given in brackets.

As a result, the variable might look like this:

* `$!data.get('recommendedItems').get(0).get('price')`

<Image align="center" width="80% " src="https://files.readme.io/e0fc408f43b6c9c85451d287b629099eadfd75082ced56b14d699ca3a852325a-image3.png" />

[Learn more about using Velocity in emails >](https://docs.yespo.io/docs/using-velocity-email)
