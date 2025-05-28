---
title: Workflow Troubleshooting
excerpt: >-
  If you have some problems with the workflow functioning, check the following
  typical setup issues
deprecated: false
hidden: false
metadata:
  title: Workflow Troubleshooting | Yespo Guide
  description: >-
    The document provides troubleshooting steps for workflow issues, including
    checking the workflow's active status, event triggers, workflow settings,
    and user contact information, with a recommendation to contact support if
    problems persist.
  robots: index
next:
  description: ''
---
If you have some problems with the workflow functioning, check the following typical setup issues.

## Workflow Does Not Launch

1. Check your workflow status in the workflow list (*Automation* → *Workflows*).

It should be *Active* (a green indicator is displayed next to the name).

<Image align="center" width="80% " src="https://files.readme.io/5e692c5636bd4ad388222c3cec32fc53cc1542a2cf0e3b1daf14f5928cf0310b-workflow-troubleshooting-201.webp" />

If it’s *Not active*, click the *Activate* button.

<Image align="center" width="80% " src="https://files.readme.io/5ecbd9de356cd827554e4782aa2a4a444dec1a7ec59dca7722591fa47a26f038-workflow-troubleshooting-202.webp" />

2. Check the event launching a workflow. If the workflow should be launched by the event transferred via API, make sure you transfer it and select it in the dropdown list in the *Start configuration*.

<Image align="center" width="80% " src="https://files.readme.io/fbbefd12fc22f3f96e2c7e7f57e6ed9a1eae8f04f178c64f8bac0a3449a0a100-workflow-troubleshooting-203.webp" />

3. Check if the workflow launches were registered in the system.

See the workflow statistics.

<Image align="center" width="80% " src="https://files.readme.io/385c2753ee2d2df99d725cf16798fcc387eeefe5dd2906f525509468f958968f-workflow-troubleshooting-204.webp" />

If all statistics values are zero, the workflow was never run.

4. Make sure there is an event that should launch the workflow in *Automation → Event History*. See whether the event is linked with the corresponding workflow.

<Image align="center" width="80% " src="https://files.readme.io/9aee94bc82ec51f3701e22b8bda6307cbccc27f12215d5cb6855c20876fd08f0-workflow-troubleshooting-205.webp" />

5. If the [event is triggered by clicking on the button](https://docs.yespo.io/docs/how-add-scenario-button) in the message, check whether the event and the button are linked.

<Image align="center" width="80% " src="https://files.readme.io/15c1acddf3fe390a5f7e90a52e233c1f851625982b361d7b3af408a39ced7fc0-workflow-troubleshooting-006.webp" />

Ensure that events in trigger configuration and in the message corresponding to each other.

<Image align="center" width="80% " src="https://files.readme.io/8d6a1fce495ee8a7a29514971c4b8c0992a477a75050c680f10bd26ac310419f-workflow-troubleshooting-206.webp" />

## Workflow Launch, but Works Incorrectly

1. Check the settings of the workflow blocks.

Enter the workflow, click on each block and inspect its settings:

* Have you selected the message in the *Message* field?

<Image align="center" width="80% " src="https://files.readme.io/38f49801bc63e84102a4bb838f9185f1855c0411ee30e46327750ffc28146214-workflow-troubleshooting-008a.webp" />

* Have you specified the correct variable in the *Email* field?

<Image align="center" width="80% " src="https://files.readme.io/9ac0ff8118243579f501f6d5ac6fc74a67b61006ca7b01b37e893e948704fb6f-workflow-troubleshooting-009a.webp" />

It should match the variable you pass in the event (you can see your event parameters in *Automation* → *Event history*).

<Image align="center" width="80% " src="https://files.readme.io/0e97743e875a297e483fd08f96efb79812379c0d6252710b9d06c06870913fb8-workflow-troubleshooting-010.webp" />

2. Check the correctness of the workflow structure. All blocks should be connected to each other. For example, a common mistake is to connect two blocks through another one.

<Image align="center" width="80% " src="https://files.readme.io/6da9fbc8729fb6002ee62d77e1f013a92fbc7ea2230bf1d1ac5c559e75afc76e-workflow-troubleshooting-011.webp" />

3. If all settings are correct, but some users didn’t receive the messages from the workflow, inspect the contact information of these users.

Maybe they are unsubscribed, blacklisted, over your sending limit, and so on. You can see this information in the *Campaigns* → *Single reports* section. Enter the contact ID in the search bar and see the details of delivery errors. Also, you can see contact information in *Contacts* → *All contacts* section.

<Image align="center" width="80% " src="https://files.readme.io/8f40139072296e7673fbec95e806bc3995eb548bda867f869c2b8a6df5887cc0-workflow-troubleshooting-012.webp" />

***

These are the basic settings that you should check if you encounter problems. If, after review, you still have troubles, please contact our support team.
