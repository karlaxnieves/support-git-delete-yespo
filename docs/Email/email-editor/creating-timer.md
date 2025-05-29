---
title: Creating Timer
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating Timer | Yespo Guide
  description: >-
    The document guides on adding a countdown timer in Yespo emails to highlight
    promotion deadlines, detailing steps from inserting the block to customizing
    settings for appearance and functionality.
  robots: index
next:
  description: ''
---
In the Yespo editor, you can add a countdown timer to your email. This block is useful to encourage your subscribers to purchase by indicating the promotion's end date.

<Image align="center" width="80% " src="https://files.readme.io/5be9107c94c568c8d1864ad32e71abb195f2e46ee648342c33c1805cd914229a-image9.webp" />

## Adding Timer to Template

1. Create an email or open a ready-made one in the **Messages → Messages** section.

<Image align="center" width="80% " src="https://files.readme.io/ddfb491f97537dda04539a97e6d120ae8b5005459f88544830df6f0cd3bc1306-image3.webp" />

2. Go to the **Blocks**tab in the **Content** tab on the left sidebar. 
3. Drag the block with a timer from the **Blocks** tab into the template.

<Image align="center" width="80% " src="https://files.readme.io/8d47f71033ba440a607e1d6f713ddc4646296fdb58efef18078881677304a658-image4.webp" />

## Timer Settings

Click the timer in the template to open its settings.

### General Settings

1. Specify the end date and time for the timer to make other timer settings available.
2. Select the time zone according to which the time will be displayed in the timer.
3. Set the font, color, and size for the numbers.
4. Specify the timer background color.
5. Select whether to display days. The timer will be in `HH:MM:SS` format without displaying days.
6. Select a separator between numbers (the default is colon).

<Image align="center" width="80% " src="https://files.readme.io/15531fa45168e27ae648c16d2ca752d02fcf3fcc7f76827f8fd64e9744f52490-image6.webp" />

7. Enable/disable number labels.
8. Select label language.
9. Select label font, size, and color.
10. In case the recipient opens the email after the timer expires, add an image that will be displayed instead.
11. Add a link to redirect the user when clicking the timer.
12. Alternate text will be displayed if the image fails to load. This can happen, for example, because the user has turned off the display of pictures in emails.

<Image align="center" width="80% " src="https://files.readme.io/f086f2f8c4dab75ab5267d62799aaf1ff3ff06d2e7c80f2e5c37ea8cf3dddebf-image2.webp" />

13. Alignment is set to left/right or center for desktop and mobile versions. To set the alignment for the mobile version, turn off image responsiveness in the settings below and full-width buttons on the **Appearance → Mobile Formatting** tab.

<Image align="center" width="80% " src="https://files.readme.io/2f3c5a1eca3aec5e586c772dc38b434c5a7b5cca7635c9db4d455b609ba6854e-image7.webp" />

14. Set the block width and height parameters in pixels.
15. You can adjust the timer to the email width.
16. When the **Responsive image** option is activated, the timer will adapt to the width of the mobile device.
17. We'll look at advanced timer settings in more detail below.

<Image align="center" width="80% " src="https://files.readme.io/e93b4984b96ef2562c1db2bdd1be4f0b1d73e0707e17d7104d275859407c07ba-image11.webp" />

18. Add padding to the left, right, top, and bottom of the timer (you can set separate padding for the mobile version).
19. You can direct recipients to the desired sections of the email using [anchor links](https://docs.yespo.io/docs/how-add-anchor-links-email). It is important to clarify that anchor links are not supported in some email clients: Gmail (iOS), Apple Mail (iOS), Outlook.com (Web), Outlook (Android), Outlook (MacOS).
20. Hiding an element means the selected version (desktop or mobile) will not have a timer.
21. Choose where to show the timer: everywhere, only in the HTML, or only in the [AMP version](https://docs.yespo.io/docs/amp) of the email.

<Image align="center" width="80% " src="https://files.readme.io/93312041abbd4b08bc52cb898b24336c3be668de77c9d3c71531a009dcff94b9-image10.webp" />

### Advanced Settings

Activate the corresponding switch in the timer settings to open advanced settings.

<Image align="center" width="80% " src="https://files.readme.io/5d636579ce749632ad56073287463d1eda0812b8e79596c0175dbb48c2ef1870-image8.webp" />

Advanced settings include:

1. Retina Display support — this option provides a high-resolution timer on LCD and OLED displays of Apple devices. Please note that activating this option may increase the download time of the letter.
2. Labels letter case.
3. Separate color settings for digits.

<Image align="center" width="80% " src="https://files.readme.io/29f3437ef3ce1a8ba253f15dbfaf2fb568dbce3bf55e17d2420db3f7c878fa8f-image1.webp" />

4. Font, size, and color of the separator.
5. Separate color settings for labels.

<Image align="center" width="80% " src="https://files.readme.io/b9344268fa8575ca9bdc53712c79819a7eb233b62351fc65b1c944026fb219af-image5.webp" />