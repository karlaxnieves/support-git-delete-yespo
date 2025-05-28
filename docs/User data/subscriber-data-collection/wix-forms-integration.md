---
title: Integration with Wix Forms
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Integration with Wix Forms | Yespo Guide
  description: >-
    This is a guideline for integration with contact collection forms published
    on sites built on Wix.
  robots: index
next:
  description: ''
---
This is a guideline for integration with contact collection forms published on sites built on Wix.

Before getting started with integration, you need to:

- [Create additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) in the system. They should be similar to the fields of the form.

## Step 1. Form Creation

1. Go to _Site → Integrated forms_ and click the _New integrated form_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e5cd13320315b5da6f441498b8ac2e221cc4d411cd2915a1edda88c21406cd5b-Integrated-forms-05-07-2025_11_31_AM.png",
        null,
        "New integrated form"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the form name and select _Wix_ in Services. Click _Next_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dae921890246895862d8759458f491ae2b1087a089176bbf78b340faf134b07f-Subscription-form-05-07-2025_10_25_AM.png",
        "Wix (2).png",
        "Select Wix"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. In _Add contacts to_, enable a segment where the contacts who fill in the form will be added.

- For the _New segment_, create a segment.
- For the _Existing segment_, select a segment from the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d20fd93-Wix_3.png",
        "Wix (3).png",
        "Select segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Select what contacts to collect:

- **New**. Select to collect new contacts. Further, you will need to set Double Opt-In and select a confirmation email that will be sent to new subscribers automatically.
- **All**. Select to collect both new and existing contacts. For new contacts, you will need to set Double Opt-In and select a confirmation email that will be sent to new subscribers automatically. Existing contacts will not be sent a confirmation email.
- **Additional data only for existing contacts**. New contacts will not be able to subscribe through this form.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/29faa15-Wix_4.png",
        "Wix (4).png",
        "Select what contacts to collect"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Click _Next_.

## Step 2. Integration with Wix

1. In _Wix websites_, enter your site URL.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/39589eb-Wix_5.png",
        "Wix (5).png",
        "Enter your site URL"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Copy the Webhook URL and enter it in your Wix account as described below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e49a7305fccf6efb0cc0007f633de0dd6d91decd6883092855af7f91e8585e6e-Subscription-form-05-07-2025_01_35_PM.png",
        "Wix (6).png",
        "Copy the webhook"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- In your Wix account, go to_ Automations → New Automation_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/58704c4fc6fa7a4f6a21133121ae9c14d415c1442a44d388f7cbeb772eace887-image4.png",
        "Wix (7).png",
        "Create an Automation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Select _Start from Scratch_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/272a2a4d5797ff47f5df2e853628d4ea5bf0c4f476e7f0489a67df94805bf58e-image6.png",
        "Wix (8).png",
        "Start from Scratch"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Select _Wix Forms → Forms submitted_ in trigger settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bdd738961071f5ab0aff984e732261aefe68911ca6173aeae4f7110d3de0d16f-image9.png",
        "Wix (9).png",
        "Select the form"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Select any or specific forms.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f0d6cd50049987ab534f268abc60895086b86fda94686020cf88023cf48d2e71-image7.png",
        "",
        "Select forms"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Click + to add a step.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4a9c1604830284fdd7db7cbe34450e0a54f39f6cdc552bdccae75bce37077520-image8.png",
        "Wix (10).png",
        "Add a step"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Select _Action_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cb1b12080c04d82826b7bea78b9c9a1c5eb9baf5a55b1bb7b71e2a390e309cb2-image1.png",
        "",
        "Action"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Select the action type — _Send HTTP request_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/700768324c3d47d8d022fa6b1ebdf1947c8f9aee041b3305816fd4ae19ba7090-image5.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Paste the Yespo Webhook URL and click _Apply_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e76eb3eb756bce62e6855c48483fd1bb6f703c2b67ea98a0aac2fa1649f6c874-image3.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Step 3. Field Mapping

1. Fill out the form and send the submitted data.
2. Click _Show data from Wix_.
3. Map it to the contact field.
4. Click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0633419315d0f68cd26d0eb2c734a12390347b70444bfdc39ba646b0aea21634-image1.png",
        "Wix (11).png",
        "Show data from Wix"
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]


## Step 4. Setting Parameters

Check and edit form parameters and actions after subscription on the _Parameters_ tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/10eb319-Wix_12.png",
        "Wix (12).png",
        "Parameters tab"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When everything is set and checked, click _Save_. The created form will appear in the general forms' list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b6885431f5b61b425f3899ea34e0ff1eeac2bffb8c0fd3f6d766a6044befcf17-Integrated-forms-05-07-2025_11_29_AM.png",
        null,
        "Created form"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Here you can see the statistics on requests and the last update. To delete the form, click the three dots icon on the right.

> 📘 Note
> 
> Requests display how many times the form has been filled and not the number of new contacts. One person can fill the form more than one time or fill the form but not subscribe.