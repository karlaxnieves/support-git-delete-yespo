---
title: Creating Segments
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: Creating Segments | Yepo Guide
  description: >-
    The document explains how to create and use static and dynamic segments in a
    CDP to target audiences for promotional emails, showing how well-designed
    segments improve campaigns by focusing on specific groups.
  robots: index
next:
  description: ''
---
Create groups to define the target audience of promotional emails and automate work with segments. Well-designed segments are the key to the success of marketing campaigns. Sending messages to a small group of selected contacts provides more value than a bulk campaign to the entire contact list.

## Types of segments you can create in our CDP

To segment subscribers and pick target audiences in the system, you can use two types of groups.

* Static segments (Lists)

Such groups are updated manually, through workflows, or by transferring data via API.

<Image align="center" width="80% " src="https://files.readme.io/34f04af6f18c8671b4228bf866a17e0e2fdfa46386fca14649873839627cb164-list.webp" />

Most often, static segments are created when [importing contacts](https://docs.yespo.io/docs/uploading-file-with-user-profile-data), [exporting them from reports](https://docs.yespo.io/docs/exporting-subscriber-groups-reports) or dynamic segments. You can remove contacts from a group manually, through workflows, or using the API.

<Image align="center" width="80% " src="https://files.readme.io/17330887632857b23881fc5c6b07904c9a66947178a636df1c5e9b33a90983af-creating-segments.webp" />

Use lists when working with a small group of specific contacts, such as seminar attendees.

* Dynamic segments

These groups are updated regularly based on the parameters you set. As soon as a contact matches the specified conditions, it’s automatically added to the segment. If the contact ceases to meet the parameters, it automatically leaves the group.\
Examples of dynamic conditions: haven't purchased over 7 months, have opened 5 emails during the last month, have a birthday today, etc. The migration of contacts occurs constantly without manual intervention.

[How to Add a Dynamic Segment >](https://docs.yespo.io/docs/how-add-dynamic-segment)
