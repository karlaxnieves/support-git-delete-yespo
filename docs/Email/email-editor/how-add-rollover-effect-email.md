---
title: Adding The Rollover Effect
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adding The Rollover Effect | Yespo Guide
  description: >-
    Rollover effects in email campaigns enhance interactivity by changing images
    when hovered over.
  robots: index
next:
  description: ''
---
Rollover is the effect that changes one image to another when a user hovers it. When user moves the cursor away, the initial image returns.

In email campaigns, rollover helps implement interactivity and can make the message more interesting for customers.

## Creating a Rollover

1. [Create a new email](https://docs.yespo.io/docs/compose-email) or open an existing one.
2. Select a place for the rollover in [the email structure](https://docs.yespo.io/docs/adaptive-email-builder-review#structures): go to the [Image block](https://docs.yespo.io/docs/working-images-block) and drag it to the required place.

<Image align="center" width="80% " src="https://files.readme.io/83a5167b705a72ad4aa6caf903e4969ebc1a00020004b1e074cdae19750c82a1-adding-a-rollover-001.webp" />

Prepare two images in `PNG`, `JPG` or `GIF` format. Not more than 3 MB or 4000 x 4000 px.

> 📘 Important
>
> Both images must have the same width-to-height ratio; otherwise, the layout of the email may be broken when hovering over it.

One of the two images will be displayed independently of the cursor's position, while the second will appear when user hovers the cursor over the image.

<Image align="center" width="80% " src="https://files.readme.io/ce48aa8d77710e63a70acc288559bac50e9f096cc3f6b9ffaef0889c07f44359-adding-a-rollover-002.gif" />

3. Clik on the **Image** block and upload the main image, which will be displayed without hovering over and in static emails. 

<Image align="center" width="80% " src="https://files.readme.io/98b5a9ff605fc77bfaeba4d0d143e1dea604e794f98695d421d4b7a500669189-adding-a-rollover-003.webp" />

4. Activate the **Rollover effect** switcher.

<Image align="center" width="80% " src="https://files.readme.io/e7baaee5dc65ebeab6d18e9fea82073499866bdfc6bb31baecae6062b33813e2-adding-a-rollover-004.webp" />

5. Upload a second image that will be displayed on hover over. 

<Image align="center" width="80% " src="https://files.readme.io/faa316da17302baca0c8fb23d77878251f1b69fe498051770f1a4bbba5d8d2c7-adding-a-rollover-005.webp" />

6. Add a required link, alt text, and other settings for the **Image** block.

<Image align="center" width="80% " src="https://files.readme.io/ebdac142072955d2567f72ff3557f6c638eb5002d64de267ef1307c1cdbc61e0-adding-a-rollover-006.webp" />

> 📘 Note
>
> The link to the image and the alternative text are the same and are set only once after uploading the second picture.

The email in the mail client looks like this:

<Image align="center" width="80% " src="https://files.readme.io/11d8ebc02209ab380b8e1aa45a9ce9429bb55040c28da888216178c629ff5cee-adding-a-rollover-007.gif" />

## Rollover Features

1. Rollover is displayed in limited email clients: Gmail, iCloud Mail, Outlook 2003, Apple Mail, Yahoo! Mail, Ukr.net, AOL.
2. Rollover works only on desktops where it’s possible to hover over images. Touchscreen devices don’t support this feature: they display one picture a click on which would forward to the website.
3. By far, no email testing tool (Litmus, Email on Acid) offers interactive message testing. To see how your campaign looks like, send tests to all the available email clients and devices.
4. Currently, this feature is available for images and buttons (highlight-hovered buttons). The rollover effect for other elements isn’t supported.