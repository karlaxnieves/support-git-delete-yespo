---
title: Linking Workflow to the Button
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to add the workflow to the button in the CDP | Yespo Guide
  description: >-
    Step-by-step guide how to create an event, set up the workflow based on the
    event, and add the workflow to the button in your email campaign.
  robots: index
next:
  description: ''
---
The algorithm for linking a workflow to the button is universal. We will illustrate it with the example of a campaign for segmenting contacts.

Let us suppose that you have a quite large contact database but you don’t know anything but email addresses about your subscribers. If you don’t want to annoy them with trifles but send only the relevant content you need to know their interests and expectations. For this purpose, we send subscriber a trigger email that contains request to tell more about himself/herself and a special workflow attached to it.

## Basic segmentation

The simplest example is an email with the question: *What kind of clothes are you interested in?* A contact could click on one of three buttons: *Men's*, *Women's*, or *All*. Your goal is to build a workflow to add contacts to segments when they click the buttons in the email.

Each workflow must be linked to a certain event. You can pass events via API or [create them in our system manually](https://docs.yespo.io/docs/creating-events).

## 1\. Creating an Event Type

1. Go to *Automation → Event types* and click *New event type*.

<Image align="center" width="80% " src="https://files.readme.io/f92be4036168a6176fe4636b0f5a3ab484b686585080131a3eeeaad0dd02e3f7-linking-workflow-to-the-button-001.webp" />

2. In the *New event type* window add an event name and select a category.

<Image align="center" width="80% " src="https://files.readme.io/e05a8b1f2c32b8f34b795f556e493febac7ba8bb2151fe29c0f49a5ff86d56ae-linking-workflow-to-the-button-002.webp" />

> 📘 Note
>
> For the *Click* category be sure to specify the key in the corresponding field. The key is any value/word, preferably written without using numbers. For example: action, click, etc.

3. Click *Add*.

## 2\. Linking Event to the Button

1. Open the email with a questionnaire in the editor.
2. Click on each button with the answer option and link an event to it. Select the corresponding one from the dropdown list.

<Image align="center" width="80% " src="https://files.readme.io/4d3af0376cc60765d9e3c8654b8dbbbabbf654277597e743a5a419c47dc730ec-linking-workflow-to-the-button-003.webp" />

## 3\. Setting Up Workflow

1. Go to *Automation* → *Workflows* and click *New workflow*.

<Image align="center" width="80% " src="https://files.readme.io/aadd8b5c282c439490ed183295dd13b25ae9b13f8cd70617c0dca65ecec6a852-linking-workflow-to-the-button-004.webp" />

2. Enter the title and add tags (optionally) of the workflow.
3. Build a chain of actions:

* Start
* Add to segment
* End

In the *Add to segment* block, select the group to add contacts to.

<Image align="center" width="80% " src="https://files.readme.io/cb32c974c2b800ac85e2d4466061631a9bd66d476821b8701ef52e611b4c0cd1-linking-workflow-to-the-button-009.webp" />

You can add more actions to such a workflow, for example — send a message after adding to the segment.

<Image align="center" width="80% " src="https://files.readme.io/213c7a007cdcadf202e90ba43649edcedd16ef2738aea0511e42abe27fb25848-linking-workflow-to-the-button-006a.webp" />

4. Click *Save and exit*.
5. Go to *Start/Stop configuration*.

<Image align="center" width="80% " src="https://files.readme.io/f9611ba565391541f464fb770cced134972aaac5f70e68ce5770b0ad41cf3c76-linking-workflow-to-the-button-201.webp" />

6. In *Start configuration*, select *Event-based* and select the event in *Event* field. Set up processing unique events (in this case, we recommend you the once option).
7. Click *Apply*.

<Image align="center" width="80% " src="https://files.readme.io/b958d16cb703c0c0df754dd444b6e614b055d44cdf771c913b6df750ccf61ec9-linking-workflow-to-the-button-007a.webp" />

> 📘 Important
>
> If you want the contact to receive an email with recommendations immediately after the workflow is executed, set the \_Once in every \_\_*parameter in the\_Process unique events*  field. If this parameter is not specified, and a subscriber accidentally clicks the button several times, the scenario will run anyway, sending several identical messages to one person.

8. Click the *Activate* button.

<Image align="center" width="80% " src="https://files.readme.io/f2122891328f6cc571b3334e08b35bdfbd6e6974167462a51e8583eed65b27c2-linking-workflow-to-the-button-202.webp" />

Each contact who clicks on the button will be added to the segment specified in the workflow. This way, you will get the target audience segments for emailing campaigns with relevant content. Using the same principles you can generate new events arranging much more complex workflows and adding them to buttons, pics, and even text links in your messages.
