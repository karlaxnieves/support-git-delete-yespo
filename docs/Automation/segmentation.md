---
title: Segmentation
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Segmentation | Yespo Support
  description: >-
    The document explains the process of segmenting a contact database in Yespo
    into static and dynamic segments to enhance marketing strategies and
    campaign efficiency, detailing how to create, manage, and delete segments,
    as well as search for them.
  robots: index
next:
  description: ''
---
Segmentation is the process of dividing the contact database into segments based on specific conditions, such as gender, date of birth, order value, region, interests, etc.

Effective segmentation allows for more precise adaptation of marketing strategies, messages, and offers for each segment of contacts. It can also enhance the efficiency of campaigns and improve interaction with the audience.

## Segments Types

There are two types of segments in Yespo:

* **Lists**: static segments, that are updated manually, via workflows, or by transferring data [via API](https://docs.yespo.io/reference/getting-started-with-your-api). For example, when [importing contacts](https://docs.yespo.io/docs/uploading-file-with-user-profile-data), [exporting them from reports](https://docs.yespo.io/docs/exporting-subscriber-groups-reports) or dynamic segments.
* **Dynamic**: dynamic segments that are regularly updated according to specified conditions. As soon as a contact matches the specified conditions, it’s automatically added to the segment. If the contact ceases to meet the conditions, it automatically leaves the segment.

## Creating Segments

1. Go to *Contacts → Segments* and click *Add segment*.

<Image align="center" width="80% " src="https://files.readme.io/b844c084e53928608c7abc51f56bddc82da613474ed25558effb20d172ea720b-segmentation-001.webp" />

2. Select the type and click *Create*.

<Image align="center" width="80% " src="https://files.readme.io/ab1e5e0048c66a147930473d3176905438c1b817178237bc6ec66817111ebad1-segmentation-02.webp" />

[Learn more about how to create dynamic segments >](https://docs.yespo.io/docs/how-add-dynamic-segment)

## Segment Management Options

To access management options, press the three dots icon in the segment field.

<Image align="center" width="80% " src="https://files.readme.io/c554211e5206b9eb945189ab17773d9a7f4dadfe649a9cd190b8cd7246d48249-segmentation-03.webp" />

Available options:

* **Contacts export**

Any dynamic segment can be transformed into a regular contact list. For example, it is necessary to save contacts in a permanent list, as contacts in dynamic segments are constantly updated depending on conditions.

* **Copy segment**

Only for the *Dynamic* segment type.

* **Split segment**

Used for A/B testing. Splitting can be done manually or automatically by activating the *Distribute evenly* switch.

<Image align="center" width="80% " src="https://files.readme.io/8cd6d2bb388028acc119fe2c551153174b9babdd00872b680641f2388feb7e13-segmentation-04.webp" />

> 📘 Note
>
> You can split a segment only if it includes more than 10 contacts. We recommend conducting split tests with more than 2,000 active contacts to avoid inaccurate results.

* **Empty segment**

Only for the *List* segment type.

> 📘 Note
>
> When you delete contacts from the list, they will remain in your database.

## Deleting Segments

Two methods are available:

1. Via the segment management options.

<Image align="center" width="80% " src="https://files.readme.io/c2508fb227aa213ea408dd2bb1198bf7020bd4683d679ede1f8bf922e9557693-delete-segment-01.webp" />

2. From the list of segments.

> 📘 Note
>
> This method allows you to delete multiple segments at once.

Select the required segment from the list and click the *Delete selected* button.

<Image align="center" width="80% " src="https://files.readme.io/53c982e838a93705a81dd2366a2fc5c5e0de90b1d04adbc1bcdeef5ed3d02a0b-delete-segment-03.webp" />

If you choose the *Delete with all contacts included in the segment* option, restoring contacts will be impossible.

<Image align="center" width="80% " src="https://files.readme.io/2261226623f9bb00343cac458d4a5b6f9629febf47797ff711063ed2e2acac4c-delete-segment-02.webp" />

## Searching for Segments

For a quick segment search, use the search field for:

* Name
* [Tag](https://docs.yespo.io/docs/adding-tags#adding-tag-to-the-contact-segment)
* ID

<Image align="center" width="80% " src="https://files.readme.io/d361b9820255bd0cda28469897e969e473c9bc81190f36e5750477bfc30c13d5-segmentation-05.webp" />

> 📘 Note
>
> The list of segments shows the workflows in which they are used

<Image align="center" width="80% " src="https://files.readme.io/c5384f1cd7acdcded39b5f5631e03863b6978d3b286d9c4d3379c474e27aeb59-workflows.webp" />
