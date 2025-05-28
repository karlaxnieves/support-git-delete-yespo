---
title: API Keys
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## API Key Usage

Create an API key to set up integration with your Yespo account.

Yespo API supports [Basic HTTP Access Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) method using an API key.

The key provides access to the data in your Yespo account, so it must be protected from unauthorized access.

To access your account:

- enter any value in _Username_.
- enter your API key in _Password_.

An example of authorization with an API key for Postman:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a7d7b79-postman.png",
        "postman.png",
        1894
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]


## Creating a Key

To generate an API key:

1. Go to _your profile_ → _Settings_ → _API_.

2. Click _New key_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1df7df9c775d63a099dbc1713fc2327c43a5278f8abf900d4fa47e6f39655d57-api-key-01.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. In _Description_, enter the name of an application or a site, where you want to use the key to access your Yespo account. 

4. Open the dropdown menu and select the access rights for the API key.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7e42b47-download_8.png",
        "download (8).png",
        ""
      ],
      "align": "center",
      "sizing": "80"
    }
  ]
}
[/block]


> ❗️ 
> 
> The access rules apply to all method versions (/v1, / v2, etc.) unless otherwise specified.

5. To set up several integrations, create a key for each. You can create several keys with different access rights for the same account.

You can find all the API keys in the API tab. Each key shows the following information:

A. Key number  
B. Who created  
C. Creation date and time  
D. Accesses rights  
E. Key description  
F. Key status (enabled/disabled)

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d045059483718087be77791752205d451cc75977783efc138bcac38befda21b3-api-key-02.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Access Rights

Access to Yespo resources through an API key is set up at the key creation stage.

You can give full access to all Yespo API resources and methods by choosing _Full access to API_. Or you can limit access rights by choosing:

- “Access to events”
- “Access to events and contacts”
- “Access to events and contacts” (adding/updating)
- "Access to messages"

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46c1a9b-apikeys4.png",
        "apikeys4.png",
        1406
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Copying a Key

To copy your key:

- Point to your key number to display the _Copy_ icon.
- Click _Copy_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a718471-APikey1.png",
        "APikey1.png",
        1764
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Enabling or Disabling a Key

When you create your key, it becomes enabled by default.

To disable your key:

1. Click the _toggle switch_ on the right side of your key.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1e943c-small-03_new_api_keys_en.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click _yes_ on the pop-up window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fe8921d-apikey2.png",
        "apikey2.png",
        1012
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Your key becomes disabled. The system blocks access to the API for this key. 

> ❗️ 
> 
> If you don’t use a key for 90 days, it is disabled automatically.

## Editing a Key

To edit your key:

1. Click the _Options_ menu (...) on the right.
2. Select _Edit_ from the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d2d95a2-apikeys.png",
        "apikeys.png",
        1664
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Edit your description and/or access rights and click _Save_.  
   Your key settings update.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a247625-apikeys3.png",
        "apikeys3.png",
        1646
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Deleting a Key

If a key is compromised, you can permanently delete it and create a new one for that application or site.

To delete a key:

1. Click the _Options_ menu (...) on the right.
2. Select _Delete_ from the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce54e05-apikeys6.png",
        "apikeys6.png",
        804
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _yes_ to confirm.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/754438d-apikey2.png",
        "apikey2.png",
        1012
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The deleted key is removed from the list of API keys.

## API Key Security

The API keys provide access to all the data of your Yespo account. Follow the rules below when working with API keys:

> ❗️ Important
> 
> **Do's**:
> 
> - Keep your API keys secure, like passwords.
> - Periodically check you account for suspicious activity.
> 
> **Don'ts**:
> 
> - Do not show your API key in screenshots or videos. Remove it completely.
> - Do not email your API key; it could fall into the wrong hands.
> - Do not wait if your key is misused. Disable it and create a new one.