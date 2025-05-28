---
title: API Methods for Adding Contacts
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: API Methods for Adding Contacts | Yespo Guide
  description: >-
    The document covers API methods for adding/updating contacts: subscribing
    via forms, bulk imports, and individual updates. It explains double opt-in,
    workflows, segment management, and contact source tracking.
  robots: index
next:
  description: ''
---
**Main methods of adding/updating contacts:**

* *[Subscribe contact](https://docs.yespo.io/docs/api-methods-adding-contacts#subscribe-contact)* (Method type: POST)\
  This method is used to embed subscription form into the website. It creates new contacts and updates existing ones. It also creates events in the system to launch workflows. New contacts are created with "not confirmed", status and require double opt-in. 

* [Add/update contacts](https://docs.yespo.io/docs/api-methods-adding-contacts#addupdate-contacts) (Method type: POST)\
  This method is used to import or update contacts. It has all the features of contact management through API. It allows to add/update one contact or a bulk of contacts, as well as move contacts from one segment to another. Created contacts are already confirmed, that is why this method is not used with subscription forms. It is not designed to launch workflows.

**Useful methods for specific tasks:**

* *[Add contact](https://docs.yespo.io/docs/api-methods-adding-contacts#add-contact)* (Method type: POST)\
  This method is used to add or update one contact.
* *[Update contact](https://docs.yespo.io/docs/api-methods-adding-contacts#update-contact)* (Method type: PUT)\
  This method is used to update one contact. It doesn’t allow creating new contacts. To update a contact using this method you need to know contact id in our system. 
* *[Add/update contacts from external file](https://docs.yespo.io/docs/api-methods-adding-contacts#addupdate-contacts-from-external-files)* (Method type: POST)\
  This method is used to add/update contacts from an external file. You can upload a file with contacts to your server and launch import from this file using this method. Link to file is submitted in the request. Our system downloads the file and imports contacts from it.
* [Attach contact to static segment](https://docs.yespo.io/docs/api-methods-adding-contacts#attach-contact-to-static-segment) (Method type: POST)\
  This method is used to add contacts to segments of the *List* type.
* [Delete from static segment](https://docs.yespo.io/docs/api-methods-adding-contacts#delete-from-static-segment) (Method type: POST)\
  This method is used to delete contacts from segments of the *List* type.

**Additional details:**

* Other methods used for contact creation.\
  Some API methods don’t allow creating contacts. They are designed for other tasks. However, in some cases use of such methods results in contact creation.
* How can I find out how contact was created?

### Subscribe Contact

Method type: POST. [Method description](https://docs.yespo.io/reference/subscribecontact-1).

This method is used to add and update contacts. It is aimed at embedding subscription forms and has the following features:

* new contacts are created with unconfirmed email addresses
* one contact can be added in one request
* contacts are created with maximum speed and are not delayed
* it allows to create events to launch workflows
* if the email address or phone number are already in the contact list, a new contact is not created, instead existing contact is updated

> 🚧 Important
>
> The configuration of confirmation procedure of contact’s email is a must. Find instructions [here](https://docs.yespo.io/docs/subscription-form-configuration).

**Workflows launch**

Method *Subscribe contact* is used to create *events*. You can configure and launch workflow automatically for contacts sent with this method. Two types of events are created:

* `subscribeFromApi` - event title for new contacts
* `subscribeUpdateFromApi` - event title for existing contacts in the system

Every event type can launch its own workflow. So you can configure different workflows for new contacts and contacts created earlier. In addition to that, if you have several subscription forms, you can configure creation of other events to launch other workflows. To do this use optional parameter formType in the request body. Its value is added after the name of event type (hyphenated). For example, if you send "formType": "abc", the event will look like:

* `subscribeFromApi-abc` - for new contacts
* `subscribeUpdateFromApi-abc` - for existing contacts

See below example of a request with this parameter.

Each event contains 2 parameters:

* ContactId - numerical contact id in our system
* EmailAddress - email address. If only telephone numbers are sent, this parameter is not available

These parameters can be used in workflows like this: `${name_parameter}`. For example, `${EmailAddress}`.

Event key is contact id in our system.

If the request is submitted successfully, such events will appear in Event log:

<Image align="center" width="80% " src="https://files.readme.io/810500a522db822951e94945adbfb933c37db5450ddb1819a65090569c0b8087-api-methods-for-adding-contacts-001.webp" />

**Example of request body**

Not all the elements are obligatory. Use those, which you need. Format and description of all fields are available [here](https://docs.yespo.io/reference/subscribecontact-1).

```json
{
    "contact": {
        "channels": [{
            "type": "email",
            "value": "mail@example.com"
        }, {
            "type": "sms",
            "value": "380942583691"
        }],
        "firstName": "John",
        "lastName": "Smith",
        "address": {
            "town": "London",
            "region": "West",
            "address": "First str. 1",
            "postcode": "12345"
        },
        "fields": [{
            "id": "12345",
            "value": "..."
        }]
    },
    "groups": ["Subscribers"],
    "formType": "abc"
}
```

URL for sending request: `/api/v1/contact/subscribe`.

### Add/Update Contacts

Method type: POST. [Method description](https://docs.yespo.io/reference/contactsbulkupdate-1).

This method allows to add/update one contact or a bulk of contacts. In fact, it substitutes manual import of contacts from a file. It works for synchronization of your CRM contact list with our platform. It has the following features:

* It allows to  add/update from 1 to 3000 contacts in one request.
* Created contacts are already confirmed, same as when imported.
* It allows to add contacts to segments or delete them from segments.
* Contacts are added/updated not instantly, it may take a few minutes.
* It allows to create an event to launch a workflow for new contacts.
* The response returns *asyncSessionId*. You can use this *asyncSessionId* parameter in the [Get contact import status](https://docs.yespo.io/reference/getimportsessionstatus-1) method to get import status and ID of contacts.

> 🚧 Note
>
> New contacts submitted using this method are created with confirmed email addresses. It is assumed that these contacts have been already verified with double opt-in in the other system. Sending campaigns to contacts whose emails were not verified with double opt-in is spamming.

**Example of request body**

Not all the elements are obligatory. Use those, which you need. Format and description of all fields are available [here](https://docs.yespo.io/reference/contactsbulkupdate-1).

```json
{
    "contacts": [{
        "channels": [{
            "type": "email",
            "value": "mail@example.com"
        }, {
            "type": "sms",
            "value": "380942583691"
        }],
        "firstName": "John",
        "lastName": "Smith",
        "address": {
            "town": "London",
            "region": "West",
            "address": "First str. 1",
            "postcode": "12345"
        },
        "fields": [{
            "id": 12345,
            "value": "..."
        }]
    }],
    "dedupeOn": "email",
    "customFieldsIDs": [12345],
    "groupNames": ["Customers"],
    "groupNamesExclude": ["Subscribers"],
    "restoreDeleted": false,
    "eventKeyForNewContacts": "newContact"
}
```

For the required fields *externalCustomerId* and *dedupeOn*, the priority for the search is the following:

* externalCustomerId
* dedupeOn

The parameters *externalCustomerId* in the *contacts* array and *dedupeOn* are used to search for already existing contacts in our system.

The parameter *dedupeOn* is used to prevent the creation of duplicate contact cards when adding new contacts. The system performs a search for contacts in the database by media channels (email, phone number) and updates them.

The logic for using *dedupeOn* and *externalCustomerId*:

* If the request includes an *externalCustomerId* that doesn't exist in the database and an email that does exist, the existing contact is updated with the *externalCustomerId* and other fields.
* If multiple contacts have the same email (or phone number), the contact that was updated later than the others is used.
* If there are two contacts with the same email (or phone number), one of which has a different *externalCustomerId* and the other doesn't have an *externalCustomerId*, the latter contact is updated with the *externalCustomerId*.
* If there are two contacts with the same email (or phone number), and both have *externalCustomerIds* that don't match the one in the request, a new contact is created.
* If the contact with the *externalCustomerId* in the request was deleted and the flag *restoreDeleted = false*, this contact is skipped. If the flag *restoreDeleted = true*, the deleted contact is restored and updated.

The arrays *groupNames* and *groupNamesExclude* are used to add contacts to segments and to delete contacts from segments respectively.\
Parameter *dedupeOn* shows how contact uniqueness is checked. When receiving a request, the system searches contacts in the contact list by specified feature (in this case be an email address). If the contact is found, it is updated. If it is not found, a new contact is created.

URL for sending request: `/api/v1/contacts/`.

If your API request is correct, the response returns the HTTP 200 success status code.

> 🚧 Important
>
> Since the methods can process up to 3,000 contacts, some of them may not be added or updated. The list of contacts that can not be added/updated is returned in response 200 in the *failedContacts* field (see the response example in the [API doc](https://docs.yespo.io/reference/contactsbulkupdate-1)). Check the response details to find out the cause.

**Workflow launch**

This method allows to create events only for new contacts. To create events add parameter eventKeyForNewContacts to request body. Value must be a line with Latin symbols and figures with no spaces. Value is used as event type key and its title.

For each new contact the system creates an event with the following parameters:

* contactId - numerical contact id in our system
* EmailAddress - email address (if not sent, the line will be empty)
* SMS - phone number (if not sent, the line will be empty)

Email address is used as event key. If it is not sent, a phone number is used.  

### Add Contact

Method type: POST. [Method description](https://docs.yespo.io/reference/addcontact-1).

This API method is used to create a new contact. Features:

* if a contact with the same email address or phone number already exists, it will be updated
* one contact is created at a time
* created contacts are already confirmed. It doesn’t allow configuring double opt-in
* events are not created. The workflow cannot be launched.

URL for sending request: `/api/v1/contacts`.

### Update Contact

Method type: PUT. [Method description](https://docs.yespo.io/reference/updatecontact-1).

This method is used to update one contact. Features:

* it doesn’t allow creating contacts. It is designed to update existing contacts
* it allows to update one contact at a time
* contact identification is possible only by id
* events are not created. The workflow cannot be launched.

URL for sending request: `/api/v1/contact/{id}`.\
*\{id}* needs to be substituted with numeric contact identifier in our system. It can be obtained with method for contact search by email or by other parameters *[Search contacts](https://docs.yespo.io/reference/searchcontacts-1)*.

Use of identifiers may be inconvenient. So you can update contacts by email or phone number with method *Search contacts*.

### Add/Update Contacts from External Files

Method type: POST. [Method description](https://docs.yespo.io/reference/filecontactsbulkupdate-1).

It allows to add or update contacts from external file. You can upload a file with contacts to your server and launch contact import from it with this method. Our system downloads the file and imports contacts from it. This method has the same features as method *[Search contacts](https://docs.yespo.io/reference/searchcontacts-1)* except the fact that contact data are not sent in the request. They are saved in a separate file.

Method features:

* сontacts are submitted not in request body, but in a separate file
* сreated contacts are already confirmed, like when imported
* it allows to add a contact to segments and delete it from segments
* contacts are added/updated not instantly, it may take a few minutes
* it allows to create an event to launch a workflow to new contacts

Thr file must be saved in CSV format with encoding UTF-8. File requirements and request body format are available [here](https://yespo.io/api/el_ns0_fileContactsBulkUpdate.html).

The file should be saved at Http-resource. URL of the file is indicated in request body in parameter link. Specify login and password in URL to get access to the file.

URL for sending request: `/api/v1/contacts/upload`.

## Attach contact to static segment

Method type: POST. [Method description](https://docs.yespo.io/reference/attachcontactstogroup).

This method adds contacts by contactId or externalCustomerId to a segment of the List type (use only one contact identifier in the request). The maximum number of contacts in one request is 500.

URL for sending request: `/api/v1/group/{id}/contacts/attach`.

\{id} needs to be substituted with a numeric segment identifier in our system. 

File requirements and request body format are available [here](https://docs.yespo.io/reference/attachcontactstogroup).

## Delete from static segment 

Method type: POST. [Method description](https://docs.yespo.io/reference/detachcontactsfromgroup-1).

This method deletes contacts by contactId or externalCustomerId from a segment of the List type (use only one contact identifier in the request). The maximum number of contacts in one request is 500.

If you do not specify IDs, all contacts will be removed from the segment.

URL for sending request: `/api/v1/group/{id}/contacts/detach`.

\{id} needs to be substituted with a numeric segment identifier in our system. 

File requirements and request body format are available [here](https://docs.yespo.io/reference/detachcontactsfromgroup-1).

## Other API Methods Which May Result in Contact Creation

There are several API methods with other purposes, but in some cases, the use of these methods results in contact creation. In such cases created contacts are already confirmed, but aren’t included in any segments.

**Methods for sending messages (email/SMS).**\
If a message is sent to a user not from contact list, such contact is created at the moment of sending. Only communication channel (email address or phone number) is sent to this new contact. No other fields are completed. It is not included in any segments. Events are not created.

* [*send email message*](https://docs.yespo.io/reference/sendemail-1)
* *[send SMS message](https://docs.yespo.io/reference/sendsms-1)*
* /v1/message/\{id}/send
* [send prepared message](https://docs.yespo.io/reference/sendextendedpreparedmessage-1)

**Method of submitting orders.**\
When an order is added to our system, the system verifies whether there is a contact with a specified email address or phone number in the contact list. If not, it is created. Some order data, such as email address, phone number, name/surname are sent to this new contact. Please note that if the contact already exists in contact list, it won’t be updated. Name/surname from the order won’t be added.\
This method allows to create events in the system. So you can do some additional operations launching workflow to the contact who has made an order. For example, you can add it to a segment.

* *[Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1)*

**Contact creation/update with event and workflow.**\
You can send event through API to launch the workflow for contact creation or update. To do this there are specific blocks in workflow. You need to submit contact’s email address and a line with the required format in event parameters to complete contact’s fields.

* *[Generate event](https://docs.yespo.io/reference/registerevent-1)*

## How to Find a Contact Creation Source

You can always check which method was used to create a contact

<Image align="center" width="80% " src="https://files.readme.io/a10c85a1405a51c626615cf13c5347f4b47de6d2ab124e326c713bfebe2b2dad-api-methods-for-adding-contacts-002.webp" />

To do this go to *Contacts → All contacts* and press View button against required contact.  

A new window with contact information will open.

<Image align="center" width="80% " src="https://files.readme.io/77e1bdb930674ef43d0dffc094f5a3ea39e56c0656da5e876615f01c253476ae-api-methods-for-adding-contacts-003.webp" />

You will see required information in the field Source.

### Source names for different methods

**Main methods:**

* *Subscribe contact* (subscription form)
* *Search contacts* (contact import)
* *Search contacts* (API)
* *Add/update contacts from external files* (contact import)

**Methods of sending email/SMS messages:**

* *Send email message* (single message)
* *Send SMS message* (single message)
* */v1/message/\{id}/send* (single message)
* *Send prepared message* (single message)

**Method of sending orders:**

* *Add orders* (Integration of orders for RFM)
