---
title: Promocodes
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Promocodes | Yespo Guide
  description: >-
    The document outlines various methods for adding promo codes to messages,
    including options like user profiles, databases, APIs, workflows,
    preprocessors, and code generation, with links to detailed instructions for
    each method.
  robots: index
next:
  description: ''
---
You can add a promo code to any messages in one of the following ways:

- [Promo code added from user profile](https://docs.yespo.io/docs/promo-code-added-user-profile). Unique promo codes for each contact in bulk campaigns. A promo code is added to the contact card, and next is added to the campaign.
- [Promo code from data base](https://docs.yespo.io/docs/promo-code-data-base). Unique promo codes for each contact in bulk campaigns. Upload a promo code database, and the system will take promo codes from there and insert them into emails.
- [Promo code added via API](https://docs.yespo.io/docs/promo-code-added-api). You can send emails via API and deliver a unique promo code to each recipient or launch bulk campaigns with a single promo code.
- [Promo code sent from a workflow](https://docs.yespo.io/docs/promo-code-sent-workflow). Upload a big list of promo codes for triggered messages and send them from a workflow.
- [Promo code sent via preprocessor](https://docs.yespo.io/docs/promo-code-sent-preprocessor). Only for email bulk campaigns.
- [Promo code generated in a workflow](https://docs.yespo.io/docs/promo-code-generated-workflow) at the moment of the campaign launch. They can be decoded and verified on your side.
- [Promo codes generated  with PHP/JAVA](https://docs.yespo.io/docs/encoding-and-decoding-promo-codes).

Use an [HTTP request](https://docs.yespo.io/docs/passing-promo-codes-messages) to pass a unique promo code from the message to the card of the contact who received it.