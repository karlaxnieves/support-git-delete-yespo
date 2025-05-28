---
title: Using A/B Tests for Widgets
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using A/B Tests for Widgets | Yespo Guide
  description: >-
    Yespo offers A/B testing for widgets like subscription forms, informers,
    launchers, and age gates. Compare variations to optimize user experience.
  robots: index
next:
  description: ''
---
A/B testing (or split testing) is a methodology for researching user experience. When running a test, you can split your audience to test different variations of your widget or launcher and determine which of them is performing better.

In Yespo, you can run an A/B test for the following types of widgets:

- Subscription forms
- Informers
- Launchers
- Age gate

A test can include different types of widgets.

> 📘 Note
> 
> You cannot delete the widgets participating in a running test.

You cannot run A/B tests for the widgets:

- Containing errors.
- Having non-saved changes.
- Used in another A/B test.

To open the A/B tests screen, go to _Site → Widgets_ and select _A/B tests_ in the left-hand side panel. If you do not have any tests, the A/B tests landing page displays.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6c5bd13d00ab144336ff1a79fa5ebfb8b1e8a6362e8e3025f68325cb67d8be21-using-ab-b-tests-for-widgets-01.webp",
        "A/B tests",
        "A/B tests"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Managing A/B Tests

To create a new A/B test, click the New test button. 

You need at least 2 widgets to create and run an A/B test. If you don’t have them, pressing the _New widget_ button opens the dropdown menu suggesting the creation of a widget.

Select the type of widget you want to create and follow the instructions in [Setting Up Widgets for Your Site](https://docs.yespo.io/docs/setting-up-widgets-for-your-site).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a455dacc954a35fe92b3ce8807d3f2e2fa1535cd30826afb52e3188f1fd7c083-using-ab-b-tests-for-widgets-02.webp",
        "New widget",
        "New widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


  When you have the widgets to compare, you can proceed with the creation of tests.

In Yespo, you can create and run A/B tests to compare:

- 2 widgets.
- 2 widgets when one has a connection to a launcher.
- 2 pairs of widgets and launchers.

See the following sections to learn how to create and run the different types of tests.

When you have the created and completed tests, the A/B tests page shows the tests in progress marked with the play icon in the Status column. The completed tests are marked with the _tick_ icon.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60543b83d2d2b2887a8f8f119ac8d2fdd3286f40de988b1018414364ffa6c72a-using-ab-b-tests-for-widgets-03.webp",
        "A/B tests page",
        "A/B tests page"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The Confidence column shows the reliability of the test results in percent. The test results are reliable when the confidence is greater than 90%. In this case, the confidence value is displayed in green.

### Stopping a Test in Progress

To stop the test in progress, expand the In progress dropdown menu in the Status column and select one of the options:

- **Stop**: To stop the test and keep the widgets published.
- **Stop and unpublish the worse**: To stop the test and unpublish the widget with the worst performance when the confidence is less than 90%.
- **Stop and unpublish loser**: To stop the test and unpublish the widget with the worst performance when the confidence is greater than 90%.
- **Stop and unpublish both**: To stop the test and unpublish both widgets when the confidence is 0%.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/579f6297a46ea2cd7249eb55eed9098b73d3ead0e1ee1b6e6245d919bc994007-using-ab-b-tests-for-widgets-04.webp",
        "Stopping a test",
        "Stopping a test"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The stopped tests change their status to _Completed_.

> 📘 Note
> 
> When you stop a test in progress, you will not be able to relaunch it.

### Deleting a Test

To delete a test from the list of A/B tests: 

1. Click the _ellipses (three dots)_ icon on the right-hand side of the test row, and then click _Delete_ in the dropdown menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/031c50f2b4685691b8b737d8657274c3865cb9c47c9e4fab8084b6ff2f1596da-using-ab-b-tests-for-widgets-05.webp",
        "Deleting a test",
        "Deleting a test"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. Click _Delete_ in the dialog box.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/92376e71a909764452447359116a1c9403d37414c5728d17aa1871fead528187-using-ab-b-tests-for-widgets-06.webp",
        "Click Delete",
        "Click Delete"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The test is permanently deleted from the list of A/B tests. The widgets that participated in the deleted test are not deleted.

### Viewing the Test Statistics

To view the test statistics, click the _test name_ in the Name column. The statistics page opens. Switch between the _Desktop, Mobile_, and _All tabs_ to view the test details for the desktop, mobile, or both versions of the widgets.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f3355b00e0db16f80ee9d70c5faf5062db3d246cd10f697b4a3e00887b82effa-using-ab-b-tests-for-widgets-07.webp",
        "Test statistics",
        "Test statistics"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To preview the widget, point to the widget _name_ in the Widgets column. The widget shows in the bottom right corner of the screen.

To go to the widget parameters, click the widget _name_.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5cd3af6b84309474a9057cfb99583a8a94eb580fd93e4bc0a7f6e573f6f0ff34-using-ab-b-tests-for-widgets-08.webp",
        "The widget parameters",
        "The widget parameters"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


To preview the widget and its calling rules in a new window, click the _Widget preview (eye)_ icon on the right-hand side of the row. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/97971137df92c97cb12cccb219b008b0c97868873c64b80c3f9b67bb5f2af016-using-ab-b-tests-for-widgets-09.webp",
        "Widget preview icon",
        "Widget preview icon"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


In the preview window, you can switch between the desktop and mobile preview by selecting the _Desktop preview_ or the Mobile preview icons in the top left-hand side corner of the screen. 

To go to the widget parameters, click the _Open_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bea2e1c8fa08f803dc9ca2d31b0b33fca1a066d9b9160ae4155c1b52becdcaf9-using-ab-b-tests-for-widgets-10.webp",
        "Preview window",
        "Preview window"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Creating the A/B Test for 2 Variations of a Widget

You can run an A/B test to compare the performance of 2 widgets.

To create the A/B test for 2 widgets:

1. In the A/B tests window, click the _New test_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/05536388cf13973f8dcaa72efc1fe1b6eab0882024a43d3329f2924ddaee2841-using-ab-b-tests-for-widgets-11.webp",
        "A/B test for 2 variations of a widget",
        "A/B test for 2 variations of a widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In the _New test_ window, enter the test _name_ (required) and test _description_ (optional) into the corresponding fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/83dfdfc8d2d997c3170dea4ddd9a3a9391c97bd742d46f0c91541a9b4765c010-using-ab-b-tests-for-widgets-12.webp",
        "New test window",
        "New test window"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Select widget A_ and select the widget from the list in the _Select widget_ window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5677c7280c452b0d7201b3cf4a0936a4662108c8a687c47aa56692b841f47efe-using-ab-b-tests-for-widgets-13.webp",
        "Selecting the widget from the list",
        "Selecting the widget from the list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> You can search for the widget using the Search box at the top of the Select widget window:
> 
> - To search by the widget name, enter the widget name or a part of the name into the Search box and click the _Search (magnifying glass)_ icon or press Enter.
> - To search by the widget ID, enter id: followed by space and the widget ID into the Search box and click the _Search (magnifying glass)_ icon or press Enter. For example, id: 8230

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18f82e81a1feb2ea72c873422314ee164aa038268283158abff15710aea01444-using-ab-b-tests-for-widgets-14.webp",
        "Searching widgets",
        "Searching widgets"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Select widget B_ and select the widget from the list in the Select widget window.

> 📘 Note
> 
> To replace the widget, point at the widget, click the _Replace widget_ icon, and select another widget from the list in the Select widget window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e76df514032ade51efd6b2664498c846b0e2886ca72b381b1007c17b445c0418-using-ab-b-tests-for-widgets-15.webp",
        "Replace widget",
        "Replace widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Enter the value in the _Traffic allocation_ field for one of the widgets.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f2306850ea170bcdadcf82f03f5ced2cd0ec24c5a0bfd58aac15df974d687d9a-using-ab-b-tests-for-widgets-16.webp",
        "Traffic allocation",
        "Traffic allocation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> The traffic allocation value specifies the distribution of displays for widgets A and B. The default value is 50% for each widget. This means that the number of displays for both widgets is evenly distributed between all site or page visitors. The minimum value is 1, the maximum value is 99.

6. Click _Start test_.

If your widgets are not published, the Start testing dialog window opens. Select _Publish both widgets and start the test_ and click _Start test_ in the Start testing window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eb8d89a5c96393e56a6e93cc195b8d0139e842c46793c9e1a4bf550b90d235ac-using-ab-b-tests-for-widgets-17.webp",
        "Start testing",
        "Start testing"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


The test shows in the A/B test window with the In progress status.

## Running the A/B Test for 2 Widgets with One Attached to the Launcher

If one of your widgets has the By click on launcher option enabled in the Widget calling settings, you can run an A/B test for 2 widgets attached to that launcher.

When the page visitor clicks the launcher during the test, it will show either widget A or widget B, depending on the traffic allocation values applied.

> 📘 Note
> 
> For this type of test, only one widget must have the By click on launcher option enabled.

To run an A/B test for 2 widgets attached to the same launcher:

1. In the left-hand side panel, select _A/B Tests_ and click the _New test_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/85db0eb15b90a6327cd88fa78a3bee3b434a66964c6e0778f5b6e52eeee60214-using-ab-b-tests-for-widgets-18.webp",
        "Creating a new test",
        "Creating a new test"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In the New test window, enter the test _name_ (required) and test _description_ (optional) into the corresponding fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/43aab740e6c7f5ed5af92bc6da74ebde42ffe9bbe0e63d8e6a61daf6ee6a7c8d-using-ab-b-tests-for-widgets-19.webp",
        "New test window",
        "New test window"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Select widget A_ and select the widget from the list in the Select widget window. This widget **must** have the By click on launcher option enabled.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/598b05da23332829fa28bd4e540be57797938fd4a44d78a1d96a71abac1faefb-using-ab-b-tests-for-widgets-20.webp",
        "Selecting the widget from the list",
        "Selecting the widget from the list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> You can search for the widget using the _Search_ box at the top of the Select widget window:
> 
> - To search by the widget name, enter the widget name or a part of the name into the Search box and click the _Search (magnifying glass)_ icon or press Enter.
> - To search by the widget ID, enter id: followed by space and the widget ID into the Search box and click the _Search (magnifying glass)_ icon or press Enter. For example, id: 8230

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c63083c19f30b113fbd11a1c3bb4af47844446bbfff54abd941a80f7b160080-using-ab-b-tests-for-widgets-21.webp",
        "Searching widgets",
        "Searching widgets"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Select widget B_ and select the widget from the list in the Select widget window. This widget **must not** have the By click on launcher option enabled.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/288c819bd57edefbeada7c5f8f20040625c3ac0df6840d847d1840cfd03cd249-using-ab-b-tests-for-widgets-22.webp",
        "Select widget B",
        "Select widget B"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> To replace the widget, point at the widget, click the _Replace widget_ icon, and select another widget from the list in the Select widget window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/04564024c508c66ce8266a64f041f5b6c0a662876b3459364660bb24e3b3b8c8-using-ab-b-tests-for-widgets-23.webp",
        "Replace widget",
        "Replace widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Enter the value in the Traffic allocation field for one of the widgets.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/92bd7da21203a319b59815abbccaf9ee81e495dbfe901d9cecf469cb90080a2c-using-ab-b-tests-for-widgets-24.webp",
        "Traffic allocation",
        "Traffic allocation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Click _Start test_.

If your widgets are not published, the Start testing dialog window opens. Select _Publish both widgets and start the test_ and click _Start test_ in the Start testing window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/da2f4f78cdc8f2b46ca618f0bb5dd8782911ef2726297a636e92278754e78505-using-ab-b-tests-for-widgets-25.webp",
        "Start testing",
        "Start testing"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


## Running the A/B Test for 2 Variations of a Widget Attached to 2 Variations of a Launcher

If both your widgets have the By click on launcher option enabled in the Widget calling settings, you can run an A/B test for 2 widgets attached to 2 different launchers.

The page visitor will see either of the launchers and their associated widgets depending on the traffic allocation values applied.

In this case, 2 different tests are run automatically:

- Test for launchers.
- Test for widgets.

The statistics data are collected independently for each test.

To run an A/B test for 2 variations of a widget attached to 2 variations of a launcher:

1. In the left-hand side panel, select _A/B tests_ and click the _New test_ button.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8eddaa9089f5a3831e40beb9f68ee4f019c42980654f407c9bcb64860fad62bf-using-ab-b-tests-for-widgets-26.webp",
        "Creating a new test",
        "Creating a new test"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


2. In the _New test_ window, enter the test title and test description into the corresponding fields.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/672b6063467dbf14a59c8aba2f1561f17c1948884e5dc5af8376bf8ee5422d0e-using-ab-b-tests-for-widgets-19.webp",
        "New test window",
        "New test window"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


3. Click _Select widget A_ and select the widget from the list in the Select widget window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/498a979ef34e17dd2e99b5e166c1043017afb4c9d3114a278951403fdf2d8df5-using-ab-b-tests-for-widgets-20.webp",
        "Selecting the widget from the list",
        "Selecting the widget from the list"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


This widget **must** have the By click on launcher option enabled.

> 📘 Note
> 
> You can search for the widget using the _Search_ box at the top of the Select widget window. Or, you can use the _period_ dropdown menu or the _By update_ switch to filter the widgets shown in the list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e4680bbc63e70ec63799714e6c872b814ccab99c4654789e4deca9ee75a431ed-using-ab-b-tests-for-widgets-27.webp",
        "Searching widgets",
        "Searching widgets"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


4. Click _Select widget B_ and select the widget from the list in the Select widget window. This widget **must** have the By click on launcher option enabled.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d9cff293679becb560ba57c7371243f586f6e35c49f28af105c5c979ea1dd5dd-using-ab-b-tests-for-widgets-28.webp",
        "Select widget B",
        "Select widget B"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 📘 Note
> 
> To replace the widget, point at the widget, click the Replace widget icon, and select another widget from the list in the Select widget window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f049e0123ccff879366313b30dd84b9fb71edf2adf668b6512a86fcb05ea79f9-using-ab-b-tests-for-widgets-23.webp",
        "",
        "Replace the widget"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


5. Enter the value in the Traffic allocation field for one of the widgets.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8e004412a477bcf02a79c2dfb10d184ee41d19fe8bf523bd69e093e9facd5e21-using-ab-b-tests-for-widgets-29.webp",
        "Traffic allocation",
        "Traffic allocation"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


6. Click _Start test_.

If your widgets are not published, the Start testing dialog window opens. Select _Publish both widgets and start the test_ and click _Start test_ in the Start testing window.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b05ba10cbf85d4b2940be1502c09ce7a5b128f377fdf9587569c56c059e9b04-using-ab-b-tests-for-widgets-30.webp",
        "Start testing",
        "Start testing"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


Two tests – one for the widgets and one for the launchers – appear in the list of tests in the A/B tests screen.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5879a70f64d23ce30c992446e09d1174fcda30807bbb8feb9a50a2b41a6fdb69-using-ab-b-tests-for-widgets-31.webp",
        "The list of tests",
        "The list of tests"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]