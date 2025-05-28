---
title: Flutter User Behaviour
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

`Reteno SDK` provides ability to track custom events.

```dart Dart
RetenoPlugin().logEvent({required RetenoCustomEvent event});
```

###### Custom Event model:

```dart Dart
class RetenoCustomEvent {
  RetenoCustomEvent({
    required this.eventTypeKey,
    required this.dateOccurred,
    this.forcePush = false,
    required this.parameters,
  });
  final String eventTypeKey;
  final DateTime dateOccurred;
  final List<RetenoCustomEventParameter> parameters;
  final bool forcePush;
}
```

- `eventTypeKey` - key qualifier of the event (provided by appDeveloper, confirmed by marketing team).

- `dateOccurred` - time when event occurred (Date should be in [ISO8601](https://en.wikipedia.org/wiki/ISO_8601) format)

- `parameters` - list of parameters, which describe the event

- `forcePush` - `iOS`-only feature; Please read more about it [here](https://github.com/reteno-com/reteno-mobile-ios-sdk/blob/b8a9c60da9a41dc7cb22260b6ef8e5a842752b5e/Reteno/Sources/Core/Reteno.swift#L47)

###### Parameter model containt key/value fields to describe the parameter:

```dart Dart
class RetenoCustomEventParameter {
  RetenoCustomEventParameter(this.name, this.value);
  final String name;
  final String? value;
}
```

###### Example of usage:

```dart Dart
final dateOccured = DateTime.now();
final event = RetenoCustomEvent(
  eventTypeKey: eventTypeName,
  dateOccurred: dateOccured,
  parameters: [
    RetenoCustomEventParameter(<parameter_name>, <parameter_value>)
  ],
  forcePush: true|false,
);
await RetenoPlugin().logEvent(event: event);
```

> 📘 Note
> 
> Set up [event-based segmentation](https://yespo.io/support/how-to-use-event-segmentation) to ensure custom events and their parameters are recorded in contact cards, enabling the creation of dynamic segments.