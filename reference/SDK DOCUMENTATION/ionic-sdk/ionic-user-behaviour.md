---
title: Ionic User Behaviour
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
## Track Custom Events

Reteno Plugin provides ability to track custom events.

```typescript
import { RetenoPlugin } from 'сordova-plugin-reteno';

const eventName = 'EVENT_NAME';
const date = new Date().toISOString();
const parameters = [
    {
        name: 'Additional parameter',
        value: 'Additional value',
    }
];
const forcePush = false;

var payload = { 
    'eventName': eventName, 
    'date': date, 
    'parameters' : parameters, 
    'forcePush': forcePush
}

cordova.plugins.RetenoPlugin.logEvent(payload, success, error);
```

The `parameters` list item structure:

```typescript
type CustomEventParameter = {
  name: string;
  value?: string;
};
```

**Note**

`date`

Date should be in <a rel="nofollow" href="https://en.wikipedia.org/wiki/ISO_8601"> ISO8601 </a> format.

`forcePush` is `iOS`-only feature; Please read more about it  <a rel="nofollow" href="https://github.com/reteno-com/reteno-mobile-ios-sdk/blob/b8a9c60da9a41dc7cb22260b6ef8e5a842752b5e/Reteno/Sources/Core/Reteno.swift#L47"> here </a>.

> 📘 Note
> 
> Set up [event-based segmentation](https://yespo.io/support/how-to-use-event-segmentation) to ensure custom events and their parameters are recorded in contact cards, enabling the creation of dynamic segments.