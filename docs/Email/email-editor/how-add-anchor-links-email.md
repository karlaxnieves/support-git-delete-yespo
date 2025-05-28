---
title: Adding Anchor Links
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adding Anchor Links | Yespo Guide
  description: >-
    Learn how to add anchor links to emails in a drag-and-drop editor. Anchor
    links help the recipients navigate long email copies, skip irrelevant blocks
    and go to the content they’re most interested in.
  robots: index
next:
  description: ''
---
An anchor link is a link that leads the reader to a specific place in the email. Anchor links are most often used in the email menu, helping navigate long emails. Using them, readers can skip the irrelevant sections and jump straight to the content they’re most interested in at the moment.

<Image align="center" width="80% " src="https://files.readme.io/ec7b296e0558c8881732d0c6c7a649fb3b000f60509a5b471fc078134bc723ef-anchor.gif" />

> 🚧 Important
>
> Some email clients don’t support anchor links: Gmail (iOS), Apple Mail (iOS), Outlook.com (Web), Outlook (Android), Outlook (MacOS).

In our editor, you can add anchor links to the email in two ways:

* In the HTML editor;
* In the code editor.

## How to Add an Anchor Link in the HTML Editor

1. Select the block the anchor will lead the reader to.
2. Enable *Add an anchor link* and enter the anchor name (without a hashtag).

<Image align="center" width="80% " src="https://files.readme.io/f479c2bb8472028237e9561ec03794c325570393d5b6b7df328dbf9b40304db3-Adding_Anchor_Links01.webp" />

3. Select the element that will contain an anchor link.
4. In *Link*, chose the anchor name with a hashtag.

<Image align="center" width="80% " src="https://files.readme.io/4ddb0932a6046b26a00e59c361ee62aba3d377684f60c816194eec1145f90fcd-Adding_Anchor_Links02.webp" />

5. Click *Save*.

## How to Add an Anchor Link in the Code Editor

1. Select the element that will contain an anchor link.
2. Open *Code editor*.

<Image align="center" width="80% " src="https://files.readme.io/5d4eceadf3efc927858bf8fe3e238d30f334c5f614b7ff6ad23b58304374f5a5-Adding_Anchor_Links03.webp" />

3. Add `a href="#anchor_name"` before the element name in the code.

<Image align="center" width="80% " src="https://files.readme.io/4a2004b86eaa28da7880229ea55cc57dc126099ba4b715f4fd773bce114fb388-image6.webp" />

4. Select the block the anchor will lead the reader to.
5. Add `a class="esd-anchor" name="anchor_name"` before the closing `a` tag.

<Image align="center" width="80% " src="https://files.readme.io/b7faac2e2c3e53eee0f59a62acaf2abaa06598e39228ed82344fc2f36e2cc06d-image5.webp" />

Send a test message to check anchor links.

<Image align="center" width="80% " src="https://files.readme.io/39050b3ac6cb058e2d6e98649568b213409f545b27a64d88712931d8115b574e-Adding_Anchor_Links04.webp" />
