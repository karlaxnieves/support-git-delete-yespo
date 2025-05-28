---
title: Integrating with Google BigQuery
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Integration with Google BigQuery | Yespo Guide
  description: >-
    Follow the steps described in this article to integrate your BigQuery
    account with Yespo
  robots: index
next:
  description: ''
---
To integrate BigQuery with your Yespo account:

- Register your account at <a rel="nofollow" href="https://cloud.google.com/" target="_blank">Google Cloud Platform</a>,
- Get a project key,
- Create tables in Google BigQuery for importing data **to Yespo**; tables with data **from Yespo** will be created automatically after the first export,
- Create the Yespo connector.

If you already have a project key and BigQuery tables with data for Yespo, you can go directly to the [connector settings](https://docs.yespo.io/docs/google-bigquery-integration#setting-up-bigquery-connector).

## Creating a Project Key

1\. Create a <a rel="nofollow" href="https://cloud.google.com/" target="_blank">Google Cloud Platform</a> account.

2\. Select a project → _APIs & Services → Credentials_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/35700109b3f8e1605392e4eaf4e328a12c63e2b665df6c5abccda15126a174d1-bq-1.webp",
        "Credentials",
        "Credentials"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3\. Click _Create credentials → Service account_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/06de9720113bc51537c4d38258e5c6984365764680ee31c44c77f13492d48f48-bq-2.webp",
        "Service account",
        "Service account"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4\. Enter a service account name and click the _Create and continue_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e06d76e50f444ccea5ddd32c7adfc6620192593285279635c68e63216b6af732-bq-3.webp",
        "Create and continue",
        "Create and continue"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5\. Select _BigQuery Admin_ role, click _Continue_ → _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8291c2edf731225c202b0bba9606f4b45b958743152d4ac378f8550c4cfbc8da-bq-4.webp",
        "BigQuery Admin",
        "BigQuery Admin"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6\. Click the link _Manage service accounts_ on the main page of the _Credentials_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ded87e2dddd5547a319d5876b9a079c696905efb1c80bc7d05c26c2e2ce79837-bq-5.webp",
        "Manage service accounts",
        "Manage service accounts"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


7\. Click on the three dots opposite created account and select the option _Manage keys_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/613bca51d9738995b1fcef291466a550d2272847101d11614384af8993e0be2a-bq-6.webp",
        "Manage keys",
        "Manage keys"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


8\. Click on the _Add key_ button and select _Create new key_ option in _Keys_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bd891b394f7c602043081de69e92d37c4f2da5497e406886ab3d630c6001fa8a-bq-7.webp",
        "Create key",
        "Create key"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


9\. Select JSON key type and click _Create_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c1420e4ba75d8c7f5144e938dbc3a517492c2f1525358417e5c02c4ccc674fdc-bq-8.webp",
        "Select JSON key type",
        "Select JSON key type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


10\. The browser will automatically download the key to the download folder.

## Setting up BigQuery Connector

Go to your profile → _Settings_ → _Connectors_ → and select _Connect BigQuery_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d123c1614c269c69821ba9e7692bcbc0c87fac32f7f1f10db495a6d0f306c150-image6.webp",
        "Connect BigQuerry",
        "Connect BigQuerry"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Create connector:

1\. Fill in the _Name_ field.  
2\. Upload the key file.  
3\. Click _Validate connection_ to test whether the authorization data is correct. You will see the notification if the connection is successful or not. If the connection fails, check the entered data and contact your system administrator if needed.  
4\. Set unique contact field: select a table column that contains a unique contact key and Yespo's unique contact key. They should match.  
5\. Click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d26dcc00b643531205aadad971a8092d89955c3cf74735321c61b055af1ba7f-image9.webp",
        "Setting up BigQuery Connector",
        "Setting up BigQuery Connector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You will see created connector in _Settings_ → _Connectors_. Click the tab with its name to edit the connector’s parameters.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2726d89eb4b06f2a14713f9f160c95f9ca82fc2ee35f8ce7ddd1feb17c763ac1-bq-12.webp",
        "Setting up BigQuery Connector",
        "Setting up BigQuery Connector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Now, you can use it for [exporting Yespo’s data](https://docs.yespo.io/docs/exporting-data-bigquery-tables) and for [importing data from BigQuery](https://docs.yespo.io/docs/importing-data-bigquery-tables).