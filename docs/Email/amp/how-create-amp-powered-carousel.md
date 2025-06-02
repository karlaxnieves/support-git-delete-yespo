---
title: Creating an AMP Carousel
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: 'AMP-Powered Carousel in Email: How to Create | Yespo Guide'
  description: >-
    The article will teach you how to build and manage your first AMP-powered
    carousel in an email campaign
  robots: index
next:
  description: ''
---
You can create an AMP-powered carousel in the [email template editor](https://docs.yespo.io/docs/email-editor) with the help of in-built blocks or third-party services.

> 📘 Important
>
> To start sending campaigns with AMP-powered carousels, you must [register with Google](https://yespo.io/blog/how-apply-sending-amp-powered-emails-within-gmail) as a dynamic email sender.

## How to Create an AMP-Powered HTML Carousel

1. Go to **Messages** and choose any template you want to edit. Go to **Blocks** → **AMP-Carousel**.

<Image align="center" src="https://files.readme.io/39d233a830aeb8689681469fb9fcbef7b1e5c618f6b0e8291e6e43f7f861814b-AMP-Carousel.gif" />

2. Drag an AMP-carousel block to the HTML block you’re editing.

<Image align="center" width="80% " src="https://files.readme.io/fdaaa2dab3138648732ab427557d52d85395260fd98caa7d041594293d975546-amp2.gif" />

This block is **⚡HTML** tagged by default, as an **AMP element** is displayed only in email clients that support the AMP technology (Gmail, Mail.ru as for now). In other email clients, this block will be hidden: below there is provided an alternative option for such emails.

3. Double-click on the block to start editing.

* To add a slide, you can download **the images** from your computer, use the prepared images or bank images, or insert an external link to an image. One image shouldn’t be more than 2MB. The number of slides is unlimited.

<Image align="center" width="80% " src="https://files.readme.io/5d5481ec0928f36308b41745d0145f652a4d2708da8517a553219022a9c47f2d-amp3.gif" />

* Set the preview width, if needed, and add alternate text.

<Image align="center" width="40% " src="https://files.readme.io/18df2893ee279ccea646b854b5f7a0776a4a639e6f64c72d8d5aee1d28b6d188-amp4.webp" />

* Enable **Display preview** and click on **Message view** to see how your carousel will be displayed in an email on different devices.

<Image align="center" width="80% " src="https://files.readme.io/75459f9aba99e1985bcbde6b101578af016aa223ea0c147b820f88e49e06d2dc-amp5.gif" />

> 📘 Important
>
> Use images of the same height for smooth slide switching.

If the uploaded images are of different sizes, you can edit them in a built-in image editor. On the left of the slide image, click on **Edit image → Crop**, and set the necessary parameters.

<Image align="center" width="80% " src="https://files.readme.io/b09f6c1b85a7934022c6ac32fe8c520e59ba5f7a425676c4da5b7cd7f74757ac-amp6.gif" />

## How to Create an HTML Block for Email Clients that Don’t Support AMP

AMP-supported blocks will be displayed only for Gmail users. To make it visible in other email clients (Apple and Yahoo! Mail as for now), **create a dynamic carousel** using <a rel="nofollow" href="http://freshinbox.com/resources/tools/carousel/" target="_blank"> FreshInbox</a>.

* Go to Freshinbox and add necessary images by inserting their URL. The carousel should contain not less than three images.

<Image align="center" width="80% " src="https://files.readme.io/ca1a193656141e957a3b2e35a898178b0530154043d66cff15a984357be808a9-how-to-create-dynamic-carousel.webp" />

* If needed, add extra images by clicking on **More images**.

<Image align="center" width="80% " src="https://files.readme.io/2bd9b74ed310f1cffe3bbc85d7347bba5f73d3f9fed7470a5eadc6a4c340be30-how-to-add-more-images.webp" />

* Edit the image parameters. For carousel blocks, responsiveness is set by default.

<Image align="center" width="80% " src="https://files.readme.io/f555edf8ef914a2a05756e94ed10a56d3d651b3512b799850b18e846b173b99e-how-to-edit-images.webp" />

* Test the carousel by sending it to your email address.

<Image align="center" width="80% " src="https://files.readme.io/d789a79cbc09eed4eb1dd413bf3987052cb4a3a7d8088951c80d582310b4c13f-test-the-carousel.webp" />

Now you need to **transfer the carousel block**.

* Drag an HTML block to the previously created email with the AMP-powered carousel, and click on it to open the code editor tab.

<Image align="center" width="80% " src="https://files.readme.io/314471079cc7953613520546b63333c4994be176bc3782b73743a808461b2b7e-amp11.gif" />

* Copy HTML from Freshinbox.

<Image align="center" width="80% " src="https://files.readme.io/e933d6595a997ebe9b4339244880b5d7dbed4ddcca0d74d6fe3dd831800f26c4-amp12.webp" />

* Paste the copied code in the code editor.

<Image align="center" width="80% " src="https://files.readme.io/b9824b76321e3089dd70ee02cdc87338a047d0989baa3e5f1a9c8a5b8cc2387f-amp13.webp" />

* Copy CSS from Freshinbox.

<Image align="center" width="80% " src="https://files.readme.io/1067cf2e314644e63babef4365e6c63902c04afb8be3c7af132846b815892429-amp14.webp" />

* Paste the copied CSS at the end of the code in the corresponding tab.

<Image align="center" width="80% " src="https://files.readme.io/740a33530bf6c6bad4a84a50d4093f1f23369796b3516a61de3392ae0c89f84b-amp15.webp" />

* Click on the **Code editor** icon to close the editor.

<Image align="center" width="80% " src="https://files.readme.io/ee099fcf405e61ab0a86f8a244db60a81a7a84d309260d47a64790c75043d1af-amp16.gif" />

* Click on the added carousel, go to **Include in** and click on **HTML**.

<Image align="center" width="80% " src="https://files.readme.io/4436cb20cd4427ae2266f91bc5710fadb0ac18b4cad7157c742fb919a397098c-amp17.webp" />

* Click on **Message view** to see how both blocks look on different devices.

<Image align="center" width="80% " src="https://files.readme.io/3ea353b004bfa0b585799d113f15597f70f1fe76595a694530c2b2ef2ce51271-look-on-different-devices.gif" />

> 📘 Important
>
> * When you enable **Include in HTML**, the selected element will be displayed in all email clients that support only classic HTML-mime protocol.
> * When you enable**Include in AMPHTML** (⚡HTML), the selected element will be displayed in all email clients that support AMPHTML-mime protocol (text-x-amphtml).
> * If you enable **Include in both** (set by default), the selected element will be displayed in all email clients.
> * If the email client doesn't support the format of the selected element, the recipient will only see the first image.

**A few more tips:**

* Instead of an interactive HTML carousel, you can add a regular product card and enable **Include in HTML**. It will be displayed only in those clients that don’t support the AMP technology.

<Image align="center" width="80% " src="https://files.readme.io/ea4b7dbb0879af538ef99cf6c00fa1362dcb8ee93561d9611e909f6280819242-amp19.webp" />

* You can edit carousel images in the built-in image editor:
* add text;
  * edit size;
    * add a button, etc.

<Image align="center" width="80% " src="https://files.readme.io/68b19578189ff1bca3632e3f60df223bd434a3e297f56dbbdee5aded4f33f9b0-amp20.webp" />

* To check the AMP email for errors, click **View message**.

<Image align="center" width="80% " src="https://files.readme.io/7e90658ef0c305482b9dbb2d462f93e5998f15923665a321d187e75c58de98f6-Email_message_-_Google_Chromeghbtv.webp" />

Hover over the errors to see the description. You can fix them straight in the builder, or copy the code for validation in Google Playground.

<Image align="center" width="80% " src="https://files.readme.io/d598c9016cdd4294c59ef6d7c476eba55713e582d965083f69b5674ee6a9e881-Email_message_-_Google_Chrome7878.webp" />