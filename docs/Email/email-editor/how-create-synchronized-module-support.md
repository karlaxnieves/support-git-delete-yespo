---
title: Creating Synchronized Modules
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating a Synchronized Module | Yespo Guide
  description: >-
    The document explains how to create, synchronize, and update synchronized
    modules in email templates, allowing for automatic updates across all
    templates containing the module
  robots: index
next:
  description: ''
---
The synchronized module is an email element that can be automatically updated in all [templates](https://docs.yespo.io/docs/launching-an-email-campaign) containing this module, meaning you don't have to manually edit each email, which is especially convenient when working with triggered emails.

Use synchronized modules to simultaneously update elements in all email templates: logo, contacts, social media icons, etc.

## Creating Module

1. Open your email or create a new one (the **Messages → Messages** section).

<Image align="center" width="80% " src="https://files.readme.io/08963bb77b8d9b8e6d070db250c820494920aee591077002eb1c5e4f6d7978d0-sync-module-3.webp" />

2. Select an element (container/structure/stripe), click on the three dots on the right if it is a structure or stripe, and on the left if it is a container.

<Image align="center" width="80% " src="https://files.readme.io/92baccc-sync_modules_1.webp" />

3. Click the **Save as module** icon, after which you need to enter the module settings on the left panel.

<Image align="center" width="80% " src="https://files.readme.io/8f32e7a-sync_modules_2.webp" />

### Module Settings

Do the following in the left panel:

1. Enter the module name to quickly find it among other modules.
2. Add a description (optional) to clarify information about the specifics of its use.
3. Select a category so that the settings from the [Appearance](https://docs.yespo.io/docs/designing-your-email) tab are applied according to the element type (optional).
4. Activate the **Synchronized** switch.
5. Add [tags](https://docs.yespo.io/docs/how-add-tags) for easy searching.
6. The ID is generated automatically for use in emails with dynamic variables, but you can change it to make the name meaningful.
7. Save the module.

<Image align="center" width="80% " src="https://files.readme.io/42112e04a7daf139f52ef79a7e0660beb076f4f6c6f2abbe498c457e7e44fb13-sync-4.webp" />

The **OFF** icon will appear in the lower right corner of the saved module, which indicates that the module has been added to synchronized but is not yet synchronized with emails.

<Image align="center" width="80% " src="https://files.readme.io/31481e4-sync_modules_4.webp" />

## Synchronizing Module

To synchronize, click on the synchronized element and make the synchronized module switch active on the left side of the settings panel. Perform the same action each time you add the synchronized module from the library to the template.

Now, you can use the synchronized module in other emails. **OFF** will change to **ON**.

<Image align="center" width="80% " src="https://files.readme.io/ea874365d59d01885cda3bdda259c2e31a3cab3e72fcd6812fac707ba60433ac-sync-3.webp" />

> ❗️ Important
>
> A synchronized module cannot be dropped or added to another synchronized module. Synchronization of the internal module will be deactivated.

## Updating Synchronized Module

To update the synchronized module, open any email where it is used:

1. Click on the area in the email where it is located.
2. Make the necessary changes.
3. The word OFF will appear again in the lower right corner; click on the block.
4. The settings for the synchronized module will open on the left. Select one of the options:

* Update module: current changes will be saved in the library and applied to all templates with this module.
* Restore: the module content will be restored from the library.
* Make unsynchronized: save changes only in this template, breaking the link with the library.

<Image align="center" width="80% " src="https://files.readme.io/a88320970583b7deab7e6c5f16aa299efb1562f44c2a9a3e4fd88a0dba600e3b-sync-2.webp" />

Confirm the update. **OFF** will change to **ON**.

## Updating Modules in All Emails

To bulk update emails with synchronized modules, go to **Messages → Messages** after saving the changes in the email. Click on **Update synchronized modules**.

<Image align="center" width="80% " src="https://files.readme.io/4fb9204442323989efd4629e490d4771725a2b55917ee8b6780bd0d1e4188cc6-sync-modules-7.webp" />

You can select the messages you need to update:

* by specifying their label or ID in the search field;
* by selectively selecting emails using a checkbox in the list;
* by selecting all emails using the checkbox above all messages.

<Image align="center" width="80% " src="https://files.readme.io/d9150856c5e3c8fab8b1c4de9afd37e498d9db486e8fd170d532e269186ac5ea-sync-modules-8.webp" />

Confirm the action by clicking on **Update modules**.

The status of the update process will be displayed in place of the update button. You can abort it if necessary or wait for it to complete.

<Image align="center" width="80% " src="https://files.readme.io/a76d3d8c86b7082938348b5f3ef90224431c448895b93a665ab45c1326b5fcd0-sync-modules-9.webp" />

If you **DO NOT** run a bulk update of synchronized modules, but they are in several emails, they will be updated after opening each template. For example, if Module 1 is synchronized and is used in Email 1 and Email 2, then after editing the synchronized module in Email 1, in Email 2 it will be updated when opening Email 2.

## Viewing Module Information

If you need to see which synchronized module is used in the email, click the **Save as module** icon. You will see this synchronized module's name and other parameters in the left panel.

<Image align="center" width="80% " src="https://files.readme.io/b69267f2ee87e7e1142b1dbc9fbb2895d568ce9b4e91ec4de8b2f43899a2db29-sync-5.webp" />