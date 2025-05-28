---
title: Collecting Contact Data from Campaigns
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Create Campaigns to Collect Additional Contact Data | Yespo Guide
  description: >-
    Create campaigns to collect contact data and use it to communicate with
    customers in different channels. Build dynamic segments based on contact
    data or send emails with Velocity code.
  robots: index
next:
  description: ''
---
If you use several channels for communication with customers, you can invite subscribers of one channel to join you in another channel. For example, ask email subscribers to subscribe to your web push notifications or ask the app users to subscribe to your email. To do so, you can build segments based on contact data or use Velocity in emails.

## Sending Bulk Campaigns to Dynamic Segments

Let’s create an email campaign that offers email subscribers to subscribe to web push notifications. You need to [create a dynamic segment](https://docs.yespo.io/docs/how-add-dynamic-segment) with conditions based on a channel.

> 📘 Note
> 
> You can choose any channels instead of Email and Web Push, depending on those you use for communication with customers.

1. Go to _Contacts → Segments_, click _Add segment_ and select _Dynamic_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/86fb4c44d18d252cbf8b1477c23942732a8d7f77fd9edaf51c58a94c5c36f37a-creating_conditional_segment_en.webp",
        "Create a new dynamic segment",
        "Create a new dynamic segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the segment name and optionally purpose and tags.
3. In _Include_, click _Add condition_. Go to _Channels → Email domain_ and select _All contacts with email_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d0307c0a5d2be641a761fc940ff9e9a039aea2df733b6b7ab3f987e31f913022-collecting-contact-data-from-campaigns-001.webp",
        "Include segment conditions",
        "How to include segment conditions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. In _Exclude_, click _Add condition_. Go to _Channels_, select the domain of a website you use for the web push subscriptions, and select _All contacts with sitename.com_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0462a6d4522fcac2053df4a3f8b3863555fb0f58dc9b2501a9e414ba739510c9-collecting-contact-data-from-campaigns-005.webp",
        "Exclude segment conditions",
        "How to exclude segment conditions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Your segment have to look as follows. Click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58d72bf7c0d1c5ea2d80786e7c7366168352c3c3f682a9c0d9ba98d33f4a263c-collecting-contact-data-from-campaigns-004.webp",
        "How a ready segment looks",
        "Ready segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Create an email offering to subscribe to your web push notifications and send it to this segment. Embed the link to your site. When subscribers click it, they will be navigated to your site, where they can subscribe using a regular request prompt.

## Triggered Campaign

### Option 1. Send one email with Velocity code.

1. Create an email with an invitation that will only display to email subscribers without a push token. The invitation should be created as a separate block.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9fca2d833a10366cf0920efaa3d92749ce3c05102ba34e35bac10e247b52cc87-collecting-contact-data-from-campaigns-003.webp",
        "Template with a subscription invitation",
        "Template with a subscription invitation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Left-click the block and click _Code editor_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1617ad091ac6c9cebfc12ebbd13eff7b47491bff76e378230d185a339617942e-collecting-contact-data-from-campaigns-002.webp",
        "Code editor",
        "Code editor"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Add before the table:

```Text Apache
<!--#set($filtered = [])
        #foreach($item in $data.get('mediaList'))
        #if($item.get('mediaType') == 'WEB_PUSH')
        $!filtered.add($!item)
        #end#end
        #if($filtered == [])-->
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/01f12531d9f4a612f0174fff1e2ab66c6b86af47af180786d193f4c43d46a12c-image1.webp",
        "Where to add code before the table",
        "Code before the table"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Add the following code at the end of the table before closing `td`:

```Text Apache
<!--#end-->
```

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d49432e3fba2a907bec1c7b37a824eb493f37ae5abc2d059dcbd01b71b042f71-image2.webp",
        "Where to add code after the table",
        "Code after the table"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Go to _Automation → Workflows_ and create a new workflow that consists of the following blocks:

- Start;
- Task Get contact;
- Email. Select the created email in _Message_;
- End.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/62d73751a249983b6c4eb2898d0528cc516fa375b2459f35bf7edeb9e127033a-collecting-contact-data-from-campaigns-01.webp",
        "Workflow example",
        "Workflow example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


This way, all subscribers receive the email, but the block with the invitation is visible only to subscribers without tokens.

> 📘 Note
> 
> To collect web push tokens, use only the task Get contact; otherwise, the Velocity block won't display.

### Option 2. Send different emails.

You can either create two different emails: one for email subscribers with a token and another for subscribers without a token, or create one email and then schedule an extra campaign for the later segment.

1. Create a dynamic segment as explained above.
2. Create a workflow including the following blocks:

- Start;
- Included in segment? Select the created segment. If the subscriber matches the segment condition that is has the token they will be excluded from the campaign;
- Email. Select the email with an invitation;
- End.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dc4e02284cb0be57f2899486b54f92f4ce2b55972af9821ade082b28e0c7c770-collecting-contact-data-from-campaigns-02.webp",
        "Workflow example",
        "Workflow example"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Sending Bulk Campaigns with Velocity Code to Collect Phone Numbers

To engage users who have not provided their phone number, you can send an email with a block asking for the number and permission to send SMS. Add the corresponding Velocity code to the email code, and it will hide the permission block for users who already receive your SMS.

In the block code, add before the table:

```Text Apache
<!-- %SMS% -->
<!-- #set($sms = $data.get('SMS')) -->
<!-- #if(!$sms) -->
```

Add the following code at the end of the table before closing td:

```Text Apache
<!--#end-->
```

> 📘 Note
> 
> This option can only be used to collect phone numbers.