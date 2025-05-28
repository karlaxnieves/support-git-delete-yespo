---
title: GDPR Overview
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: GDPR Overview | Yespo Guide
  description: >-
    See how to solve main regulation tasks and remain compliant with data
    protection laws.
  robots: index
next:
  description: ''
---
## GDPR

General Data Protection Regulation (GDPR) is a complex of rules for using and protecting EU and UK residents’ personal data.

According to GDPR, two parties are responsible for compliance with the law: _Controller_ and _Processor_.

- **Data controller** determines the goals and means of personal data processing (your organization as a customer).
- **Data processor’s** function is to process personal data on Controller's behalf or provide tools for this purpose (area of responsibility).

As the data processor, we provide you with the full range of technical and organizational measures to protect the data subject's rights according to GDPR.

> 📘 Note
> 
> GDPR became the basis of some other personal data regulations, such as California Consumer Privacy Act (CCPA) or Brazilian General Data Protection Law (LGPD). However, due to the common basis of these laws, our data protection measures allow you to meet all their requirements.

See below how to solve main regulation tasks and remain compliant with data protection laws.

## Right to awareness

Provide users with information in a transparent, accessible way about the data you collect and how you plan to use it. Make this information available every time you plan to gather new information — from downloading your app to subscribing to new communication channels. A user should be aware of how exactly you are planning to process the data.

## Data processing permission

Permission to use personal data must be free, specific, informed, and unambiguous. It must be active — do not use default permission checkmarks.

We help you to receive communication permission for every channel:

- **Email** — as DOI email subscription completely meets the GDPR requirements, we provide you with ready-made DOI templates, workflows, and web forms: everything you need to grow your contact list effectively.
- **Mobile push, In-app, App inbox** — we recognize iOS and Android users and send them notifications according to App Store and Google Play rules respectively.
- **Web push** — we provide you single and double opt (DOI) in mechanics to collect user web tokens.

## Right to be forgotten

Users have the right to be forgotten, so you must exclude them from all marketing campaigns and delete all their data upon request.

To do that, use the [Delete contact](https://docs.yespo.io/reference/deletecontact-1) API method. It completely deletes the user profile and all their data, including the tracked activity.

## Data access and portability

Users have the right to demand a copy of all their personal data you store. You must provide it within 30 days.

To get data on tracked user’s activity, use the [Get token activity](https://docs.yespo.io/reference/gettokenactivated-1) API method.

## Right to edit personal data

Users have the right to request that you make changes to their personal data if they consider it inaccurate or incomplete.

Use the [Update contact](https://docs.yespo.io/reference/updatecontact-1) API method to make changes to a user profile in our platform.

## Additional support

We will kindly help you develop all the processes you need. If you have some questions, suggestions, or wishes, feel free to contact our support service.

If you have questions regarding the legal side, we advise you to contact your lawyer.

[More on API >](https://docs.yespo.io/reference/getting-started-with-your-api)