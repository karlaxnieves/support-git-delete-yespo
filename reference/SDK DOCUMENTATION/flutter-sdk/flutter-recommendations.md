---
title: Flutter Recommendations
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Flutter Recommendations | Guide
  description: >-
    This guide provides a comprehensive walkthrough on personalizing user
    experience and boosting sales by integrating recommendations.
  robots: index
next:
  description: ''
---
## Get Recommendations

You can personalize the user experience and increase sales by adding recommendations of your goods and services to your React Native app. The passed recommendations are based on customer activity data and include various options such as out of stock items, cross-selling, upselling, potential purchases, personal recommendations, and more.

```dart Dart
final recommendations = await Reteno.getRecommendations(
  recomenedationVariantId: 'r1107v1482',
  productIds: ['240-LV09', '24-WG080'],
  categoryId: 'Default Category/Training/Video Download',
  filters: [RetenoRecomendationFilter(name: 'filter_name', values: ['filter_value'])],
  fields: ['productId', 'name', 'descr', 'imageUrl', 'price'],
);
```

## Log Recommendation Event

You can track events related to showing user-specific product recommendations or user clicks on recommended products using this method.

```dart Dart
final event = RetenoRecomEvent(
  eventType: RetenoRecomEventType.impression,
  dateOccurred: DateTime.now(),
  productId: 'product_id',
);
final events = RetenoRecomEvents(
  recomVariantId: 'recom_variant_id',
  events: [event],
);
await Reteno.logRecommendationsEvent(events);
```