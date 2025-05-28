---
title: Segment Tracking
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Segment Tracking | Yespo Guide
  description: >-
    Tracking segments enables you to observe the growth trends within chosen
    segments. Consequently, you can assess the efficiency of marketing
    initiatives aimed at particular audience groups.
  robots: index
next:
  description: ''
---
Segment tracking allows you to see the dynamics of base growth for selected segments. This way, you can see the effectiveness of marketing campaigns targeting specific groups of your audience.

## Adding Segments for Tracking

1\. Go to the *Contacts → Analytics* section and find *Segment tracking* in the general report.

2\. By default, statistics for individual segments are not tracked. To start collecting data for analytics, click the *Select segment* button.

<Image align="center" width="80% " src="https://files.readme.io/3ed8081746dbdaac415a53c6060d5eaa0f9816ff18a532a9fe408a9e303cdfff-segment-analytics-201.webp" />

3\. Activate the switches opposite the desired segments.

<Image align="center" width="80% " src="https://files.readme.io/dc452d6a23a252994b3551394377acdbe221337426357e83e5d2aed4d2b390c5-image1.webp" />

Data on changes in the number of contacts in the segment will appear within 24 hours.

## Displaying Data

Select the period for which you want to view statistics.

<Image align="center" width="80% " src="https://files.readme.io/eff1af40fc79f81a773449a5f5db9d6cd850a116ebf0c2e8ac6b1ebefd78c2af-segment-analytics-002.webp" />

The first column displays:

1. Segment name.
2. Tracking start date.
3. The number of contacts in the segment on the last day (recalculation ends at 02:00 UTC).
4. The number of contacts by which the segment has increased or decreased.
5. The segment's growth percentage at the end of the tracked period compared to the beginning.
6. The percentage of the segment's growth dynamics at the end of the tracked period compared to its beginning.
7. The button for viewing growth dynamics in the form of a curve.
8. The button for segment preview. 

<Image align="center" width="80% " src="https://files.readme.io/a7f2e2bf19599e93aca301581bb32da31936dadda7ef85b4efe34a1380217002-segment-analytics-003.webp" />

Other columns of the table display the following data:

1. The number of contacts in the segment on a specific date.
2. The number of contacts added or deleted relative to the previous reporting date.
3. The percentage of the segment growth relative to the previous reporting date, calculated using the formula: (current number of growth percentages - previous number/previous number) \* 100%.
4. The percentage of growth dynamics, calculated by the formula: the current number of growth percentages – the previous number.

<Image align="center" width="80% " src="https://files.readme.io/73ba81999a02b05d3ad5368970da4569ea2a17f0c02ea78647a6f629122df2ec-segment-analytics-004.webp" />

The shades of red and green in the color of the cells make it easy to see when significant changes have occurred in the segment size and to analyze marketing activities that occurred during the corresponding period.

If changes between reporting dates are less than 1%, growth percentages and growth rates are not shown.

> 📘 Note
>
> The segment statistics display the number of contacts without considering the type of their IDs. If, for example, you want to track the number of email subscribers, configure the appropriate parameters in the conditional segment.
