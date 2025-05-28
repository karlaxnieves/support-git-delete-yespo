---
title: Creating Pop-ups via Google Tag Manager or WordPress
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating Pop-ups via Google Tag Manager or WordPress | Yespo Guide
  description: >-
    The document provides instructions for creating popups in Yespo using Google
    Tag Manager or WordPress, detailing steps for adding scripts via GTM,
    WordPress plugins, or manually in WordPress files.
  robots: index
next:
  description: ''
---
You can simplify the process of creating popups in Yespo using <a rel="nofollow" href="https://tagmanager.google.com/ " target="_blank"> Google Tag Manager</a> or <a rel="nofollow" href="https://wordpress.com/" target="_blank"> WordPress</a>. See the instructions for using these systems below.

## Placing a Popup via GTM

Add the Yespo script to your site using <a rel="nofollow" href="https://support.google.com/tagmanager/answer/6102821?hl=en" target="_blank"> GTM</a>. For this: 

1. In your Yespo account, go to _Site → Widgets_. Get the script and copy it.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b88d8581041f724f062d81e63c07c50161badf4d0d5becafa0ca8339dd8be026-Pop-ups_via_Google_Tag_Manager.webp",
        null,
        "Get the script"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click the _New_ button in the _Tags_ section of your GTM account.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6991ec5e359b6ebfdfb078b55b00ed912f693d2ac3843d0ec31cd35228eada57-image11.webp",
        null,
        "New Tag"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Name the tag and click on the _Tag Configuration_ field.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/486418bb79f24b43d911c423c84864c52888af8c19b5f145bf22046063fcc009-image10.webp",
        null,
        "Tag Configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Select the tag type _Custom HTML_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6764c09d527e2d6a139e5c1be002d4a12d21fa898eab61a1e378530dd51d57dd-image1.webp",
        null,
        "Custom HTML"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Paste the script obtained in Yespo into the _HTML_ field. Save changes.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ad043b46dbe89f44f58a67beb3077e9b66643a9446bdd118c73083f7a2799716-google-tag-manager.webp",
        null,
        "Paste the script"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. A dialog box will appear. Click _Add Trigger_. You can also click _Activate_ in the tag settings window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/81980d4f101caab47d07f71b588d3160b9a39b93d17f9103f9dc1ae604f0a5ab-image3.webp",
        null,
        "Add Trigger"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


7. Select the type of trigger, for example — _All Pages_, to place a popup on all site pages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/02ed2c255010e0814a689a144c9d7cc91bcb7bb950188089689a29748626d44c-image5.webp",
        null,
        "Trigger type"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The tag and activator you created are ready to publish.

## Placing a Popup via WordPress

Use one of the three ways to add a script to a WordPress site (getting the script is described in the first step of the instructions for placing a popup window with GTM).

### 1. Using Insert Headers and Footers Plugin

This plugin allows you to install the Yespo script on the entire WordPress site. For this:

1. Follow<a rel="nofollow" href="https://wordpress.org/plugins/insert-headers-and-footers/" target="_blank"> the link</a> and download the plugin.
2. Activate the downloaded file and install the plugin according to the <a rel="nofollow" href="https://www.wpbeginner.com/beginners-guide/step-by-step-guide-to-install-a-wordpress-plugin-for-beginners/" target="_blank"> instructions</a>.
3. To activate the plugin, go to _Insert Headers and Footers_ → _Settings_ and insert the Yespo script in one of the fields:

- Script in Header (recommended)
- Script in Footer

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e62267dd445af52178455d01168f0581201d3d64dadb2f2867ecb05fd98c4ac5-insert_headers_footers_settings.webp",
        null,
        "Headers and Footers"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Save_.

The plugin will automatically upload the code to each page of your site.

### 2. Add the Script via Code Manually

You can add the script to WordPress files yourself (see <a rel="nofollow" href="https://www.wpbeginner.com/beginners-guide/beginners-guide-to-pasting-snippets-from-the-web-into-wordpress/" target="_blank"> instructions</a>).

The script can be placed in the following site locations:

- Header
- A certain post
- A certain page
- Footer

#### Add a script to the site header

Paste the script into the <a rel="nofollow" href="https://www.wpbeginner.com/glossary/functions-php/" target="_blank"> functions.php</a> file in the <a rel="nofollow" href="https://www.wpbeginner.com/beginners-guide/what-why-and-how-tos-of-creating-a-site-specific-wordpress-plugin/" target="_blank"> plugin for the site</a>, or use the <a rel="nofollow" href="https://www.wpbeginner.com/plugins/how-to-easily-add-custom-code-in-wordpress-without-breaking-your-site/" target="_blank"> plugin for code snippets</a>.

An example:

```javascript
function wpb_hook_javascript() {
   ?>
       <script>
         // insert your javascript code here
       </script>
   <?php
}
add_action('wp_head', 'wpb_hook_javascript');
```

#### Add a script to a specific post

To add a plugin to one of the posts on WordPress, insert conditional logic into the code.

An example:

```javascript
function wpb_hook_javascript() {
 if (is_single ('5')) {
   ?>
       <script type="text/javascript">
         // insert your javascript code here
       </script>
   <?php
 }
}
add_action('wp_head', 'wpb_hook_javascript');
```

This code executes the script only if the post has the identifier 5. You must insert 5 as your post ID.

The post ID is the number after _post =_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c85f953ae8597790f5dec20f64986a5076b82c28157c539bf82234335b05bd3f-image12.webp",
        null,
        "Post ID"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


#### Add a script to a specific page

To add a script to a WordPress page, add conditional logic to the code.

An example:

```javascript
function wpb_hook_javascript() {
 if (is_page ('10')) {
   ?>
       <script type="text/javascript">
         // insert your javascript code here
       </script>
   <?php
 }
}
add_action('wp_head', 'wpb_hook_javascript');
```

This code executes the script only if the page has the ID _10_.

#### Add a script to the site footer

Add the following code snippet to your website, so the script runs in the footer.

An example:

```javascript
function wpb_hook_javascript_footer() {
 ?>
    <script>
         // insert your javascript code here
       </script>
   <?php
}
add_action('wp_footer', 'wpb_hook_javascript_footer');
```

This code is attached to wp\_footer instead of wp\_head.

### 3. Adding a Script Inside Posts or Pages Using a Plugin

Use the plugin to select a place to embed the script in the site content.

1. Download the <a rel="nofollow" href="https://wordpress.org/plugins/simple-embed-code/" target="_blank"> Code Embed</a> plugin.
2. Install and activate the plugin in the plugin menu in WordPress controls. See the <a rel="nofollow" href="https://www.wpbeginner.com/beginners-guide/step-by-step-guide-to-install-a-wordpress-plugin-for-beginners/" target="_blank"> instructions</a> for details.
3. In the WordPress Post Editor, click on the context menu icon (three vertical dots) in the upper right corner of the screen and select _Options_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b8eaf931e11781e9d5b50d313b1202dc876c60d03f46437bf770907a9c47c85c-post_editor_menu.webp",
        null,
        "Options"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. In the dialog box, check the _Custom fields_ option in the _Advanced panel's_ section.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/481fccce40fa3dfe18181ed666f3a54729a26b45f87bebd9eef46811260b4faa-custom_fields_checkbox.webp",
        null,
        "Custom fields"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


5. Click _Enter new_ In the _Custom Fields_ window under the content editor.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e0e6c294252a174966ac7a5271780aaf3776407f8ce5ffccd369424f7ac8e813-image9.webp",
        null,
        "Enter new"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Enter the name of the custom field, which should start with the prefix _CODE_, and insert the script in the _Value_ field.
7. Click _Add Custom Field_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/051133f32d47a19c837b51dc51c9d8e9b47d95b163c088b5eafacb3c717b5644-image8.webp",
        null,
        "Add Custom Field"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Use this custom field to embed script code in any post or page position. To do this, add the following embed code anywhere on your content:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/67762018d51328517fdb7638ffecacce37c790e63fed90fe2cc6c9d0fe3abd56-code.webp",
        null,
        "Code"
      ],
      "align": "center",
      "sizing": "40% "
    }
  ]
}
[/block]


Then click _Update_ or _Publish_ to run the script code on the page or post.