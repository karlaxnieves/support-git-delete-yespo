---
title: Subscription Categories
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Subscription Categories | Yespo Guide
  description: >-
    Subscription categories enable to send campaigns to particular contact
    segments. Assign contacts to categories based on their preferences and send
    them messages they are interested in.
  robots: index
next:
  description: ''
---
Subscription categories allow companies to manage campaigns and send them to particular contact segments. You can create unlimited subscription categories, for example:

* Newsletters;
* Product categories;
* Promo and sales;
* Subscriptions to products of a particular brand.

Contacts will be included in categories based on their preferences and will receive only campaigns they are interested in.

> 📘 Note
>
> Subscription categories aren’t a default feature. You need to create them manually.

<Embed url="https://www.youtube.com/watch?v=O0IFa5xgGWE" href="https://www.youtube.com/watch?v=O0IFa5xgGWE" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FO0IFa5xgGWE%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DO0IFa5xgGWE%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FO0IFa5xgGWE%252Fhqdefault.jpg%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

## Creating Category

1. Go to your profile → **Settings → Subscription categories** and click **New category**.

<Image align="center" width="80% " src="https://files.readme.io/168330a9312755bf83ba2c6d42a035a933065088d6d21223bfda22b277ab1f7c-caregoty-en-001.webp" />

2. Enter the title and click **Done**. The key is created automatically based on the title. Keys are used for API integrations.

<Image align="center" width="80% " src="https://files.readme.io/3da61b7e329ccaf7ee0b948713b828345387d703c109eebe7a6b3886ddc1d839-caregoty-en-002.webp" />

3. The system will create the category:

<Image align="center" width="80% " src="https://files.readme.io/a24ebde623b050f6781d66785ff1e76af229c5bf6e19cdc3e5284a3ea482f93b-caregoty-en-003.webp" />

and a segment with the same name that will appear in the general list of segments. The corresponding label marks each segment assigned to the category.

<Image align="center" width="80% " src="https://files.readme.io/ba42d3c2103b1ef94da61f386691d4fe580b98b201241a0f8daf4659588db491-caregoty-en-004.webp" />

You can create unlimited categories.

> 📘 Important
>
> A segment assigned to the subscription category cannot be deleted or renamed in the general list. Delete the corresponding subscription category in **Settings → Subscription categories** to delete the segment. Contacts included in the deleted segment will remain in the system.

<Image align="center" width="80% " src="https://files.readme.io/62501dd93a302bc35284dad310467f8799f2fd7c67023111be8bc730ac6523d3-caregoty-en-005.webp" />

## Adding Contacts to the Category

You can add contacts to the category in the following ways:

* Importing new contacts;
* Exporting existing contacts;
* Transferring contacts from the subscription form or CRM [via API](https://docs.yespo.io/reference/getting-started-with-your-api).

The same contacts added to one category via different methods are not duplicated.

### Importing New Contacts

1. Choose the necessary subscription category and click *Import contacts*.

<Image align="center" width="80% " src="https://files.readme.io/c91ecadd1750056c293c444b8e48a54cdb8a3d7faa7269d77a70b2996651a232-caregoty-en-006.webp" />

2. You’ll be directed to [New import](https://docs.yespo.io/docs/file-uploading). Upload the file with contacts and map contact fields.

<Image align="center" width="80% " src="https://files.readme.io/250cd3b0162c08038a694dd4419b022bef39fc7a64adb536e987fa464d0a5327-caregoty-en-007.webp" />

3. The assigned segment will be specified automatically.
4. Once the import is successfully completed, contacts will appear in the category.

### Exporting Existing Contacts

You can export to the category existing single contacts or list segments.

1. To export a single contact:

* Go to **segment**, click **Add contact** and select **Add from existing**.

<Image align="center" width="80% " src="https://files.readme.io/f1a47006d62f66b21b755be1d8ca6c27834406ec725afeb0b388484d4659515f-caregoty-en-009.webp" />

* activate the checkboxes next to the required contacts in the list and click **Done**.

<Image align="center" width="80% " src="https://files.readme.io/e790f4afa347518f12ee49d936bfcd61572367373c8e08db739ba8a85e843b26-caregoty-en-010.webp" />

2. To export from the segments list:

* Go to the **segment** **from which** you will be adding contacts, click **Export**, and select **To existing lists** from the dropdown menu.

<Image align="center" width="80% " src="https://files.readme.io/5107032cee942f7d9a799ba8e15616749312ecb19b1e444e7299922e6feedc68-caregoty-en-011.webp" />

* Activate the checkboxes next to the **segment to which** you will add contacts and click **Done**.

<Image align="center" width="80% " src="https://files.readme.io/7ea51dcb57bbeb4ebf5ee9bd0b88c41b51456f07a90df6b9cd88c4577a447407-caregoty-en-012.webp" />

### Transferring Contacts via API

If you want to configure subscription category transmission via API, use:

* The subscriptions field in [v1/contact/subcribe](https://docs.yespo.io/reference/subscribecontact-1).
* The groups field in [v1/contact](https://docs.yespo.io/reference/addcontact-1).
* The groupNames field in [v1/contacts](https://docs.yespo.io/reference/contactsbulkupdate-1).

### Contact Management

You can exclude contacts from a category in the following ways:

* Exclude all contacts
* Delete individual contacts
* Delete a category from a contact card.

To delete all contacts from the category, click **Empty segment**.

<Image align="center" width="80% " src="https://files.readme.io/ad6535ed372fe4b5b67a49b6b6c05f3e9dc58db6fa63a35792c46dbb7dcf7893-caregoty-en-013.webp" />

To delete a single contact click the **trash icon** on the right of the necessary contact.

<Image align="center" width="80% " src="https://files.readme.io/117aa0480b2b2f47b14ea481521f7e26f4ecab139a2f6f6d84aafcb8720a3e6a-caregoty-en-014.webp" />

To remove a category from a contact card, go to it and click **Edit contact**.

<Image align="center" width="80% " src="https://files.readme.io/4293f4bbbcff4b8f7df0319713ba200b93d9360ef23978f3fb46a92560ccb854-caregoty-en-015.webp" />

Next, click **Edit contact subscription** and uncheck the unnecessary categories.

<Image align="center" width="80% " src="https://files.readme.io/79089ecfe71e7b0935d41ea4f9bb3b02e3c87208490ea4d848177bd6eb4e697a-caregoty-en-016.gif" />

Contacts that are excluded from the category remain in the account and will be available for other campaigns. The category itself is not deleted.

## Setting Up Unsubscription

You can set up unsubscription from all campaigns or from a certain category. A contact can unsubscribe:

* In the personal account on the site;
* In the email;
* On the unsubscribe page.

Subscription categories can be displayed on the unsubscribe page so that users can update their preferences on their own. To set up such a page, send a request to our support team.

<Image align="center" width="80% " src="https://files.readme.io/41ebdb1dcc6fa2f3fccd0a2f259bdb77cbcb68906e250018a477ac2c47561817-caregoty-en-018.webp" />

## Creating Category-Based Campaign

You can use subscription categories to control the frequency of campaigns depending on their subscriber’s interests. Subscription categories apply to all communication channels. Subscription categories are specified when the message is created.

* In **Messages → Messages**, create a message or choose the existing one.
* Open its general settings, click **Select categories**, and select categories applicable to the message. You can select several categories. Below is an example of choosing categories for email.

<Image align="center" width="80% " src="https://files.readme.io/15e5d733c381d912ac7859ad094f1593c3b0d28bf7ac37b9d8b6e83eb992f1cf-caregoty-en-017.webp" />

When scheduling the campaign, you can select any other segments to send it. 

The system will automatically calculate the contacts following the rules:

* The message is sent only to contacts from the selected segments who have subscribed to the corresponding subscription category.
* If the message isn’t assigned to any category, it will be sent to all contacts from selected segments.

[A campaign report](https://docs.yespo.io/docs/campaigns-analytics) will show the subscription categories applied to the message.

<Image align="center" width="80% " src="https://files.readme.io/323269ea82d241a9d07b79779c5d295f1d896e34b2a63a575f471decc4a50a60-categories_16.webp" />