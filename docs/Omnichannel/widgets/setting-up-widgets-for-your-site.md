---
title: Setting up Widgets for Your Site
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Widgets for Your Site | Yespo Guide
  description: >-
    The guide details creating, customizing, and publishing widgets to boost
    interaction and gather contacts, covering appearance, placement, settings,
    and Google Analytics integration.
  robots: index
next:
  description: ''
---
RPlace different widget types on your site to improve visitor interaction and collect more contact data.

> 📘 Note
> 
> To publish widgets, install our script before the closing body tag on every website page. To get a script, go to _Site → Widgets_, click the _Get script_ button, and specify your site's domain.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/650dbbbdd769c8bec2337789f4688e71b110589452b04dd1846fcc9b478d44f9-01_new_widget_en.webp",
        null,
        "Get script"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


After installing the script, proceed to the widget creation. The listed website elements have similar settings and differ in minor nuances in preparation.

Select the widget type from the left menu or the drop-down list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/824e6bf4c576c4a3ddf5b8bb564226d5b5e139f853051541cac3759ee1d9a043-create-widget-en.webp",
        null,
        "Widget creation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Appearance

Start widget creation with initial settings.

### 1. Name / Type and Fields

1.1. Fill in the _Name_ field. The name is used for search within the system. Users won't see it.

1.2. For subscription forms and informers, select the type from the available options:

- **Inline** — embedded into any element of the webpage
- **Popup** — appears on top of other elements and disables the background. When open, it prevents page scrolling.
- **Floating box** — floats on top of other elements in the corner of the webpage or as a full-width bar without disturbing users’ reading experience.
- **Floating bar** — floats as a full-width bar without disturbing users’ reading experience. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e9e9d2ed0ddde4d09bf9bf12a5c0f7e06e2fec366c2dfec7c69fbd02aecee49-widget-type.webp",
        null,
        "Subscription forms options"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


1.3. For subscription forms, activate the widget’s input fields. 

1.4. Click the _Next_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0a8301f72974fe6dc6cdf70f1ad27a63e5300da37e99da250b6e9c4e45bb2b0a-widgets08.webp",
        null,
        "Input fields"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### 2. Style (skipped for launchers)

2.1. To create a widget based on your website style, select colours and style. The system will generate a widget based on your settings.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6511bebf386d3b625d974497b9547a5edb310491e7b0b3625c0aa0ae25fdb12e-widgets09.webp",
        null,
        "Colours and style"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2.2. Click _Next._

### 3. Select Appearance

Select the appearance style for the element. Each widget type has different options.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/550321db05c553e632573c89190074ba00bd0cad8c90154e65189009aa06218b-widgets10.gif",
        null,
        "Appearance style"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> Select the most appropriate option. You’ll be able to edit it as needed.

## Widget Editor

You have various tools to customize the widget’s style and elements.

### Basic Actions

The widget structure has 3 levels:

1. State.
2. Container (for some types of widgets).
3. Element.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3c66698d7cb72e46ab8d89548ce31194588650e5634e54d5c8779bc76aba858-widgets11.webp",
        null,
        "Widget structure"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


When you click the right mouse button on the widget element, the following basic actions become available:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3b9745b6af72a6dd4e07f022a0416f99558236f366583464685c97c8ac46ebbb-widgets12.webp",
        null,
        "Basic actions"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


1. Copy
2. Duplicate
3. Cut
4. Delete
5. Put behind all floating elements
6. Put in front of all floating images
7. To container

### Top Panel

The top panel menu contains buttons with the following functions:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0fb452baceb43c7d84e53738184d1d9b5e4c9724b009496b34cfee4eb90f53ad-widgets13.webp",
        null,
        "Top panel menu"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


1. _Undo/Redo._
2. _[Multilanguage](https://docs.yespo.io/docs/multilanguage-overview)_ settings:

- Form appearance is set up only in the version with the default language. Then it's automatically applied to other language versions.
- In other language versions, you can only change the text.
- The form is displayed in the site language, which is determined by the value of the `lang` attribute in the `html` tag. If the page code doesn't contain it, then by the browser language.
- Switch to the desktop version.

3. Switch to the desktop version.
4. Switch to the mobile version.
5. Widget preview.
6. Close without saving.
7. _Save_ button.

### Left Panel

On the left side of the screen, you can find the components of the widget you are creating. The editor works as a drag-n-drop constructor. If you need to add any element, left-click on it and drag it to the appropriate place of the widget.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ab2aa4793da5454207dbc3d0c6e27a44791828f43729f6d86f78e79f233b69cb-widgets14.gif",
        null,
        "Left panel settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Pay attention to the components NPS & Feedback described below — they will help you learn about customers' attitudes toward your product, brand, or company.

#### NPS/Feedback

The NPS (Net Promoter Score) component looks like a scale with scores from 0 to 10.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4ce96934a371dd4ada045dda284fb36621b48fecd8a19f10fade58cf46239aaf-NPS_5.png",
        "",
        "NPS"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The Feedback component is presented in four types (you can download your icon for each):

- 5 stars,
- 1-5 Rating,
- 3 Emojis,
- Like/Dislike.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/37e44195716110b9929716245b74351ce8918b5cdd9d05bdcb857a56d23129a4-NPS_6.png",
        "",
        "Feedback"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The NPS and Feedback settings are the same:

1. Select how to process data:
   - As a contact field (the _Checkbox_ type — for NPS, the _Text field_ type — for Feedback);
   - As an event parameter.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ae5126be6d3e72eb1797064ea645f34850d917de2191efd4a0bf467588207895-NPS_1.png",
        "",
        " Data processing"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The field for collecting NPS will contain a value from 1 to 10; in the Feedback field, depending on the type:

- 1-5 (“5 stars”, “1-5 Rating”)
- 1-3 (“3 Emojis”)
- Yes/No (“Like/Dislike”)

To use data processing as an event parameter, leave a request, after which our support will contact you. The steps for setting up data processing as a contact field are described below.

2. Set an action on click:
   - **Open widget page** — select one of the widget pages,
   - **Open widget page based on answer** — select a widget page for each respondent's satisfaction level.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c8d1a00b213d0be4c8f9a82828e9038a5cc9d834050737de448076f729fb8bf-NPS_2.png",
        "",
        "Action on click"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Determine whether the field is required.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4352ff94e7eb571ae1729b795477899f89b9cbf87876b4faf881692e7d095fef-NPS_4.png",
        "",
        "Required"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Customize the appearance of the component on the _Style_ tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1d5dea2c0f66a694ebce06e56d89409b83d5da407a9f32b2bf81f0e023acd182-NPS_3.png",
        "",
        "Style"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Right Panel

When you don't have any widget items selected, you will see design settings on the right side of the screen. These settings apply to the entire widget:

- Align inner elements
- Distance between elements
- Size

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b949e98bd68ef4ee5869b4fd1e94d26c39b2a414c92acc0d52cdc1284f21472e-widgets15.webp",
        null,
        "Right panel settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Background
- Stroke
- Shadow
- Round corners
- Spacing inside component
- Spacing around component
- Breakpoint

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0ba06c7b1271272d7f56d139e61781bd69d6fc665471ec59902492a5db8f89f4-widgets16.webp",
        null,
        "Right panel settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


\+ launcher settings: 

- Action on click
- Positioning
- Entry animation
- Loop animation

> 📘 Note
> 
> Settings marked with a lock icon sync parameters across pages. You can change the synchronization setting by clicking the icon and selecting the needed option.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/68d66e60e343723e7802fa104e37f32efba706a52638233474fd27abe0ab4805-widgets17.webp",
        null,
        "Synchronization setting"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


#### Editing widget elements

If you want to edit individual widget elements, just click on the desired element.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09e3e22a02c12db1054d91d7554c4ee3d29dc9ed340731e0badbdf9982a00afa-widgets18.webp",
        null,
        "Editing widget elements"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Text settings

To edit text style, click on the widget element with some text. The following panels will appear.

1. Text style options panel — on the editor's top.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5087ea8ae39f31817d3cac6263d9bd7c09f355ced9a45a3c289af4efe927b5ab-text-widget-set-01.webp",
        null,
        "Top settings panel"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> By default, widgets use the font set on your site as the primary font.

2. Text placement panel and changing the text background in a container — on the editor's right, with the following parameters:

- Size (by container width and content height) 
- Background
- Spacing inside component
- Spacing around component

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/25cda01e99f2e153997ee92d59ba3154b44f3ce7cecd110015acbc66a1d9a453-text-widget-set-02.webp",
        null,
        "Right settings panel"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#####  Image customization

To open image style settings, left-click on the image. You can upload your picture, choose a suitable one from the library of free photos and icons, or enter the URL of the image you want to embed. External URL allows you to keep the referenced sources up-to-date. For example, promo actions or products on a site.

> 📘 Note
> 
> Upload images in PNG, JPEG, SVG, GIF formats, up to 3 MB

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d3dbd9d827a418edc217934091aff9ad3f28d1f39a6dc4dbbcfe0f12695d2d3-image16.webp",
        null,
        "Image settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In addition to the standard settings, positioning customization is also available for images:

- Fill,
- Fit,
- Fit to image.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49b3ee6ebe384b08d745f9a8a39acbd596069d5efc98cbed0705190a954e88ef-widgets21.webp",
        null,
        "Standard images settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> You can edit the image directly in the editor when uploading (if it does not meet the requirements) or after uploading (the _Edit_ button). After editing, the image is saved in PNG format.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/706f4599da82fb3be2a02d5209edd8de3dfab2c78133287d91826b4e6765476e-untitled-1.webp",
        null,
        "Edit image"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


##### Slider settings

Drag the slider from the left-side panel and drop it into the widget’s template. _Set up slider_ and _Manage slides_ buttons will appear on the right-side panel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d1c0e8648769c945ac10e045e36b28db8520af916727c876f92dbe6d456a0a8-image13.webp",
        null,
        "Slider settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Set up navigation buttons, indication, slideshow animation, and general slider’s design in the _Slider setup_ window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bb105b84b29cabb8318525b227c8a325b8d06f613072e81c900156ddfddf98e4-image3.webp",
        null,
        "Slider setup"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Manage slides’ order, add, duplicate, or rename slides after clicking the _Mange slides_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4ed44fa65038bbffe81831562758987ce403588c493d655642715c5e9e7c9e2b-image12.webp",
        null,
        "Manage slides"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Also, you can add a slide by clicking on the + sign.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/98a1d4cff109769387419984ee397c2f5e7ecf74fc1370811dbc862fec3d696e-image7.webp",
        null,
        "Add slide"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


To change or edit an image, click on it in the template, after which it will appear in the right settings panel. Clicking on the image from the slider in the settings panel opens the editing and editing window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b1443284d87441bae21f578881c70f7689a0ad947278e302b1c9a243c2dad0f-image4.webp",
        null,
        "Editing image"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Use navigation buttons to switch between the slider’s images.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/05120d6d709b2b395c8b0ff4a515c423a4f874f76bcfe089db23cc855c83bdc6-image2.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


#### General tab

Click on the widget's element to see the _General_ tab with such settings:

- Action on click 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/720ce7c851ba36b4309f7fea4dc0868f9c88cce8508218058a9c1c3b330a7ef1-widgets22.webp",
        null,
        "Action on click"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Contact fields validation

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fd434ead781149e56f9310a52c5b9d2a851d86eb5d9dbe6aee484d136cfc9182-widgets23.webp",
        null,
        "Contact fields validation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Timer settings

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4213740093b54165bdc8aaa8814608267e5727f407229573470de5b1a30615ef-widgets24.webp",
        null,
        "Timer settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Video settings

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b2be3c98a797479c23babec61c8688df41cf95bb0c84b97b099452658379183e-image14.webp",
        null,
        "Video settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### Creating Multi-Step Widgets

Multi-step widgets are used to make the subscription process on a website more convenient and efficient. Their main purposes are:

1. **Increased Conversion:** Breaking up many fields into multiple steps makes the process less tedious for the user.
2. **Improved User Experience:** Presenting information incrementally seems more manageable than filling out a long form on a single page.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d17916c9f7c82ff00abc0d6363311a3b803211c6f1c3a8bd1166c59b43f162bb-widget.gif",
        null,
        "Multi-step widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To add a page to the widget, you can use the buttons

- _Add_ — to duplicate the current page,
- Three dots on the additional page to duplicate it (here you can also move the page left or right or delete it).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2ea51d184e75c5cf32d0447fa3e5cd41d22f9541beb046842275ff1f8ff154e-settings.webp",
        null,
        "Adding page"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> - Multi-step forms are available in all widget types except launchers.
> - A widget can have only one game component.
> - Only one widget component can write data to one contact field.
> - The maximum number of pages is 20.

## Widget Placement

1. The age gate takes the size of the screen and completely overlaps the pages of the site until the user confirms their age, so this widget has no placement settings.
2. The positioning of a launcher is configured in the appearance editing window.
3. To specify a positioning of a subscription form or informer, enter the CSS selector of the element you want to add a placement to. This tab appears after you have customized the widget's appearance and clicked the _Save_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/08cfb2562c94d842f6023dfff22f2e9c60a43626a0e152c433cf6413c248223a-widgets25.webp",
        null,
        "Widget placement tab"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Select where to add the widget relative to the found element:

- Before the element
- After the element
- Inside the element, last
- Inside the element, first
- Replace element

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a258b2fa24d028efdf39975c0504dac078420c36eb7090904868333b074eee0c-widgets26.webp",
        null,
        "Widget placement settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you are not ready to specify the widget placement, activate the _Add placement later_ switch.

5. Click _Done_. Initially, the form will be visible only to you; on the _Parameters_ tab, you can make it public.
6. Create additional placements as needed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/61ab048fdf19705a285d91134964ffa9539dca485f287a3369917d020c4ba0c7-add-placement.webp",
        null,
        "Add placement"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Widget Parameters

In the _Parameters_ tab, you can:

1. Edit the widget's appearance.
2. Edit the placement of the form or informer.
3. [Configure widget calling conditions](https://docs.yespo.io/docs/widget-calling).
4. [Configure the actions after the user has subscribed or clicked on the launcher](https://docs.yespo.io/docs/actions-after-form-submission).
5. Activate or deactivate the calculation of the revenue from the widget ([the settings are described in the instructions](https://docs.yespo.io/docs/how-set-revenue-campaign)).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e24a3095c99bd7e471453abe8de31f60f4a444dcf6ff2b07b7287ce1c7e59d17-Revenue_calculation.webp",
        null,
        "Revenue calculation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Widget Posting on the Website

1. Having saved all the settings, check how visitors will see the widget on the site — click on the _Test widget_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a7bd71cf221066e1e90aec8bca5c673d9a632cdef5705fe1c523cc57940fc0f-image5.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the link to your website and click _Open_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/615444fb1ebbe5e5af5bed5dec5f7705229669c310bdfd1d3eee6d29b4281271-image01.webp",
        null,
        "Enter the link"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. If all steps are successful, the widget will be displayed on your website according to the specified conditions.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1d31db6c8081dbe186ddc520923db18aee95f54a7297a696678f325723e4013a-widgets42.webp",
        null,
        "Widget display on the site"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. After testing the form, publish it by clicking on the _Published_ button, then click _Save_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/02780a281acd6e602a6199f8ddd4474122c3b8d70311312f45a443b7df61124b-image15.webp",
        null,
        ""
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Click the Unpublished button to stop displaying the form, then save the changes.

Also, you can specify the widget’s schedule by clicking on the _calendar_ icon.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f3364fcadb12e35399e6ca721c689807a8cba090ea505104a04dbe27a82feb5b-image1.webp",
        null,
        "Schedule"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The schedule includes the following settings:

- Start and end dates
- Custom days and time
- User timezone

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/93f09ddaf96d10fe86c568b4801de52cd762c015e88cd4344c99440350b7f119-image10.webp",
        null,
        "Schedule settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Widget statuses are displayed in the general list and in widget details:

- Published — for published widgets with a current or no scheduled period
- Unpublished
- Scheduled — the publication period is planned for the future
- Expired — the publication period has expired

## Widget Integrations

In the _Integration_ tab, you can configure sending widget actions and custom events to Google Analytics. Note that integration is only compatible with <a rel="nofollow" href="https://support.google.com/analytics/answer/10269537?hl=en" target="_blank"> Universal analytics script</a>, set directly on the website.

[Learn more about exporting data to Google Analytics >](https://docs.yespo.io/docs/integrating-widgets-with-ga)

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60fae2e394a46f4511c47b44923cf6cf03546c7a9a36146220ff9039b8a4b13d-widgets44.webp",
        null,
        "Widget integrations"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]