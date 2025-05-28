---
title: Merge Tags Cheat Sheet
excerpt: >-
  This cheat sheet provides an overview of how to use merge tags effectively in
  your communications.
deprecated: false
hidden: false
metadata:
  title: Merge Tags Cheat Sheet | Yespo Guide
  description: >-
    Merge tags in Yespo enable personalized communication by dynamically
    inserting contact information into messages, with options for standard and
    custom tags, and can be used in links and combined for enhanced
    customization.
  robots: index
next:
  description: ''
---
Merge tags are a powerful tool for personalizing your communications in Yespo. They allow you to use dynamic content for personalized interactions with the contacts, making each touchpoint more relevant and engaging.

## Merge Tags in Messages

In messages, you can use 2 types of merge tags:

* **Standard**: Default merge tags.
* **Custom**: Additional fields you can create in the system.

These tags substitute the contact information from the contact card you add manually or using [API](https://docs.yespo.io/docs/api-methods-adding-contacts).

Read this [article](https://docs.yespo.io/docs/personalization-by-merge-tags) to learn how to personalize your messages using merge tags.

### Standard Merge Tags

| Name                 | Merge tag                  | How it works                                                      |
| :------------------- | :------------------------- | :---------------------------------------------------------------- |
| First name           | %FIRSTNAME\|%              | Inserts the contact's first name.                                 |
| Last name            | %LASTNAME\|%               | Inserts the contact's last name.                                  |
| Full name            | %FIRSTNAME\|% %LASTNAME\|% | Inserts the contact's full name.                                  |
| Email                | %EMAIL\|%                  | Inserts the contact's email address.                              |
| SMS                  | %SMS\|%                    | Inserts the contact's phone number.                               |
| External customer ID | %EXTERNAL\_CUSTOMER\_ID\|% | Inserts the contact’s unique identifier generated in your system. |
| Town                 | %TOWN\|%                   | Inserts the city or town name.                                    |
| Address              | %ADDRESS\|%                | Inserts the contact’s address.                                    |
| Region               | %COUNTY\|%                 | Inserts the name of the administrative division within a country. |
| Postcode             | %POSTCODE\|%               | Inserts the postal code.                                          |
| Group name           | %GROUP.NAME\|%             | Inserts the name of the segment.                                  |
| Message name         | %MESSAGENAME\|%            | Inserts the name of the message.                                  |

The symbol `%` denotes the start and end of merge tags in messages. This indicates that the text between these symbols should be replaced with dynamic content.

You can use the vertical bar (`|`) before the closing `%` symbol and add alternative text between them that will be shown to the contact if the contact field corresponding to the merge tag is empty.

*Example*:

<Image align="center" width="80% " src="https://files.readme.io/cc8f5e3377362b54ffd620087afcbcf0ef7b2a8b625d027f71abd199aa248e44-example-firstname.webp" />

If the first name exists in the contact card, it will be shown in the message.

<Image align="center" width="80% " src="https://files.readme.io/36900c165b23e7c8abcc55fb08cd8a00f1bf1c25513b8465fff80edf8d272301-substituted-name22.webp" />

If there is no first name, the alternative text will be shown.

<Image align="center" width="80% " src="https://files.readme.io/ff701a26839065b24ed7a4ab8380a6787cdb29d464c3ed77355fa443dd30f42e-alt-text22.webp" />

### Custom Tags

You can add your custom tags following these [instructions](https://docs.yespo.io/docs/how-add-additional-contact-fields).

## Using Merge Tags with Velocity Commands

You can pull dynamic content using the `$!data.get(‘’)` command. Use only the tag name without the `%` and `|%` symbols.

*Example*:

```json
$!data.get(‘FIRSTNAME’)
```

Read this [article](https://docs.yespo.io/docs/using-velocity-features-yespo) to learn more.

## Adding Combined Merge Tags

You can combine several merge tags in a message by adding the corresponding statement in the message code.

1. Click the *Code editor* icon, and click anywhere outside the stripes to view the entire code.

   <Image align="center" width="80% " src="https://files.readme.io/b7639fa7937a5bacd70c1ad33ae8b9a41665ad419c256aafdeb2eceee6f55733-code-editor-icon.webp" />
2. Add the *statement* in the following format before the first *opening`<tr>` tag*:

   ```json Text
   <!--#set($var='%MERGETAG1|% %MERGETAG2|%')-->
   ```

   where substitute *MERGETAG1* and *MERGETAG2* with your merge tag names.\
   You can add other characters and spaces between the tags.\
   *Example*:

   ```json Text
   <!--#set($var='%EVENT.NY_SALE|%: %EVENT.NY_BONUS|%%')-->
   ```
3. Add the following *statement* after the last `</tr>` closing tag in the message:

   ```json Text
   <!--#*end-->
   ```
4. Type `$var` in the message where you want to show your combined tags.

   <Image align="center" width="80% " src="https://files.readme.io/cf0364eaf4783dc73bb6638769265b43b9f3460cffbe312e79e0d24af9928840-insert-var.webp" />

When you send your message, the variable is substituted with the corresponding values of the merge tags, as in the following picture.

<Image align="center" width="80% " src="https://files.readme.io/651e89cf7b1584352acdc35ae895d645af0f54876bba8a893cfa3b4c77243863-var-result.webp" />

## Using Merge Tags in Links

Merge tags can be used in links to personalize the content for each recipient. 

Example:

* `https://example.com?name=%FIRSTNAME%&email=%EMAIL%`

In this example, `%FIRSTNAME%` and `%EMAIL%` will be replaced with the corresponding values for each recipient.

When the email is sent out, the link will look something like this for the recipient:

* `https://example.com/?name=Randy&email=hallraw@example.com`
