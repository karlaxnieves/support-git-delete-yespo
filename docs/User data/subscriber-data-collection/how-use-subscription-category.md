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

- Newsletters;
- Product categories;
- Promo and sales;
- Subscriptions to products of a particular brand.

Contacts will be included in categories based on their preferences and will receive only campaigns they are interested in.

> 📘 Note
> 
> Subscription categories aren’t a default feature. You need to create them manually.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FO0IFa5xgGWE%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DO0IFa5xgGWE&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FO0IFa5xgGWE%2Fhqdefault.jpg&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=O0IFa5xgGWE",
  "title": "How to Use Subscription Categories in Yespo",
  "favicon": "https://www.youtube.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/O0IFa5xgGWE/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=O0IFa5xgGWE",
  "typeOfEmbed": "youtube"
}
[/block]


## Creating Category

1. Go to your profile → _Settings → Subscription categories_ and click _New category_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/168330a9312755bf83ba2c6d42a035a933065088d6d21223bfda22b277ab1f7c-caregoty-en-001.webp",
        "",
        "New category"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the title and click _Done_. The key is created automatically based on the title. Keys are used for API integrations.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3da61b7e329ccaf7ee0b948713b828345387d703c109eebe7a6b3886ddc1d839-caregoty-en-002.webp",
        "",
        "Title"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. The system will create the category:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a24ebde623b050f6781d66785ff1e76af229c5bf6e19cdc3e5284a3ea482f93b-caregoty-en-003.webp",
        "",
        "Subscription category in segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


and a segment with the same name that will appear in the general list of segments. The corresponding label marks each segment assigned to the category.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba42d3c2103b1ef94da61f386691d4fe580b98b201241a0f8daf4659588db491-caregoty-en-004.webp",
        "",
        "Segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can create unlimited categories.

> 📘 Important
> 
> A segment assigned to the subscription category cannot be deleted or renamed in the general list. Delete the corresponding subscription category in _Settings → Subscription categories_ to delete the segment. Contacts included in the deleted segment will remain in the system.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62501dd93a302bc35284dad310467f8799f2fd7c67023111be8bc730ac6523d3-caregoty-en-005.webp",
        "",
        "Delete category"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Adding Contacts to the Category

You can add contacts to the category in the following ways:

- Importing new contacts;
- Exporting existing contacts;
- Transferring contacts from the subscription form or CRM [via API](https://docs.yespo.io/reference/getting-started-with-your-api).

The same contacts added to one category via different methods are not duplicated.

### Importing New Contacts

1\. Choose the necessary subscription category and click _Import contacts_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c91ecadd1750056c293c444b8e48a54cdb8a3d7faa7269d77a70b2996651a232-caregoty-en-006.webp",
        "",
        "Import contacts"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2\. You’ll be directed to [_New import_](https://docs.yespo.io/docs/file-uploading). Upload the file with contacts and map contact fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/250cd3b0162c08038a694dd4419b022bef39fc7a64adb536e987fa464d0a5327-caregoty-en-007.webp",
        "",
        "New import"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3\. The assigned segment will be specified automatically.

4\. Once the import is successfully completed, contacts will appear in the category.

### Exporting Existing Contacts

You can export to the category existing single contacts or list segments.

1. To export a single contact:

- Go to _segment_, click _Add contact_ and select _Add from existing_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1a47006d62f66b21b755be1d8ca6c27834406ec725afeb0b388484d4659515f-caregoty-en-009.webp",
        "",
        "Add from existing"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- activate the checkboxes next to the required contacts in the list and click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e790f4afa347518f12ee49d936bfcd61572367373c8e08db739ba8a85e843b26-caregoty-en-010.webp",
        "",
        "Activate the checkboxes"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. To export from the segments list:

- Go to the **segment** **from which** you will be adding contacts, click _Export_, and select _To existing lists_ from the dropdown menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5107032cee942f7d9a799ba8e15616749312ecb19b1e444e7299922e6feedc68-caregoty-en-011.webp",
        "",
        "To existing lists"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Activate the checkboxes next to the **segment to which** you will add contacts and click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ea51dcb57bbeb4ebf5ee9bd0b88c41b51456f07a90df6b9cd88c4577a447407-caregoty-en-012.webp",
        "",
        "Activate the checkboxes"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Transferring Contacts via API

If you want to configure subscription category transmission via API, use:

- The subscriptions field in [v1/contact/subcribe](https://docs.yespo.io/reference/subscribecontact-1).
- The groups field in [v1/contact](https://docs.yespo.io/reference/addcontact-1).
- The groupNames field in [v1/contacts](https://docs.yespo.io/reference/contactsbulkupdate-1).

### Contact Management

You can exclude contacts from a category in the following ways:

- Exclude all contacts
- Delete individual contacts
- Delete a category from a contact card.

To delete all contacts from the category, click _Empty segment_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ad6535ed372fe4b5b67a49b6b6c05f3e9dc58db6fa63a35792c46dbb7dcf7893-caregoty-en-013.webp",
        "",
        "Empty segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To delete a single contact click the _trash icon_ on the right of the necessary contact.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/117aa0480b2b2f47b14ea481521f7e26f4ecab139a2f6f6d84aafcb8720a3e6a-caregoty-en-014.webp",
        "",
        "Delete from segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To remove a category from a contact card, go to it and click _Edit contact_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4293f4bbbcff4b8f7df0319713ba200b93d9360ef23978f3fb46a92560ccb854-caregoty-en-015.webp",
        "",
        "Edit contact"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Next, click _Edit contact subscription_ and uncheck the unnecessary categories.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/79089ecfe71e7b0935d41ea4f9bb3b02e3c87208490ea4d848177bd6eb4e697a-caregoty-en-016.gif",
        "",
        "Edit contact subscription"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Contacts that are excluded from the category remain in the account and will be available for other campaigns. The category itself is not deleted.

## Setting Up Unsubscription

You can set up unsubscription from all campaigns or from a certain category. A contact can unsubscribe:

- In the personal account on the site;
- In the email;
- On the unsubscribe page.

Subscription categories can be displayed on the unsubscribe page so that users can update their preferences on their own. To set up such a page, send a request to our support team.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/41ebdb1dcc6fa2f3fccd0a2f259bdb77cbcb68906e250018a477ac2c47561817-caregoty-en-018.webp",
        "",
        "Unsubscribe"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Creating Category-Based Campaign

You can use subscription categories to control the frequency of campaigns depending on their subscriber’s interests. Subscription categories apply to all communication channels. Subscription categories are specified when the message is created.

- In _Messages → Messages_, create a message or choose the existing one.
- Open its general settings, click _Select categories_, and select categories applicable to the message. You can select several categories. Below is an example of choosing categories for email.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/15e5d733c381d912ac7859ad094f1593c3b0d28bf7ac37b9d8b6e83eb992f1cf-caregoty-en-017.webp",
        "",
        "Select categories"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When scheduling the campaign, you can select any other segments to send it. 

The system will automatically calculate the contacts following the rules:

- The message is sent only to contacts from the selected segments who have subscribed to the corresponding subscription category.
- If the message isn’t assigned to any category, it will be sent to all contacts from selected segments.

[A campaign report](https://docs.yespo.io/docs/campaigns-analytics) will show the subscription categories applied to the message.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/323269ea82d241a9d07b79779c5d295f1d896e34b2a63a575f471decc4a50a60-categories_16.webp",
        "",
        "Report"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]