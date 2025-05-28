---
title: Contact Blacklist
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Contact Blacklist | Yespo Guide
  description: >-
    What is the blacklist, what contacts get blacklisted, how to edit, delete or
    restore blacklisted contacts. Where to find blacklisted contacts in the
    system and how to import them to different segments.
  robots: index
next:
  description: ''
---
A blacklist is a contact category in the Yespo system that is excluded from campaigns due to the inability to deliver messages to them. Most often, it includes non-existent, full, or inactive mailing addresses.

## What Blocked Contacts Look Like?

Blacklisted contacts are displayed as crossed-out emails or phone numbers.

<Image align="center" width="80% " src="https://files.readme.io/2ccb12bb8e43452fcd7b9089bb8d5597b1974c022e78dd0f3b03f984c5b60ba0-blacklist-1.webp" />

## How Do Contacts Get Blacklisted?

Suppose you or someone from other organizations in Yespo previously sent emails to addresses to which the mailer responded to our service that they do not exist. In that case, these contacts are marked accordingly in the system.

Сontacts can be blacklisted at any of the following stages:

* with [manual import](https://docs.yespo.io/docs/uploading-file-with-user-profile-data);
* during import via API;
* when sending out messages;
* in case of adding an address to blacklist manually;
* temporary blocking is used in case of receiving an error status that the mailbox is full or frozen due to inactivity.

Please note that the blacklist is end-to-end in the Yespo system, so you can add a new email or phone number that is already blocked in the system.

## What Does Temporarily Blocking a Contact Mean?

If, when trying to send a newsletter, an error status is received indicating that the mailbox is full or inactive, it is temporarily blacklisted:

* the first error is blocking addresses for a day,
* the second — for 2 days,
* the third — for 3 days,
* the fourth — for 90 days.

Automatic address unlocking occurs once a day – at night.

## Is It Possible to Add Contacts to the Blacklist Yourself?

No, however, you can send a corresponding request to [support@yespo.io.](mailto:support@yespo.io.) Our specialists can add to the blacklist or unsubscribe both individual subscribers and segments with emails and phone numbers. They will be blacklisted in your organization after moderation.

## How to Understand Why a Contact Is Blacklisted?

To find out the reason for being added to the blacklist, you need to go to the contact card by clicking on the line with their data. For example, you can see the mailer's answer on the screen below that the email does not exist.

<Image align="center" width="80% " src="https://files.readme.io/0d92def89ce68e810b7459a1c8d63588b11980aab8ad6946d995e6cdaefa5674-blacklist-2.webp" />

## What Happens to Contacts After They Are Blacklisted?

These emails are not included in further campaigns, so they do not affect your reputation as a sender in any way. They are simply stored in Yespo and can be deleted or restored at the request of the account owner in the database.

<Image align="center" width="80% " src="https://files.readme.io/fcd558d96987c52c4f1b0fb1e9c021ceee4fa410e9d9e974f6ca05b31ef6c261-blacklist-3.webp" />

## How to Find a Blacklist in Yespo?

You can find the blacklist in the following tabs of the *Contacts* section.

**1\. All contacts**

To see which contacts have been blacklisted, go to *Contacts → All Contacts*. Click on the *Blacklisted* item in the menu on the left.

The blacklist is displayed for emails and phone numbers.

By clicking on the blacklist in the corresponding channel, you can view the addresses/numbers included in it.

<Image align="center" width="80% " src="https://files.readme.io/790413bef3cd0980d4d928a6df65bd8c9ce236b4e5223faf453c3e21673285d6-blacklist-4.webp" />

Click the *Recalculate* *contacts* button to determine each channel's blocked contacts. 

<Image align="center" width="80% " src="https://files.readme.io/cdb1dc6025553e931bebd6f6ff9b7ab9b760b9f55d0c95713c208dc9c9184cd0-blacklist-5.webp" />

Also, you can perform [various actions with individual contacts](https://docs.yespo.io/docs/how-work-all-contacts-tab-system) on this tab, for example, edit, delete, and view the reasons for being blacklisted.

**2. Analytics**

Here, you can see the contact list structure by activity:

* active;
* inactive;
* lost;
* never sent.

You can see the number of contacts in the blacklist in the last two categories. At the same time, the *Lost subscribers* segment includes contacts who previously received messages from you and were later blocked. The *Never sent* segment includes contacts that haven’t received any messages since they were immediately marked as blacklisted.

<Image align="center" width="80% " src="https://files.readme.io/67544f69ae71b0ee2114c6ea9ce801030033ce050c6b31b6ed4882320be52a6f-blacklist-6.webp" />

By clicking on the diagram elements, you will see the structure of each segment. You can also download contacts from each segment.

## How Does the Blacklist Category Differ from Undelivered?

Undelivered is a sending status that occurs when an email exists. Still, delivery of the message is impossible, for example, due to temporary blocking or fullness of the mail account, mail server failure, etc.

## What Actions Can Be Taken with Blacklisted Contacts?

You can:

* edit a contact and view its activity;
* recalculate quantities in channels (email, phone);
* analyze the number of such contacts in your base (*Lost, Never sent*) and export them to lists;
* explore the reasons for being blacklisted;
* delete.

## How to Remove Blacklisted Contacts from the System?

You can delete individual blacklisted contacts or all of them together.

To remove individual contacts, go to *All contacts*. Select the *Email* or *Phone number* tab where you want to find and delete the contact. Click the delete icon (trash can) in the row of the subscriber you selected. Next, you can add a reason for deletion if you restore it. Click the *Delete* button.

<Image align="center" width="80% " src="https://files.readme.io/8477c949a3a3906ec8b4536bd51ff46b7e5b71c682f3afa28ddb51a5ceec45c6-blacklist-7.webp" />

To delete all contacts in the blacklist, go to the blacklist in one of the channels (email/phone number) in the *All contacts* section. Click the *Delete contacts* button. Then click *Delete*.

<Image align="center" width="80% " src="https://files.readme.io/ff40543774977916212e50fa1a5666a005cf1562302f2633431c642e05f3325a-blacklist-8.webp" />

## How to Export Blacklisted Contacts?

**1\. Export to a pre-created segment from the *All contacts* section**

Create a segment to which you want to upload contacts by clicking *Contacts → Segments → Add segment → List* (create without contacts).

<Image align="center" width="80% " src="https://files.readme.io/a4aec227dbee75fca664cc1cfac6cf0363abafe2d0c6df3434e28c072cfa293d-blacklist-9.webp" />

After that, in the *All contacts* section, click the *Blacklisted* category in the channel you need (email/phone number); click *Export → To the existing lists* and select the created segment.

<Image align="center" width="80% " src="https://files.readme.io/f440ba044cecae10ea793167ca227b46cbdb5fe9c5e17c260ad8b98b9fd45c80-blacklist-10.webp" />

To delete the segment, click the "..." icon and select *Delete segment*.

<Image align="center" width="80% " src="https://files.readme.io/47477149176d11e9bc981b258e5675f9887ff36c8f69cd813f5906f53af07679-blacklist-11.webp" />

Confirm deleting the segment with contacts by checking the appropriate box and clicking the *Yes* button.

<Image align="center" width="80% " src="https://files.readme.io/a4d116050302d5b9aab9e98659c1ab431baeef6b6d1044a77c4f05c99a0a16f6-blacklist-12.webp" />

**2. Export to a file from the*All contacts* tab**

To download contacts to a separate file, select *Export → To CSV* in the blacklist category of the channel you need.

<Image align="center" width="80% " src="https://files.readme.io/e7bd27a205969dfb022b325c5e8cd959087ad610d6ab0754256750503020e5b4-blacklist-13.webp" />

Next, click the *Export* button. If the *Export Email only* option is active, your file will contain only email addresses. To get all contact data stored in Yespo, turn off this option.

<Image align="center" width="80% " src="https://files.readme.io/7bb8d8ed543aa9ab565209cf79d770e189882e96ab144e54e1d086ca73198785-blacklist-14.webp" />

**3\. Export to a segment from the *Analytics* tab**

Open the *Analytics* tab. Click the *Blacklisted category* in the segment of lost contacts or those to whom messages were never sent. Edit the name and click the *Create a segment* button.

<Image align="center" width="80% " src="https://files.readme.io/f39ad5932a6e385c453b5926c376f1ee4f0ee1c893b217970dca227558b77143-blacklist-15.webp" />

The created segment will appear in the *Segments* section. You can delete it like a list created by uploading it from the *All contacts* section.

## What Happens When Deleting Сontacts?

When you delete a contact or segment along with its contacts, they are moved to the *Deleted* section. The system continues to store contacts’ statuses, but contacts are no longer displayed in the *All contacts* tab.

In this case, when re-importing, the system will recognize that these are contacts from the blacklist and will not launch a mailing campaign on them.

## How to Recover Deleted Contacts?

You can recover deleted addresses and phone numbers in one of the following ways:

* When importing, activate the *Recover and update previously deleted contacts* option.

<Image align="center" width="80% " src="https://files.readme.io/bd76e6be2a93b759c1b7fdd675ba410b0fd573292becae526e8c889e43f247dc-blacklist-16.webp" />

* Click the recovery icon (rounded arrow) in the subscriber line in the *All contacts → Deleted* section.

<Image align="center" width="80% " src="https://files.readme.io/65971cd7f04891b523a9e05b853509aa06dc9db2d98c2329f495da10ca33f7d2-blacklist-17.webp" />

The contact will appear on the blacklist again.

## How to Make a Blacklisted Contact Active?

You cannot activate blacklisted contacts yourself; however, upon request to our technical support, we can do this for you. Send a request confirming that this address or phone number exists.

## What Happens When Removing Contacts from the Blacklist?

After our support team activates a contact from the blacklist, you can use them in future campaigns.
