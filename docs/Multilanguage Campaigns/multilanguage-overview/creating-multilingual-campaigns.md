---
title: Creating Multilingual Campaigns
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating Multilingual Campaigns | Yespo Guide
  description: >-
    To create multilingual campaigns, use multilingual workflows that
    dynamically display different language versions based on language
    determination algorithms.
  robots: index
next:
  description: ''
---
Using multilingual workflows, you can send one message that dynamically displays different language versions to your subscribers.

> 📘 Important
> 
> The system automatically determines the language for a campaign based on one of the algorithms:
> 
> 1. If the event doesn’t determine the language, the message will be sent in the language specified in the [contact profile](https://docs.yespo.io/docs/user-profile). This is convenient for the existing base.
> 2. If the event determines the language, the message will be sent in this language. The language specified in the user profile will be ignored.
> 3. If the language isn’t determined by the event and isn’t specified in the user profile, the message will be sent in the default language.

## Creating Bulk Campaign

The process of scheduling/launching a bulk multilingual campaign is standard:

- select a multilingual message,
- move to _Campaigns_,
- select a [segment](https://docs.yespo.io/docs/segmentation),
- schedule or send a message.

The system will automatically send the necessary content to the corresponding contact. You don't need to build segments based on the language.

## Creating Triggered Workflow

The language value is passed from the event to the workflow's message block to the _languageParam_ (_Set the language parameter for the workflow_) field. This field is available in the [Email block](https://docs.yespo.io/docs/message-blocks), and all _Send obligatory (transactional) messages_ tasks ([email](https://docs.yespo.io/docs/popular-blocks#send-obligatory-transactional-email), [SMS](https://docs.yespo.io/docs/popular-blocks#send-transactional-sms-message), [Viber](https://docs.yespo.io/docs/popular-blocks#send-transactional-viber-message)).

Place any of these blocks in the workflow and

- Copy the name of the variable responsible for the language code from the event you link to the workflow.
- Wrap the variable in a dollar sign and curly braces in the _languageParam_ field of the workflow block.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0fa58393fe67ff04c85a4f168cbd6523388d7075dbca2d960aebd8038c78232f-creating-multilingual-campaigns-01.webp",
        "",
        "Block's settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


If you use one of the [single message blocks](https://docs.yespo.io/docs/message-blocks) except for email, there is no _languageParam_ field. This means the message will be sent in the language specified in the user profile. The message will be sent in the default language if the language isn’t specified in the user profile. If you need to determine language by the event, use the _Condition_ workflow blocks.

## Using Workflow Condition Blocks for Multilingual Campaigns

1. Create separate messages for every language you want to use.
2. Add the _Condition_ blocks with such settings to the workflow:

- Task name — _Variable matches regular expression_,
- name — variable name (eg, _Language_),
- pattern — regular language code value checked for compliance.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/caf717fbde4c0bcd3e3c61b5a60d187ca066b268609ca42c1aeaa9a1f0e3b919-creating-multilingual-campaigns-02.webp",
        "",
        "Condition's settings"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Each _Condition_ block should check if the event variable matches the specified pattern.

- If it does — the workflow goes by Yes brunch, which should be connected with the message in the corresponding language;
- If it doesn't — the workflow goes by No brunch, which should be connected with the following condition block.

The last _Condition_ block should be connected with the message on the default language by both branches. This way, if the event variable doesn’t match any specified pattern, such users will receive this last message.