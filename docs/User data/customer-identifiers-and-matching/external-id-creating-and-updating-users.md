---
title: External ID for Creating and Updating Contacts
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: External ID for Creating and Updating Users | Yespo Guide
  description: >-
    The document explains the importance of using an external ID as a unique
    contact identifier in Yespo's system to prevent duplicate profiles and
    ensure comprehensive data collection
  robots: index
next:
  description: ''
---
The external ID is a [unique contact identifier](https://docs.yespo.io/docs/customer-identifiers-and-matching) generated in your system. We recommend using an external ID as the main identifier in the API request field *externalCustomerId* (or *user\_id* in [Mobile SDK](https://docs.yespo.io/reference/integrating-your-app-with-yespo)). It will help you avoid duplicating contact profiles, collect all available data into a single contact profile, and get complete information about their interaction with your company.

## Identifier Types

There are 2 types of contact identifiers — conditionally permanent and changeable:

* **conditionally permanent** — email, phone number, and other contact data received during contact’s registration.
* **changeable** — web cookies, mobile, telegram and web tokens.

As a rule, changeable IDs enter the system first, but the external ID is only linked to conditionally permanent IDs.

> 📘 Important
>
> The external ID must be created in your system at the time you first receive any conditionally permanent ID

To better understand how contact data enters the system and how to optimize contact identification, consider 2 basic use cases: creating contacts from mobile applications and websites.

## Use Case 1. Creating and Updating Contact from the Mobile App

1. Contact installs the application on a mobile device with Android OS.
2. The application transfers the contact's mobile token to Yespo ([Add/update a contact](https://docs.yespo.io/reference/addcontact-1) API method).
3. Yespo creates a contact profile with this token as an ID.
4. Contact registers in the application.
5. Conditionally permanent identifiers such as email, phone number, or name enter your system.
6. Your system assigns this contact a unique ID and passes it to Yespo along with other identifiers, including a mobile token ([Add/update a contact](https://docs.yespo.io/reference/addcontact-1) API method).
7. Yespo finds user profile with this mobile token and updates its profile by writing new identifiers to it.

## Use Case 2. Creating and Updating Contact for the Website

1. Non-logged-in contact visits your site.
2. Appropriate cookies are transmitted and recorded in Yespo. The contact profile is not created (the web tracking script is used).
3. Contact registers on the site or subscribes to the newsletter.
4. Conditionally permanent identifiers such as email, phone number, or name enter your system.
5. Your system assigns this contact a unique ID and passes it along with other IDs to Yespo ([Add/update a contact](https://docs.yespo.io/reference/addcontact-1) or [Subscribe contact](https://docs.yespo.io/reference/subscribecontact-1)).
6. Yespo saves the contact with all transferred identifiers and adds their previous history of interaction with your site (cookies).

After a contact profile has been created in Yespo with the External ID field, we recommend making each profile’s update by this field — for example, at login ([Add/update a contact](https://docs.yespo.io/reference/addcontact-1)) or creating order ([Add orders](https://docs.yespo.io/reference/ordersbulkinsert-1) or [Generate event](https://docs.yespo.io/reference/registerevent_1)). In this way, you will be able to constantly maintain the relevance of all contact data since external ID is unique and immutable, while other identifiers, even conditionally constant ones, can change.

> 📘 Note
>
> If your system does not assign IDs to contacts, you can use Yespo's system ID (*contactId*) and save it on your side as a contact ID. However, using the external ID is a better option because this identification 100% prevents the creation of duplicates.

## External ID in Single Contact API Methods

Updated logic of single API methods:

### [Add/update a contact](https://docs.yespo.io/reference/addcontact-1)

The system searches for a contact by external ID when getting a request:

* if the contact profile with this external ID is found, it is updated with the data from the request;
* if the contact profile with this external ID has been removed, it will be restored;
* if the contact profile is not found, it will be created in the system;
* if there is no external ID in the request, the creation logic remains unchanged.

### [Update contact](https://docs.yespo.io/reference/updatecontact-1)

The contactId is specified in the request URL, and the external ID is passed in the body:

* if this external ID already belongs to the contact with another contactId, an error will occur;
* if the external ID does not belong to another contact, the contact will be updated and given that ID;
* if there is no external ID in the request, the creation logic remains unchanged.

### [Get contact](https://docs.yespo.io/reference/getcontact-1)

The external ID is added to contact data returned by request.

### [Subscribe contact](https://docs.yespo.io/reference/subscribecontact-1)

The external ID has the highest priority in the contact search logic; if the contact profile with this identifier is not found, the system searches for it by email address; if the email is not found — by phone number.

## External ID in Bulk Contact API Methods

Updated logic of bulk API methods:

### [Search contacts](https://docs.yespo.io/reference/searchcontacts-1)

You can set the uniqueness of the contact search by the externalCustomerId field. In this case, you cannot set other search parameters.

### [Add/update contacts](https://docs.yespo.io/reference/contactsbulkupdate-1)

When importing contacts to Yespo, you can use any field to define their uniqueness. For example, import contacts with uniqueness by email and, at the same time, add or update their external ID.

## Export External ID to BigQuery and PostgreSQL

Export external IDs to BigQuery and PostgreSQL — they will appear in the corresponding column in the contacts table. By default, this option is available for all new exports. If you need to create one for existing exports, please contact our support team.

## Finding Empty External IDs in Yespo Account

Create the dynamic segment to find all your contacts with empty external IDs.

1. Go to *Contacts → Segments → Add Segment* and create the dynamic segment.
2. Add condition: *Fields → External ID → is empty* and click *Done*.

<Image align="center" width="80% " src="https://files.readme.io/c20f8b32597e8bf7a7f27bf1ca1cb0b47cb3b0e3739557c028140ea5a9573537-External_ID.webp" />

The system will find all contacts without external IDs and place them into this segment. As the segment is dynamic, all new contacts without external IDs will be also automatically placed in it.
