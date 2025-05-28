---
title: Unity User Behaviour
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Android User Behaviour

## Track Screen View Events

You can manually track screen view events by calling RetenoSDK.LogScreenView(string screenName) and pass name of the screen as a parameter. You can track these events according to your needs and based on your screen lifecycle:

```C#
RetenoSDK.LogScreenView("some_screen_name");
```

> 📘 Note
>
> Set up [event-based segmentation](https://yespo.io/support/how-to-use-event-segmentation) to ensure custom events and their parameters are recorded in contact cards, enabling the creation of dynamic segments.
