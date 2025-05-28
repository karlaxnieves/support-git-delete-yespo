---
title: Identification of Contacts
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Identification of Contacts | Yespo Guide
  description: >-
    Learn details about contact identification in Yespo for effective tracking
    and communication
  robots: index
next:
  description: ''
---
Our platform uses scripts for the identification of contacts. Correct identification is essential for better mapping of contacts in tracking and in web push notifications.

The script collects data from the following sources, as described below.

## Cookies

When a person visits your site for the first time, the only information about that visitor is the ID from the cookie file stored on the customer’s computer. \
The script writes this ID into the customer’s browser. This ID is used for tracing and storing historical data about the customer.

## UTM Tags

UTM tags are small snippets of code that you can add to the end of links that you insert in your messages. In our system, UTM tags are turned on by default.

The script takes the contact ID\* from the UTM tag and uses it in the tracking events. Also, this contact ID is used for linking a web push token to the existing contact.

*\*The contact ID is the identifier of a customer, whose data you store in the system.*

A contact is identified by the *contactId* parameter when navigating from a message to a website. We get the *contactId* from UTM tags according to the following priority:

1. *etm\_term* – if the tag is configured.
2. *utm\_content=Yespo-$contactId* — transmission of the *contactId* is configured by default.
3. *utm\_source=Yespo-$type* + *utm\_content=$contactId* – if the *Yespo* value is specified in *utm\_source* (it can be changed if necessary, *contactId* will be transferred from tags with higher priority).

> ❗️ Important
>
> For the script to work properly, do not change the default values of the *utm\_content* tag

## Web Push

When your customer subscribes to web push notifications, a new contact is created in your contact’s base together with a web push token.

If the same contact follows a link in your message (for example, an email or a Viber message), the UTM tag in the link contains the contact ID, if it exists in your base. 

In this case, we connect the contact ID of the existing contact and the web push token of the contact created later. The contact becomes more complete.

> 📘 Note
>
> You have to enable the Enable UTM tags for all language versions option when configuring your web push notifications. Read [this information](https://docs.yespo.io/docs/how-create-and-manage-web-push-notifications#additional-settings) to learn more.

## Subscription Form

A contact can enter the email address or a phone number in a subscription form that you show on your site. The script installed on your site identifies the contact ID connected to that address and saves it in the browser. This contact ID is substituted afterwards in tracking events or for checking the subscription status in subscription forms.

If there is no contact having such an email address or a phone number, a new contact ID is created.

> 📘 Note
>
> The contact ID received after a subscription using the subscription form has higher priority than that received after a subscription using a web-push notification.

## Sending Events Using JavaScript Requests

You can send to our system the information that you collected about contacts on your website. This works if you have installed and activated the web tracking script on your site.\
There are two ways to transfer the contact information:

* Using the [Customer data](https://docs.yespo.io/docs/how-set-web-tracking-sending-events-java-scipt-request#customer) event.
* Passing the information in the [General Info](https://docs.yespo.io/docs/how-set-web-tracking-sending-events-java-scipt-request#site-visitor-data) object inserted into any event. See the example below.

```json
- eS('sendEvent', 'PageView', {  
   'PageView': {  
   "GeneralInfo": {  
  		"externalCustomerId": "1234509876",  
  		"user_email": "[example@email.com](mailto:example@email.com)",  
  		"user_phone": "380501234567",  
  		"user_es_contact_id": 100500  
  		},  
   }  
  });
```

Read [Transferring website behavior data via JavaScript requests](https://docs.yespo.io/docs/how-set-web-tracking-sending-events-java-scipt-request) for more details.

The transferred information is saved in our script. All the events passed to our system will contain this data.
