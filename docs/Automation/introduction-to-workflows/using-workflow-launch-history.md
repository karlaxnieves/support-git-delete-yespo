---
title: Using Workflow Launch History
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using workflow launch history | Yespo Guide
  description: >-
    Learn how to use Workflow Launch History to monitor workflow performance.
    Track launch statistics, identify errors in blocks, and optimize your
    marketing automation processes with detailed insights.
  robots: index
next:
  description: ''
---
Track statistics on the number of workflow launches and check for errors in its blocks.

1. Go to **Automation** → **Workflows**.
2. Click the **Launches** icon of the workflow and select one of the items from the dropdown menu:

* In progress
* Completed
* With errors
* Last 7 days
* Launch statuses per segment (available only in [regular workflows for a segment](https://docs.yespo.io/docs/how-launch-regular-workflow-segment-support#/)).

<Image align="center" width="80% " src="https://files.readme.io/1c6b8282f8bda694b83073c333b4caa4b1acd148175338c374eebd03425fdb02-image001.webp" />

When you select the **Launch statuses per segment** option, a side panel will open with information:

* Group ID
* Workflow launch date and time
* Number of contacts in the segment
* Launch status

<Image align="center" width="80% " src="https://files.readme.io/cc15059fe355fbf9573dbbca74bd8fde9e4f4a99856b0f638271a07d543d09ba-image002.webp" />

To view the contacts included in the segment, click the **preview** icon.

## Launch History

Launch history contains the following data:

1. Launches — individual instances of the same workflow; each is independent and may have different results.
2. The blocks that are activated in each launch.
3. Information about the parameters of the blocks.

<Image align="center" width="80% " src="https://files.readme.io/97bc1e7b4892505672234c85e4cbfa70cd0340f1746936c5a0b27e7ec0b05b6a-history_2.png" />

The following tabs are displayed on the left:

* In progress
* Completed
* With errors

<Image align="center" width="80% " src="https://files.readme.io/44c3695a5deb85591ed22054ef9439de2f229684d93fe46d4bd2f415441dcb90-history_3.png" />

## Workflow Launch Viewing

1. Hover over the launch and click the **view** icon.

<Image align="center" width="80% " src="https://files.readme.io/de4deba1081789607596ffb0c32c2681e08b84bfd9aab19e47c7a9ac5f06045f-history_12.png" />

3. The **Workflow's launch view** window will open.

<Image align="center" width="80% " src="https://files.readme.io/667c65e3ac5937db122bebb01c408ab5abd141d1f5031aef27ecdf7c2fb6aeee-preview.png" />

The execution path for that launch is highlighted in blue.

Click the three-dot icon to view the campaign reports.

<Image align="center" width="80% " src="https://files.readme.io/c92088d99528549f31f24444e91d5abc27cc2ad0267c9af6cc139a68272e99fe-report.png" />

> 📘 Note
>
> The report opens based on the channel used for the first send. For example, the report will show the email campaign if the first send was an email message. [More details about the campaign reports >](https://docs.yespo.io/docs/campaigns-analytics)

The **Refresh** button allows you to manually update data for launches and blocks with the **In progress** and **Completed** statuses.

<Image align="center" width="80% " src="https://files.readme.io/bc5cb8edb5e41f0fdf9bae93678ebf436b069b62982e27b5ceac6f145ad94aa4-history_7.png" />

### Launch Errors

Workflows and their blocks with errors are marked with a warning icon.

Click on the instance of the workflow with an error, and then select the block with the error.

The block parameters will be displayed with a red error description to the right of the **Blocks** column.

<Image align="center" width="80% " src="https://files.readme.io/a454c9cd81a4301f495e83aba6887eb757ed3c3a65e1fd0da2b81c84a156f55f-history_8.png" />

## Search and Filter Launches

To search for a launch, scroll down the list in the column and click the **Show more launches** button.

<Image align="center" width="80% " src="https://files.readme.io/dcef25d5a29da34f8d2f83497f6a34b6828bc24ccda76aecf7669b1b7f4bddcb-history_9.png" />

Or use the search bar by parameter.

<Image align="center" width="80% " src="https://files.readme.io/a8f05bab16fd8a966ec3767fa10d46e3c04368974995eda83e80007099e53ea3-history_10.png" />

Use the **All existing launches** tab to filter launches by time.

<Image align="center" width="80% " src="https://files.readme.io/d5e2f525a4772a5e0d1670de3c3188ca13527e853d2a0e8ba3f83e2fba9698f0-period.png" />

## Stopping Instance

Stopping an instance of the workflow may be necessary in cases where errors have occurred, the launch is no longer relevant, changes need to be made, etc.

1. Go to the **In progress** tab, hover over the instance, and click the **Stop** icon.

<Image align="center" width="80% " src="https://files.readme.io/e676071fd153d612a74ee1441d7e450e4bb9afd0e5c7c23c762c9eabf1849a52-history_4.png" />

2. Confirm the action.

<Image align="center" width="80% " src="https://files.readme.io/f79dc492b818686c327ee31c02d6dcb228f5042b05cbda722298da937b68a5e3-history_13.png" />

To stop all instances, click **Stop all**.

<Image align="center" width="80% " src="https://files.readme.io/991dc9a93cc04f36a4b108cf035035fa29494aa746f8d96493cea811f79bae3d-history_14.png" />