---
title: Testing Email Subject Lines
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Testing Email Subject Lines | Yespo Guide
  description: >-
    Learn how to conduct A/B testing to determine the most effective subject
    lines. See how to get your emails opened more often
  robots: index
next:
  description: ''
---
You can conduct split testing of a campaign subject line in 2 ways:

- Set multiple subjects in your email
- Split the audience into several segments and send emails with different subjects to each segment

## Experiment with Subjects in Email

Specify the email's subject and click _Add subject_ in the email editor; enter an alternative one. You can use any number of alternative subjects.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1f3b8d0049b10a7b4b2dfb419186ff970de820c89504d8f70f855d2f8e04784f-en.webp",
        "Add subject",
        "Add subject"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


When sending, the system will divide recipients into equal parts according to the number of email subjects.

### Evaluating Test Results

1. In the _Campaigns → Reports_ section, open the report on the campaign with the experiment with subjects. See subject performance metrics on the _Experiments_ tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e04c6ac6f5fb26ef53705a96bdeafaa7ac6eb5a0ab2404992b5befc83da898e-image4.webp",
        "Experiments",
        "Experiments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The larger the segment, the more reliable the test result.

> 📘 Note
> 
> [Google Analytics](https://docs.yespo.io/docs/tracking-effectiveness-mailing-google-analytics) will collect statistics within one campaign without details by subjects. If you need to determine how many sales a particular subject made, use testing with a segment’s splitting.

## Testing Subjects with Target Segment’s Splitting

1. Go to a segment to which you want to send a campaign (_Contacts → Segments_).
2. Click _Split segment_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/763633afb9428e2f792282f99013fbf4e384043be5c25145306df740e304b081-image5.webp",
        "Split segment",
        "Split segment"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Set the segment parts’ number and the percentage split. The maximum number of parts is 3. Activating the _Distribute evenly_ switch ensures that segments contain equal contact numbers.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db2934941badda668bcde0e801b22cef43a349229472dabc090de6d24dfa8024-image1.webp",
        "Segment splitting",
        "Segment splitting"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


New segments will appear in the segments’ list after splitting:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/76e75f561ab9087065c285f7f5cd2dce651798626fee00dc25373c4e3a9ef1a6-image2.webp",
        "New segments",
        "New segments"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Create several emails (corresponding to the number of segment’s parts) with the same content but different subjects. Give messages different names to analyze the results of the campaign in GA.
5. Send emails to prepared segments.