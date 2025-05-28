---
title: Orders
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Orders | Yespo Guide
  description: >-
    Order automation enables processing sales, creating triggered order series,
    and sending personalized post-purchase messages.
  robots: index
next:
  description: ''
---
[Order automation](https://docs.yespo.io/docs/orders-automation) allows to process your sales, create triggered order series and send personalized post-purchase messages.

Send order data to our system to:

* get RFM analysis of your contact base;
* send transactional order-related messages;
* [segment your audience by order parameters](https://docs.yespo.io/docs/how-to-use-event-segmentation).

To send transactional messages, you need to:

* set up order transferring through API ([*Add order*](https://docs.yespo.io/reference/ordersbulkinsert-1) or [*Generate event*](https://docs.yespo.io/reference/registerevent_1)  methods);  as *Add orders* resource has some limitations, we recommend using *Generate event*.
* create a message  with [dynamic content;](https://docs.yespo.io/docs/using-velocity-email)
* create a [workflow](https://docs.yespo.io/docs/workflow-management).

> 📘 Note
>
> The system stores order events for 5 years. All this data you can use for segmentation. To increase or decrease the storage period, leave a request at [support@yespo.io](mailto:support@yespo.io).
