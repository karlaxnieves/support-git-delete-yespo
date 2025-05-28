---
title: Placement of Recommendations on the Webpage
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Placement of Recommendations on the Webpage | Yespo Guide
  description: >-
    The guide explains how to set up placements for recommendation blocks in
    Yespo: create a placement, specify an element with a CSS selector, and
    assign it to a recommendation.
  robots: index
next:
  description: ''
---
Placement setting is required for recommendation blocks created [in Yespo account](https://docs.yespo.io/docs/creating-recommendation-block).

1. Go to _Placements_, click _New placement_ and select the page type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/806fd87331893c7acc1fef6c3e8c81d848ee88eab001d7d70e8eec52261a734c-Placements.webp",
        "New placement",
        "New placement"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Enter the title. For convenience, use the page type and where on the page the recommendation will be placed.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fae5d5afccf211d3d882e08ca691d25cf1d2bab478a8f26a10d19a24a8ab9a1d-image38.webp",
        "Enter the title",
        "Title"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Use a CSS selector to specify the element you want to add a placement to.

- Go to the page where the recommendation will be placed and click F12 to open the console. You can also open the console by right-clicking on the page and clicking _Inspect_.
- Activate _Select an element in the page to inspect it_ by clicking it.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5f719138b9480e4bb516909d538d914388ca302bdd9bc9e9a670a308a062ab0b-image39.webp",
        "Activate element selection",
        "Select element"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Click the element relative to which the recommendation will be placed (before, after, inside the element).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6fedbe7bd406a1c535955938107ffdf0c7dd8bd65b8defadfcd542185c724b94-image15.webp",
        "Select the element",
        "Select element"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Right-click the selected element and click _Copy > Copy selector_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d13d0186b1b562bdcdec11c50867b43bab9b7966b892973d127fa1cb576e5b0a-image40.webp",
        "Copy selector",
        "Copy selector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Paste the copied CSS selector in the input field above.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0745e3a6e648e166e710adaa8ff3a881ba65ddd9c68402eefeeae27bafcd1239-image35.webp",
        "Insert the selector",
        "Insert selector"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Select where the recommendation will be placed relative to the selected element and click _Done_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42ff0876260ab0c80f36cff626f73608f4fe3edc8a6d59476457ca8be0ae56da-image2.webp",
        "Select where to add a recommendation",
        "Select placement "
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. To assign the created placement to the recommendation, go to _Recommendations_ and click the necessary recommendation in the general list. Click _Parameters_, and in _Placement_ select the necessary placement.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/329ef12b113a71b1e5a6349aa1cbb569073a11121779c652815c2c90bfbf60bf-image4.gif",
        "Assign the placement to the recommendation",
        "Parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]