---
title: Adding a Hidden Preheader
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Adding a Hidden Preheader | Yespo Guide
  description: >-
    A hidden preheader is a text that follows the subject line in Inbox. Learn
    how to add a preheader to emails without code knowledge.
  robots: index
next:
  description: ''
---
A hidden preheader is a text that follows the subject line in Inbox. Its display and appearance may differ depending on the device and email client. On desktop, preheader text can be between 75 and 100 characters long; on mobile – between 30 and 55 characters.

<Image align="center" width="80% " src="https://files.readme.io/7b6ceec52e4f4ae818a14572d89be53b3dfc7e8ae24e262fda4c45129e4c17f6-image4.webp" />

Tasks of the preheader:

* Complement the subject. Especially applicable to mobiles where the subject display is limited to about 40 characters.
* Show the recipient what content to expect in the email.
* Catch attention with incentives;
* Increase open rate.

## How to Add a Preheader to an Email

By default, email clients use the first line of the email copy as a preheader. Depending on the design, it can be image alts, menu titles or anchor links. Such preheaders don’t look nice in Inbox. But with a hidden preheader, you can set the exact text you want to appear as a preheader.

In our platform, you can add it without code editing by adding a preheader to a special field in the template settings. In code, it’s embedded with an esd-hidden-preheader class.

<Image align="center" width="80% " src="https://files.readme.io/c1656461aa00df0fcc33bf2141107d29a0b203da8c15b75e127d4143afc3c982-image2.webp" />

1. Go to **Messages → Messages**.
2. Open the necessary email or create a new one and click its subject.

<Image align="center" width="80% " src="https://files.readme.io/4b812ab0018cc9fa46ef2fc7f546e1dab10abb8b4ad006a47083c1a641dab284-image41.webp" />

3. In **Hidden preheader**, enter your preheader text.

<Image align="center" width="80% " src="https://files.readme.io/dc48ecb709eeb63aaf0a9dd8a9683de1bff9f1c6ac3e19667aabc5854f3e955a-image1.webp" />

4. To [optimize the text with AI](https://docs.yespo.io/docs/using-ai-email-editor), click **Improve with AI** and select one of the suggested options.

<Image align="center" width="80% " src="https://files.readme.io/168029f43c44ba53e98304a937f7f9dde88621dcb26b3b705d9e13f3463d5ea8-image3.webp" />

5. Optionally enable **Add white space**. It will separate the preheader from the rest of the copy in Inbox, making it look nice and professional.

<Image align="center" width="80% " src="https://files.readme.io/6c776e62a8a13b399f24ba40ac1a4656eb89c4ffa9e34b20828391c66073b6f5-image21.webp" />

In code, you can see white space as space symbols that alternate with non-breaking space symbols:

<Image align="center" width="80% " src="https://files.readme.io/86a02e23b7f21f12860db0dd1753de1cc0fdac0fc5a5e0f09ee00998ead81b1e-preheader-code.webp" />

You can remove unnecessary space symbols if needed.

You can use white space without a preheader. This way, only the subject will be displayed in Inbox.

<Image align="center" width="80% " src="https://files.readme.io/d9da414ea42005b207c31a758e393bac2ce33469b0efa30e8de4a2bbbe08be95-image6.webp" />

6. Send test messages to test how the preheader looks in different clients on the mobile and desktop.

<Image align="center" width="80% " src="https://files.readme.io/61fe60a97f6d0038409d1e5042e468fafa73bd622dd6be71c1d11c059f3a5089-image31.webp" />