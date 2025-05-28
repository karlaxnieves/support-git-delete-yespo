---
title: Getting and Installing Web Tracking Script
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Getting and Installing Web Tracking Script | Yespo Guide
  description: >-
    Add web tracking to your website and monitor user behavior, most viewed
    categories and products, clicks and items added to cart. Use the data to
    segment your contact base and send personalized offers tailored to each
    customer.
  robots: index
next:
  description: ''
---
To get the web tracking script, go to your account settings → *Web tracking* tab, and click *Start the web tracking*.

<Image align="center" width="80% " src="https://files.readme.io/b28ed428075d88b5c6b52f83063104a5f02231c428ebb9885e61989af162e611-w-3.webp" />

## Getting and Installing Script

1. Enter your domain name and click *Get script*.

> 📘 Note
>
> The script works for second-level domains and subdomains (`mysite.com`, `blog.mysite.com`)

<Image align="center" width="80% " src="https://files.readme.io/6d3ac4fa5e74399cbbb815744f7b06de41ae3c6ae5f0f80711ce56eaa67c7ea2-w-7.webp" />

2. Copy the script and add it to the page code before the closing `</body>` tag on every website page.

<Image align="center" width="80% " src="https://files.readme.io/2f6efd402cbfb4850dec82f08c4e9ff7ef3753eba65ecae12084ec205e1e0722-w-2.webp" />

> 📘 Important
>
> Install the script on both desktop and mobile versions of your website.

## Checking Script Status

After installing the script, click the *Check status* button.

<Image align="center" width="80% " src="https://files.readme.io/dc5c185f4c943eca050546fd3743879e2e614fac12a178f38f1b2ad18f6ab2f5-Untitled-1.webp" />

If there are any problems, you will see a warning message with a hint.

<Image align="center" width="80% " src="https://files.readme.io/f898296fbdf9bf3c8e92c58243d1c305a1c92d0e7b2fb2ff26464f962bfcc07f-w-1.webp" />

When the installation is completed successfully, the status will change.

<Image align="center" width="80% " src="https://files.readme.io/a5e389c73a52323f084873c04d0900da5367964de751a05b7612106b550ef8f1-w-6.webp" />

Now you can return to the main web tracking page, where user activity on your site is tracked (*Settings → Web tracking*).

<Image align="center" width="80% " src="https://files.readme.io/ce27ef31dfce043d77f4d42015179b5570182b540481bfe259a890579a1fd09b-w-5.webp" />

Here, you can see the number of page views yesterday and today and how many are unique. The *Additional events* list will not display statistics until the [product feed](https://docs.yespo.io/docs/importing-product-feed) is loaded into the system and these events are configured. For stable operation of events, we recommend configuring their sending [by calling eS.JS functions](https://docs.yespo.io/docs/how-set-web-tracking-sending-events-java-scipt-request). This method allows you to independently control the transfer of data and promptly respond to changes on the site.

> 🚧 Important
>
> If you install a script via Google Tag Manager or any other tag manager, you may lose tracked data as it may be blocked by content filters.
