---
title: Mobile Push Generation Using Built-in AI in the One from Many Block
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: >-
    Mobile Push Generation Using Built-in AI in the One from Many Block | Yespo
    Guide
  description: >-
    Learn how to use AI to automatically create and translate mobile push
    notification variants based on existing in One from many block, enabling
    efficient content creation and multilingual support.
  robots: index
next:
  description: ''
---
In the *[One from many](https://docs.yespo.io/docs/using-one-many-block)* block, you can automatically generate variants and translations of Mobile Push messages using built-in AI. The algorithm generates new texts based on the messages available in the block — this helps you create high-quality content faster, focusing on real contact reactions or available templates:

* If the workflow has already been active, the system analyzes the effectiveness of the message variants (for example, by the number of openings or clicks) and uses the best one as the basis for generation.
* If there is no activity yet, up to 5 messages available in the block are used to generate suggestions.

The following content is generated: the title, subtitle, and message body. Other parameters (tags, links, custom data, etc.) are copied from the original message.\
In the case of multilingual messages, the system automatically offers translations of the generated text into all languages ​​used in the original message.

> 📘 Note
>
> When you add multiple language versions to a message, their content copies the language text by default. Thanks to the built-in AI, you can avoid manual translation — just add needed language versions, and use the generation in the *One from many* block. The system will automatically create translations for each of the specified languages.

## Why AI Push Generation Is a Must-Use Feature

Built-in AI message generation is designed to significantly boost the performance of your Mobile Push campaigns. By analyzing engagement data from existing messages, the AI generates optimized content that resonates more effectively with your audience.

AI-generated messages demonstrate higher click-through rates (CTR) and conversions compared to manually written ones. This improvement comes from the AI’s ability to:

* leverage real performance data when crafting messages,
* generate content suited to specific contexts and audience segments,
* apply proven language patterns that drive user action.

Using AI in message creation also saves time and effort — from writing high-converting texts to automatically translating multilingual versions. 

> 👍 Recommendation
>
> Use the AI generation feature wherever Mobile Push messages are used in the *One from many* block. Consistent application across campaigns ensures you capture every opportunity to engage contacts with the highest-performing copy.

## Generation of Suggestions

1. In the *One from many* block settings, select the Mobile Push channel, the app, and tags you want to include (and exclude).

<Image align="center" width="80% " src="https://files.readme.io/71b198f4d49f85ed670b3cf9a59960f60338fe16df98ee51c23fa7a2c85006f9-AI_1.png" />

2. Click the *Generate now* button.

<Image align="center" width="80% " src="https://files.readme.io/a02a45eb2eab70158b9e1f6cf5d084c20e5e140205454c7c5dcb9b72623f2451-AI_2.png" />

3. Specify the number of suggestions to generate and click *Generate now* (you can generate up to 20 suggestions for one block per session).

<Image align="center" width="80% " src="https://files.readme.io/d7a1a48fe34f051ee0448c7c856276c96b746bca09c6e8992777fe3162a3fa3f-AI_3.png" />

The generation of suggestions will begin, after which you can review and save or reject the proposed AI options.

## Moderation of Suggestions

Generated suggestions are displayed in the right sidebar, where you can review them and then accept or reject them. Accepted suggestions will be added to the message pull in the block and will also be created in the general Mobile Push list.

1. Click on a suggestion in the left column to view its content on the right. If the suggestion is multilingual, a switch between the corresponding languages ​​will be available above the content.

<Image align="center" width="80% " src="https://files.readme.io/76fa96dcf9f7be06bbba8373718650112a06bad30b69169802568b68493ea4d1-AI_4.png" />

2. To save a suggestion for use in a block, select it and click *Publish messages*; to reject it, click *Discard*. You can also select all suggestions at once and accept or reject them.

<Image align="center" width="80% " src="https://files.readme.io/88b019e943fce27337ebf35f8c54bb091b8f1f25510be6d3c9726e615a2bd312-AI_5.png" />

Save the workflow to apply the changes.

> 📘 Note
>
> You can save the workflow even if not all suggestions are accepted or rejected — they are saved as drafts. The next time you open the workflow, you can return to review and finish moderating the remaining options.
