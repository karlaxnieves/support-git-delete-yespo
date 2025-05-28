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

1. Go to *Automation → Workflows*.
2. Click the *Statistics* icon of the workflow and select one of the items from the dropdown menu:

* In progress
* Completed
* Launched per 7 days

<Image align="center" width="80% " src="https://files.readme.io/757f563dee80b17daaaea238fd906734aa56ee6138fa1312d588bc979ea4560e-workflow-launch-history-301.webp" />

## Launch History

Launch history contains the following data:

1. Launches — individual instances of the same workflow; each is independent and may have different results.
2. The blocks that are activated in each launch.
3. Information about the parameters of the blocks.

<Image align="center" width="80% " src="https://files.readme.io/9dc95b78515f187920510c0633260ff07f4aaac39f52567fa6d1795dfff69b69-workflow-launch-history-01.webp" />

If you selected the *In progress* or *Completed* items, the tabs will be displayed on the left:

<Image align="center" width="80% " src="https://files.readme.io/3c8123f366f3ac241a08a5b0070526f84c8218733af06561f96ee9ed6c529965-workflow-launch-history-02.webp" />

## Workflow Launch Viewing

1. Select an instance of the workflow in the *Launches* column.

<Image align="center" width="80% " src="https://files.readme.io/3027ea2b6b748943dec044fa07e0ec6c73a95938399b404a547e3efb038ad397-workflow-launch-history-03.webp" />

2. Hover over the launch and click the *view* icon.

<Image align="center" width="80% " src="https://files.readme.io/0f088262e118789b9745fb0928840a9f985b8c15c06c23d3ac800fd291dd6535-workflow-launch-history-04.webp" />

3. The *Workflow's launch view* window will open.

<Image align="center" width="80% " src="https://files.readme.io/31fb629c4361e8f807420722a2f0494dd1bf67f8d3abb1ee000911f85e2e85c8-workflow-launch-history-306.webp" />

The execution path for that launch is highlighted in blue.

Click the three-dot icon to view the campaign reports.

<Image align="center" width="80% " src="https://files.readme.io/d28687e83226572db3c36542a0af36b54eefbf015a039a914b5c4239c4a207b1-workflow-launch-history-307.webp" />

> 📘 Note
>
> The report opens based on the channel used for the first send. For example, the report will show the email campaign if the first send was an email message. [More details about the campaign reports >](https://docs.yespo.io/docs/campaigns-analytics)

The *Refresh* button allows you to manually update data for launches and blocks with the *In progress* and *Completed* statuses.

<Image align="center" width="80% " src="https://files.readme.io/0e70fab1ee51d0bc1e0be2f63276abf883588edaeeb1bd115e3c37e3854b6e00-workflow-launch-history-13.webp" />

### Launch Errors

Workflows and their blocks with errors are marked with a warning icon.

Click on the instance of the workflow with an error, and then select the block with the error.

<Image align="center" width="80% " src="https://files.readme.io/369d9471381b7d115247e2b1162563e01985e5d2c9f9a747684dea6f03e4dece-workflow-launch-history-14.webp" />

The block parameters will be displayed with a red error description to the right of the *Blocks* column.

<Image align="center" width="80% " src="https://files.readme.io/a51c20aa84d20acf46656f788cca5dbbfefb1b0e60f43608309f11f7412ab0ca-workflow-launch-history-06.webp" />

## Search and Filter Launches

To search for a launch, scroll down the list in the column and click the *Show more launches* button.

<Image align="center" width="80% " src="https://files.readme.io/bf0c7b348880db03f86237fc160b7d59bd6670a653a6d0298addc53a09db97ed-workflow-launch-history-07.webp" />

Or use the search bar by parameter.

<Image align="center" width="80% " src="https://files.readme.io/db838068d3cbe192eabe48f7fa86df876ef0e9a442ef84c7f27d3d96cc0c1620-workflow-launch-history-08.webp" />

Use the *Period* tab to filter launches by time.

<Image align="center" width="80% " src="https://files.readme.io/f0a7e6bf6cff6b5497d8c5f71c91d368fed4cbc88840ad04efbe350ced83d836-workflow-launch-history-09.webp" />

## Stopping Instance

Stopping an instance of the workflow may be necessary in cases where errors have occurred, the launch is no longer relevant, changes need to be made, etc.

1. Go to the In progress tab, hover over the instance, and click the Stop icon.

<Image align="center" width="80% " src="https://files.readme.io/9b4631f196adec932ee4af259287e389c04d298af2a6e98226a9ae554387674b-workflow-launch-history-10.webp" />

2. Confirm the action.

<Image align="center" width="80% " src="https://files.readme.io/16d83c7bb9800d7bb6767617b0cea22f0fd0a1df303b5b18c89df316eb6ad221-workflow-launch-history-11.webp" />

To stop all instances, click *Stop all*.

<Image align="center" width="80% " src="https://files.readme.io/3b3b7beb2c935bb73a074514164a32e1984d8c48517184252f37e74a19ee935f-workflow-launch-history-12.webp" />
