---
title: Widget Calling
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Widget Calling | Yespo Guide
  description: >-
    Yespo provides a wide range of options for flexible customization of widget
    display conditions so that they work as efficiently as possible in each
    situation.
  robots: index
next:
  description: ''
---
Yespo provides a wide range of options for flexible customization of widget display conditions so that they work as efficiently as possible in each situation. 

To set the widget display rules, click on the edit button in the corresponding section of the _Parameters_ tab:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09469d5a58567739e78e295eff60809edb52cac649dc04a722ea1dab69011434-sonditions-for-displaying-the-widget-01.webp",
        null,
        "Widget calling"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Widget Triggering Rule-based

The widget will appear only when the display rules listed below are met.

The following parameters are available:

### Display Frequency

- Do not limit
- Only once
- Once per session
- One time per some period

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8e7a5ce719b6649cbca4f04211b4831d535de321296ee70e15c3295124c2d8b1-sonditions-for-displaying-the-widget-02.webp",
        null,
        "Display frequency"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> When selecting the _Once per session_ option, the widget will be displayed throughout the current web session for the customer.

A user web session is an interactive period during which a user engages with your website, where the service script is installed.

During a session, a user may perform various actions, such as navigating between pages, interacting with content, submitting forms, or using specific features.

Examples of interactions:

- Cursor movements
- Clicks
- Keyboard pressings
- Taps
- Scrolls

A new session starts when a user enters a page where the service script is installed, and the user’s previous session has timed out or there was no previous session.

A session ends after 30 minutes of user inactivity.

Examples of user inactivity:

- A user does not interact for 30 minutes with the site where the service script is installed.
- A user closes all tabs with the site where the service script is installed and does not return to this site for at least 30 minutes.

### When to Display 

You can choose to display a widget immediately or when all or any of the following conditions are met:

- Spent some time on the page 
- Spent some time on the website
- Read the page by some percentage
- Visited some amount of pages
- Not active on the page for some time
- Left the cursor off the page

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/368d054feaf2e0d1bfe02123c88489d8f7afe4d32267b6f3aa7d060022c92ec4-Widget_Calling_3.webp",
        null,
        "When to display"
      ],
      "align": "center",
      "sizing": "50% "
    }
  ]
}
[/block]


### When to Stop Displaying

- After a certain amount of seconds, in case of no interaction with the widget (the condition is canceled when a user hovers over the widget)
- After closing a certain amount of times

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ffb87b979b025e144588f94ce0081d8290683a83e72616df400e832f51613d4f-Widget_Calling_4.webp",
        null,
        "When to stop displaying"
      ],
      "align": "center",
      "sizing": "50% "
    }
  ]
}
[/block]


- After subscription (from any or this widget): do not show the widget to the contacts with the subscribed status.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/75851d474425b3f1a790d047efb5ec2736b7a91ab45c82f4c5b0e81dfb38f4b7-Widget_Calling_5.webp",
        null,
        "When to stop displaying"
      ],
      "align": "center",
      "sizing": "50% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The subscribed status is checked only for the contacts who subscribed using their email. Other channels are not taken into account.

Our system identifies the subscription status of a contact based on the contact ID. When a contact visits your site, the script requests the system to check the subscription status. This request includes the contact ID, which is stored on the site as the result of the following events:

- A contact subscribed using any or this particular widget.
- A contact clicked a link in an email message redirecting to the site where our script is installed. The contact ID is retrieved from the URL’s UTM tags.
- A contact subscribed to the web push notification.

You can select the _After subscription from any widget_ option for general subscription types, for example, weekly digests. This widget will not be displayed if a contact has already signed up using any widget or channel.

If you select the _After subscription from this widget_ option, the widget will not be displayed only in case the contact has already subscribed using this widget.  

Note  
If a contact has any status other than Active, the widget will be shown to that contact when the After subscription condition is enabled.

### Annoyance Safeguard

Set annoyance safeguard when several floating widgets must be displayed on one screen based on their triggering rules. [See details >](https://docs.yespo.io/docs/using-annoyance-safeguard)

### To Whom

#### Visitors

You can show your widget to: 

- All visitors
- New
- Returning

> 📘 Note
> 
> The visitors are identified as new when:
> 
> - They have not visited the site after the installation of our script on it.
> - They previously visited the site in incognito mode.
> - After the past visits, they cleared the cache, cookies, and local data.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/920a061fcb7a419ed4fac6a778e2f31ed7083ff7be0dae7a330f25f9616ad286-image001.webp",
        "Enabling the New visitors option",
        "Enabling the New visitors option"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Segment

You can display a widget only to contacts included into a specific segment.

To add a segment to the To whom condition:

1. Click the _Select a segment_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/83ba957f938595db2910fd4ce9066fc7f55cc4fbc31e2deaf6135f53aa002416-image002.webp",
        null,
        "Select a segment button"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Select the segment in the _Select a segment to display the widget_ window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5b3caf65f962c07797889947f4b11e4c38d41e45896eaa210a107a5828a9d6c3-image003.webp",
        null,
        "Selecting a segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


You can add both lists and dynamic segments. 

The widget will be displayed to the identified and unidentified site visitors if they are included into the segment. The system uses the following information to identify whether a site visitor is included into the segment:

- Cookies: For unidentified contacts if the segment contains only the Web Tracking conditions.
- Contact ID: For identified contacts.

The identified contacts are:

- Those who subscribed using any or this particular widget.
- Those who click a link in an email message redirect to the site where our script is installed. 
- Those who subscribed to the web push notifications.

_Segment preview_ is available for a dynamic segment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/205c96d3842435560b3d72ed266454c843e2409307de77da0d92bcbc929e4831-image004.webp",
        null,
        "Segment preview"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Device type

The widget can be displayed on:

- All device types.
- Desktop. 
- Mobile.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9ed46e4e5739d8a6d43502d9ade357c1e4b543d91f039e07b002ca7c3dd6f64a-image005.webp",
        null,
        "Selecting the device type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### On Pages

Similar to [dynamic segments builder](https://docs.yespo.io/docs/how-add-dynamic-segment), you can choose pages where to display or not to display the widget. Use this widget-calling rule to show promotions depending on products and their categories, the site’s sections, etc.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/38b22282952dc894f2dc86960277b86ef2485331b6a85a8c541ee4845614eba4-on_pages.webp",
        null,
        "On pages"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The UTM tag is considered when visiting the page within one session. When revisiting the page without the tag, the widget will still be shown if a user previously followed a link with the tag within one session. If you want the widget to be displayed only on a page with a specific tag, set the display rules for this URL.

### In Locations

Read [Setting Up Locations for the Widget Calling Rules](https://docs.yespo.io/docs/setting-up-locations-for-the-widget-calling-rules) to learn details.

## By Click on Launcher

The launcher calls the widget (Subscription form/Informer types) regardless of the widget display conditions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c6383d637f4f6b10ae2bed06ac9a7047c373b00c771cea155b6c9519c12f1ab9-Widget_Calling_11.webp",
        null,
        "By click on launcher"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Rules for forms that showed by clicking on a launcher:

- Show each time
- Immediately
- Stop to display forever after subscription from any widget
- Show on all types of devices
- On any pages
- Show in all countries

## On Clicking an HTML Element

Specify one or more CSS selectors of the call elements.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8e10a8bbe2227bc1daca14b0c7ed2b9e867f189eb58e4cbab9fcaa297beb9523-selector.webp",
        null,
        "Specify the CSS selector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To learn about finding an element and copying its CSS selector, click on the _How to find a CSS selector_ link.

> 📘 Note
> 
> Our script checks for the presence of any specified HTML element (including the ones with the _hidden_ status) when the web page starts loading. The system will not show the widget if the element appears after some time.

## API Based

Show a widget by clicking on a page element or via JavaScript. Copy the JS function and add it to your site's code to display the widget on some extra condition.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/becdf600c0334e360119aac9ecff901c8ebc5bf06732fccf7f23032f9e9286f0-api-based.png",
        null,
        "API based"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Control through other conditions is unavailable when controlling a widget’s display using API.