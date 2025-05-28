---
title: Adding Custom Fonts
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adding Custom Fonts | Yespo Guide
  description: >-
    How to add a custom font to the email editor from any source, including
    Google Fonts. What email clients support custom fonts and what replace them
    with standard ones.
  robots: index
next:
  description: ''
---
A web font is one of the ways to create an original style for your email.  you can add a custom font from Google Fonts or another source in the [email editor](https://docs.yespo.io/docs/email-editor).

## Font Sets in Yespo

There are three font sets in Yespo:

* Standard fonts – supported by all email clients and devices.

<Image align="center" width="80% " src="https://files.readme.io/60b2df20d3325278535f9976a860540c918650a272dc9cee090f69f92a8b830f-add-custom-fonts.webp" />

* Non-standard fonts – displayed on most modern devices.

<Image align="center" width="80% " src="https://files.readme.io/a945d9d7b705319022dd20465f53682069a54cbe6ee630697f1af348a4a3fd46-add-custom-fomts-02.webp" />

* Custom fonts – mainly used for banners custom fonts switch to standard ones when sending email.

<Image align="center" width="80% " src="https://files.readme.io/5a12c2e7a872d457f3579475df2e890c824649a9a7b7dd37d500e4131855a3d8-banner.webp" />

Custom fonts allow you to create individual email designs.

Email clients that support custom fonts:

* iOS Mail and Apple Mail;
* Outlook 2016 and Outlook 2011 for Mac;
* Android App and Android Mail 2.3, 4.2, 4.4;
* Lotus Notes 8.

## Adding Your Font to Yespo

1. Open an email or [create a new one](https://docs.yespo.io/docs/compose-email).
2. On the top panel of the editor, click the three dots icon and select *My fonts.*

<Image align="center" width="80% " src="https://files.readme.io/25911a14f20688ffc5d2369294c1a28e2035f94df4c6ed26797b607f681f9a69-adding-custom-fonts-001.webp" />

3. Click the *Add font* button.

<Image align="center" width="80% " src="https://files.readme.io/319596ee0c7fec4fbaabdd7644cdbf1f67aca4d10a2422eeb70b66fcf2b8275c-adding-custom-fonts-002.webp" />

4. In the *New font* window, enter the font parameters:

* Font name
* URL with CSS file
* Family

All fields must be filled.

You can get font parameters in one of the following ways:

* using the [Google Fonts library](https://docs.yespo.io/docs/how-add-custom-font#adding-a-font-from-google-fonts) (or another font library),
* creating [your font](https://docs.yespo.io/docs/how-add-custom-font#adding-your-own-font).

<Image align="center" width="80% " src="https://files.readme.io/62da4fbde74df4c44136bb0da174d6516c50c494312f254f3147a695b253a1a7-adding-custom-fonts-003.webp" />

5. Click Done.
6. Confirm page restart.

<Image align="center" width="80% " src="https://files.readme.io/903cc8f3a1d13288af28501ae2676773939db52cdcd33383eb43039c2d21a98d-adding-custom-fonts-004.webp" />

After restarting the page, the added font will appear in the general font list.

You can select *Do not restart* if changes to the message have not been saved. Next, save the message and open it again – the font will become available.

### Adding a Font from Google Fonts

1. Go to <a rel="nofollow" href="https://fonts.google.com/" target="_blank"> fonts.google.com</a>.

If you know the font's name, use the search or filter fonts by category, language, and properties (number of styles, thickness, angle, width, etc.). Also, you can sort fonts by trending, popularity, novelty, or name.

<Image align="center" width="80% " src="https://files.readme.io/1e59cb7a3ccf513a159c2ee3b913a886206b0c93be3a3c266e3d54756474fbce-adding-custom-fonts-005.webp" />

> 📘 Important
>
> Select only one font style because several styles will not load simultaneously. For 2 or more styles, add each new one separately after the previous one has been successfully added; for example, first add *regular*, then *medium*, *bold*, etc. They will be added to the editor as different fonts.

For example, let's add the *Barlow* with the *SemiBold 600* style.

2. Click the font field.

<Image align="center" width="80% " src="https://files.readme.io/cb989816826f059f85334c23d939b380a568b9f53e4b73b613607e4d60fedc80-adding-custom-fonts-006.webp" />

3. Click on SemiBold 600 + and click the *trash* icon to select a font style and display the block with options.

<Image align="center" width="80% " src="https://files.readme.io/aed534fed2f8ced8c80d001495f2e3bd6bfbefd86979a9859b31964cc0f517d0-adding-custom-fonts-007.gif" />

4. In the email editor, go to the *My fonts* tab and click the *Add font* button.

<Image align="center" width="80% " src="https://files.readme.io/ed7b96034994d43c533d1ffb47e457b735c3ff778130b0a9ff3edd4da73cfb9b-adding-custom-fonts-008.gif" />

5. Add the *Font name* in the *New font* window.

<Image align="center" width="80% " src="https://files.readme.io/eec07fd6a56b251bf486038e8de168d239018bb096d3428c95d10fb9a8fdadce-adding-custom-fonts-009.webp" />

6. In the tab copy the `href` attribute content as follows:

`https://fonts.googleapis.com/css2?family=Barlow:wght@600&display=swap`

<Image align="center" width="80% " src="https://files.readme.io/e7a60caabd5d5776e2848850f8b1047695551fa18fe78d63ad302e8935968e4f-adding-custom-fonts-010.webp" />

7. Insert the copied link in the *URL with CSS file* field.

<Image align="center" width="80% " src="https://files.readme.io/46c6030d8c2c5b3818916692bcff7740a47dbdc748c5541552f280e2cae6af38-adding-custom-fonts-011.webp" />

8.  Copy the family name from the CSS rules to specify families section in one of the formats::

* Barlow
* 'Barlow'
* 'Barlow', sans-serif
* 'Barlow', sans-serif;

<Image align="center" width="80% " src="https://files.readme.io/76ccb771e0bc99dde417a7a7bfdad1e6b1307273ef95a5a0ecebd09e150ccf91-adding-custom-fonts-012.webp" />

9. Insert the family name in the *Family* field and click *Done*.

<Image align="center" width="80% " src="https://files.readme.io/09c72dba2f443650010b3503213dd9fb6068fe988d2db27dbfe0c7dd4d006064-adding-custom-fonts-013.webp" />

> 📘 Important
>
> The value for *Family* must be copied directly from the fonts’ library. The font with a random name will be invalid.

10. Click *Restart now* and confirm the page restarting.

<Image align="center" width="80% " src="https://files.readme.io/ea251283a3848ff27b967828b0671b9a7c735fbd4932c432d519dc08462da010-adding-custom-fonts-014.webp" />

### Adding Your Own Font

Let's look at the *Font Squirrel* resource as an example.

To upload your font, you need to add the link to your server CSS file in the *URL with CSS file* field

1. **Go to<a rel="nofollow" href="https://www.fontsquirrel.com/tools/webfont-generator" target="_blank"> fontsquirrel</a>**.
2. Prepare and upload the TTF format font file and click *Upload fonts*.

<Image align="center" width="80% " src="https://files.readme.io/ba8d62f44aa736ab671a6deb8f6d7579127f5689d308c7c79c0ddf6f49450c20-adding-custom-fonts-015.webp" />

3. Click *Download your kit* and download the generated archive with **stylesheet.css** file.

<Image align="center" width="80% " src="https://files.readme.io/ddd3445f132994632994f5236725bed5fd0a02ff295930675d9f468b982f7066-adding-custom-fonts-016.webp" />

4. Add src to the file **stylesheet.css** to your server with the necessary font in the format woff2 (the script in this format would be in the kit), for example:

   ```css
   @font-face {
   font-family: 'Spartan';
   font-style: normal;
   font-weight: 200;
   font-display: swap;
   src: url(https://fonts.gstatic.com/s/manrope/v1/xn7gYHE41ni1AdIRggOxSuXd.woff2) format('woff2');
   unicode-range: U+0400-045F, U+0490-0491, U+04B0-04B1, U+2116;
   ```

5. Upload the **stylesheet.css** file to the server.

6. In the email editor, go to the *My fonts* tab and click the *Add font* button.

<Image align="center" width="80% " src="https://files.readme.io/197c8eaaa28b329b06a7dd6f8af426f12edff155b84a78b8380d334c6f8f8269-adding-custom-fonts-008.gif" />

7. In the *New font* window, add the *font name*, *URL with CSS file*, *family*, and click *Done*. 

<Image align="center" width="80% " src="https://files.readme.io/39875225802c8493c3eeae7d2ab2f3ab099d1a67f8a048f6554a73b05ca1b58a-adding-custom-fonts-017.webp" />

8. Confirm page restart. 

<Image align="center" width="80% " src="https://files.readme.io/b53126fcda06a81cdd33ae0e592f7a538d9538fcb67f36464f8c810b1e2f7be8-adding-custom-fonts-018.webp" />

### Using the Added Font

You can use all fonts in email messages after adding them.

1. Go to message and select the text.
2. Click the *Font* tab and select the required one.

<Image align="center" width="80% " src="https://files.readme.io/b07a3f6350feb303985cbb27cafc63150c1011a303c649f25ccaa722ae31dab4-adding-custom-fonts-019.webp" />

3. A font will be applied to the selected text.

### Editing/Deleting the Font

1. Go to *My fonts* in the email editor.
2. Click the *pencil* icon to edit or the *cross* icon to delete the font.

<Image align="center" width="80% " src="https://files.readme.io/5134e51a290080ad929ec9037af63b50133bc6f66df59c9a33973f7977b3bed1-adding-custom-fonts-020.webp" />

## Important Notes

1. If the font isn’t displayed in the email, check if it's available on the device you're viewing the email on. If it is not there, the text will be displayed in a standard font.
2. Some fonts are only supported for languages that use the Latin alphabet and can’t be used for languages that use the Cyrillic alphabet.
3. It is better not to use custom fonts for the main text but to place them on images; for example, add a banner to the text.
4. The email subject line and preheader will be displayed in a standard font determined by the email client.
5. When using a custom font, think about how it would look in email clients that don't support it. The text with the standard font may get bigger which may distort the layout. Test the email, configure an alternative font family, size and spacing for a correct display.