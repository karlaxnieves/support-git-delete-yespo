---
title: Building and Editing Workflows
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Create a Workflow | Yespo Guide
  description: >-
    Learn how to create basic or complex workflows and set up sending
    conditions. A workflow is an automated email or series of emails with a
    single marketing purpose.
  robots: index
next:
  description: ''
---
Workflows allow you to automate sending your notifications through different channels. You can configure delivery to a single contact or to a segment.

Yespo offers a drag-and-drop builder for building workflows. The builder uses pre-programmed configurable blocks which you can place and connect into a workflow, and assign tasks and conditions to them.

> 📘 Note
>
> Read about [workflow blocks](https://docs.yespo.io/docs/introduction-to-workflows#workflow-blocks) before you start building and editing workflow.

## Creating a New Workflow

To create a new workflow:

1. Go to **Automation → Workflows** and click **New workflow**.

<Image align="center" width="80% " src="https://files.readme.io/77f7c614b97d978b1878d3ec9e5a882d02840781bd6826598499a26d1370253d-building-and-editing-workflows-001.webp" />

2. Enter the workflow **name** (required) and add [tags](https://docs.yespo.io/docs/how-add-tags) (optional).

<Image align="center" width="80% " src="https://files.readme.io/b13bd1ebf63e937a8325ad68170f7331ae57ad65d1e559ce0155b09a62e1dfcc-building-workflows-01.webp" />

3. Add and set up the necessary blocks.

Each workflow contains the required blocks:

* [Start](https://docs.yespo.io/docs/start-block). This block is automatically added at the beginning of a workflow.
* [End](https://docs.yespo.io/docs/popular-blocks#end). Place this block at the end of a workflow branch.

4. After adding all the necessary blocks, save the workflow by selecting one of the following options:

From the dropdown menu:

* **Save** — without exiting the editor.
* **Save and exit** — returns you to the list of workflows.
* **Save and launch one time** — runs the workflow one time.

<Image align="center" width="80% " src="https://files.readme.io/a493b970367b7179b8593750848d9b820d170759ce08b9a244edd8b6720f4b1c-image001.webp" />

On the top toolbar:

**Save and launch test** — performs a test run of the workflow.

<Image align="center" width="80% " src="https://files.readme.io/912ac1b1b1bdc5c334f89814cf1d70895afbda5f47daa638a38bab237a16db7b-image002.webp" />

## Managing Blocks

Let's consider the actions that you can do with the blocks.

### Adding Blocks

You can add blocks to your workflow in two ways:

1. Left-click the necessary block. It is automatically connected to the previous block. If the previous block is a condition that has two branches – green and red – the next block is connected first to the green branch.
2. Drag a block and connect it manually to any block.

<Image align="center" width="80% " src="https://files.readme.io/f6fd236459b16d55bbafad3169d258189f17df301013b3371229b534676cd0e6-building-and-editing-workflows-0003.gif" />

### Deleting Blocks

To delete a block, select it and click the trash icon above it or in the top panel. You can also press **Delete** on your keyboard.

<Image align="center" width="80% " src="https://files.readme.io/1f33df7aa64613e7e9f9514c44f08a01e97cc299f25ade88c5cb115a5fe9bf01-building-workflows-03.webp" />

To delete a connection between blocks, select it (the color of the connection points changes to blue) and press **Delete** on the keyboard.

<Image align="center" width="80% " src="https://files.readme.io/5b87a34ae3eae0cee2225aa5a3855b89b5e20617b0a2167d1fe4f1e4c8f25ae6-building-workflows-04.webp" />

To select a few blocks and connections, press the **Shift** key on the keyboard and select the necessary workflow fragment.

To select all blocks and connections, press **Ctrl+A** on the keyboard.

### Undo Actions

To undo the previous action or redo the undone action, click the arrow icons on the top panel or press on the keyboard:

* **Ctrl + Z** — undo the previous action.
* **Ctrl + Y** — redo the undone action.

<Image align="center" width="80% " src="https://files.readme.io/4f6f54c4533774e4bed1489415a8eacf8c65148090cd9579602d53f79515db3f-building-workflows-05.webp" />

### Additional Block Settings

The blocks requiring additional settings have an orange alert label mark. Select a block and configure its settings in the right-hand side panel. Learn more about the block settings in the instructions for each block group.

<Image align="center" width="80% " src="https://files.readme.io/fa813f167d80499c349145090479871bc7273da8c35362c8542b974fee2f699e-building-workflows-06.webp" />

To expand or collapse the block panel, click **\[** on the keyboard or **angle brackets** icon in the drag-and-drop builder.

<Image align="center" width="80% " src="https://files.readme.io/0a05a45a0eca53ffce0a668bba3ebbeb15edb3b118ef8bad979c1d83b90e0f35-building-workflows-07.webp" />

## Workflow Description

The description of a workflow in the system helps mark workflows with brief information about their purpose and key actions.

Click the **Workflow description** icon and add the necessary information.

<Image align="center" width="80% " src="https://files.readme.io/76736fbe70c20ba48a28b3693fcf6c5ef32bc4b7e038218b8aa4f81e50f7c627-building-workflows-09.webp" />

In the menu, the description appears in a tooltip when you hover over the icon.

<Image align="center" width="80% " src="https://files.readme.io/8a4e741fb6f8470eb3215be9fdc514a064b0d90cdd3ce96d8fb29a1fb565e59b-building-workflows-10.webp" />

## Copying Blocks & Workflows

You can duplicate blocks in a workflow so that a duplicated block has the same configuration as the original one.

You can also copy selected blocks from one workflow to another and create a new workflow containing the blocks from an existing workflow.

To duplicate a block, select the block and click the Copy icon above it or in the top panel. You can use **Ctrl + C / Ctrl + V** combinations on your keyboard.

<Image align="center" width="80% " src="https://files.readme.io/b757d7ccfc5cc7568fbf11ec437daa332b42f855dd8c120d9cfec62af5a025f6-building-workflows-08.webp" />

To copy the selected blocks from one workflow to another:

1. Open two workflows in different tabs.
2. Using your mouse, select the blocks in the workflow you want to copy or press **Ctrl + C** on your keyboard.
3. Go to another workflow and paste the copied blocks by pressing **Ctrl + V** on your keyboard.

To copy workflow:

1. Go to **Automation** → **Workflows**.
2. Select the ellipses (three dots) icon beside the workflow you want to copy.
3. Select **Copy** from the dropdown list.

A new workflow window appears containing the blocks from the copied workflow. You can edit and save it.

<Image align="center" width="80% " src="https://files.readme.io/c5a3329e01fb9072e38b0c66a97bc85b72531faef7f27a38c2892de56d45b732-building-and-editing-workflows-202.webp" />

> 📘 Note
>
> For more convenient selection and copying of blocks, you can use the **Ctrl/command** keys

## Setting up Workflow Start/Stop Configuration

In addition to settings you can apply to workflow blocks, you can set up start/stop configuration for your workflow.

Read [Configuring Workflow Start/Stop Conditions](https://docs.yespo.io/docs/configuring-workflow-start-stop-conditions) to learn more.

## Testing Workflow

There are two ways to check the correctness of the workflow:

A. In the editor while creating or editing a workflow (the **Save and launch test** button):

<Image align="center" width="80% " src="https://files.readme.io/f73d070ae8a5f3fe0cd7ba2a9ebf2c1f6f61a751a0081df7589617693e62a07d-image004.webp" />

B. In the general workflow list (the **Launch test** option):

<Image align="center" width="80% " src="https://files.readme.io/1d723144489513b98ecc81ecf34e7a0d7fbe4788a206972d9f369748d6afb423-image003.webp" />

After selecting the way, select one of the testing options:

* Start for a contact
* Start with event

<Image align="center" width="80% " src="https://files.readme.io/922753a128faefb388acb44c66ccb53fd7910bca4d9acdea7bdab6c2a601d1e2-testing_8.png" />

### Start for a Contact

Click **Select contact** and select the contact from the list.

<Image align="center" width="80% " src="https://files.readme.io/c141abc11bcb250024c5d3d6eb2842c655b209eb6556391115af3e4dcf2108ca-testing_7.png" />

If the workflow uses event parameters, select the event from the list.

<Image align="center" width="80% " src="https://files.readme.io/3736ab2663e7e4a2ecaa82c904bf3a328f7ca70c5c1d6759a30ae40603384b77-testing_1.png" />

If variables are specified in the workflow blocks, specify their values ​​in the corresponding fields.

<Image align="center" width="80% " src="https://files.readme.io/2892f8594bf72792ff46c52d989bd5c3bec51bd7460161bf3db4d335d0188858-testing_6.png" />

Click **Launch**.

<Image align="center" width="80% " src="https://files.readme.io/6201fe21a81c3c100259b217828819a4f6619fb1aff424ac5520c08b9b13b620-testing_3.png" />

### Start with Event

Paste the event parameters in JSON format into the appropriate field and click **Launch**.

<Image align="center" width="80% " src="https://files.readme.io/cf4fc71c273581535210b26a16632e68f4b05fbbea04e02b14befb2773f9fe1a-testing_5.png" />

After a workflow test run, check [the history of its launches](https://docs.yespo.io/docs/using-workflow-launch-history) and/or the messages received through the workflow.

## Activating and Deactivating Workflows

You need to activate your workflow, so it can start automatically in accordance with the launch conditions.

To activate a workflow:

1. Go to **Automation → Workflows**, and select **Not active** in the menu on the left-hand side.

<Image align="center" width="80% " src="https://files.readme.io/ba3ca17a25ffe4e27469640e746661a9e352f3546b62f3a20eadd0a2d9570895-building-and-editing-workflows-203.webp" />

2. Click the **Activate** icon beside the workflow you want to activate.

<Image align="center" width="80% " src="https://files.readme.io/f48cc30ef884b32f7ae0497e49358e4039e557107b85db33d9472f5e4f0b4250-building-and-editing-workflows-204.webp" />

To deactivate a workflow:

Go to **Automation** → **Workflows** → **Active** and click the **Deactivate** icon beside the workflow you want to deactivate.

<Image align="center" width="80% " src="https://files.readme.io/c65b4b45cec9d8d3fc9f060bf86eeb1e1a3f3d87dae459098f43e1b1f3854188-building-and-editing-workflows-205.webp" />

## Viewing Workflow Statistics

The **Statistics** icon beside a workflow opens a dropdown list of options. You can choose the following options:

* **In progress**. This item opens the list of all the currently running workflows.
* **Completed**. This item opens the list of all the completed workflows.
* **With errors**. The workflows during which an error occurred.
* **Launched per 7 days**. This item opens the list of the workflows launched during the last 7 days.
* **Launched statuses per segment**. This item opens the details of workflows launched for the segments of contacts.

<Image align="center" width="80% " src="https://files.readme.io/4fe446675e41ca8057d3962af0fd69cb27edf19fb329e33512cbe729e1863cdc-image004.webp" />

When you select one of the first three items, you can view the launch history of your workflows and check for any errors in their blocks. You can also preview the workflows. Read [Using Workflow Launch History](https://docs.yespo.io/docs/using-workflow-launch-history) to learn more.

## Search and Filter Workflows

To find a workflow, use the search bar by name, [tag](https://docs.yespo.io/docs/how-add-tags), or workflow ID

<Image align="center" width="80% " src="https://files.readme.io/4def771f7d782eaf73ad63c37d9139a025da49e08d4d2d7b8bcc2eb30aea699c-building-and-editing-workflows-207.webp" />

To filter workflows by activity, click the corresponding tab in the menu on the left:

* All workflows (shows workflows with all statuses)
* Active
* Not active

<Image align="center" width="80% " src="https://files.readme.io/1eeda255f8bbc5e95fe7d5fb10443cd02041b3694a4457d23dd95e68e208ba21-building-and-editing-workflows-208.webp" />