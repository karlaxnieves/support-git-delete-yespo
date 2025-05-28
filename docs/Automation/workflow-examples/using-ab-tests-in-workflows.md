---
title: Using A/B Tests In Workflows
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Using A/B Tests In Workflows | Yespo Guide
  description: >-
    Learn about A/B testing in workflows to optimize triggered messages. Test
    text, calls to action, images, and channels for audience preferences and
    behavior
  robots: index
next:
  description: ''
---
A/B testing helps validate hypotheses and understand the preferences and behavior of the target audience

Built-in functionality allows testing:

* [email subject lines](https://docs.yespo.io/docs/how-test-email-subject-lines),
* [widget displays](https://docs.yespo.io/docs/using-a-b-tests-for-widgets),
* [product recommendations](https://docs.yespo.io/docs/testing-recommendation-blocks).

Using workflows, you can test the effectiveness of various elements of triggered messages, such as text, calls to action, images, or sending via different channels.

Use the *Split* block from the *Conditions* blocks for split testing.

<Image align="center" width="80% " src="https://files.readme.io/32a9ed92fd46d704815b697c6527545f4034c7e0b1b7c2207d5829b0adeaf569-using-ab-tests-in-workflows-01.webp" />

Let's consider an experiment using the example of an abandoned cart:

* The first message contains a discount on items abandoned in the cart:

<Image align="center" width="80% " src="https://files.readme.io/5ae24b3e3c3aa3792a4cfbee0ca2fe8aa4ad6461e31b4b12a72e49eeabb0fcc9-using-ab-tests-in-workflows-02.webp" />

* The second message contains a [timer](https://docs.yespo.io/docs/creating-timer) with a countdown until the end of the discount.

<Image align="center" width="80% " src="https://files.readme.io/7073e0fb49e38ca74006e68df332466c34c4e2e8244d06fe2e8d1568fc5d4517-using-ab-tests-in-workflows-03.webp" />

The goal of this test is to check whether a timer counting down the time until the end of the promotion influences the purchase decision.

## Creating a Workflow for Testing

1. Go to *Triggers → Workflows*, and click the *New workflow* button.

<Image align="center" width="80% " src="https://files.readme.io/1d7cf2f703ef187839df2c996be7a576df98e29daf3a46b55c4fd8c991d59a90-using-ab-tests-in-workflows-04.webp" />

2. Enter its name and [tags](https://docs.yespo.io/docs/adding-tags#adding-tags-to-the-workflow) (optionally).

<Image align="center" width="80% " src="https://files.readme.io/1068fe4dd9ca28d74c0068677338f84380d0091520155b43ad0d9abe0724f6b9-using-ab-tests-in-workflows-05.webp" />

3. By default, the *Start* block already starts the workflow. Then add blocks:

* [Split](https://docs.yespo.io/docs/blocks-description-conditions-group#split), where contacts are automatically distributed between workflow branches 50/50. To change the ratio, drag the slider in the block settings to the left or right.

<Image align="center" width="80% " src="https://files.readme.io/1e2d4ecb1afcf2f88f7400ce13caf42f56e00a2108dae750fe7d07d8dad2912a-using-ab-tests-in-workflows-06.webp" />

* Email for A and B branches; select the message in the block parameters.

<Image align="center" width="80% " src="https://files.readme.io/e7c9b8b504ecd1c6bd674eaae942b37bd67e2667f57bfb6647ce8af801617a3b-using-ab-tests-in-workflows-07.webp" />

* End.

The workflow will look like this:

<Image align="center" width="80% " src="https://files.readme.io/50c01d298f94437a8c43982fa28e57367bb0a3f981f8098ff090f6d7ae9a50e4-using-ab-tests-in-workflows-08.webp" />

4. Click *Save and exit*. 

After launching the workflow, the system will randomly distribute contacts between two branches in a 50-50 ratio. Each contact will receive only one message, according to the branch they fall into.

## Setting Up Workflow Launch and Checking Results

1. Go to *Triggers → Workflows* and click *Start/Stop configuration* in the field of the created workflow.

<Image align="center" width="80% " src="https://files.readme.io/5db0064fb95b358a721e41377ade37705d80198d92fef4634c1c10c1c7935de9-a-b-test-en-201.webp" />

2. Enable the *Start Configuration* slide button, select *Regular*, and a dynamic segment for the campaign.

<Image align="center" width="80% " src="https://files.readme.io/aa6572f6c6b8c867c4a3ae97da108e5cd09cc2166cba148fd2d6e3aa054e7e30-using-ab-tests-in-workflows-10.webp" />

3. Configure launch conditions and click *Apply*.
4. Activate the workflow.

<Image align="center" width="80% " src="https://files.readme.io/be0c401aea37ab20df606ee179d3f43731b1abb187684105dc0c510f72089a74-a-b-test-en-202.webp" />

Later, you will be able to check and compare the test results.

To do this:

1. Click three dots in the field of the created workflow and select *View campaign report*.

<Image align="center" width="80% " src="https://files.readme.io/9d66c7eab46b2b119d40744a0096e2f8bc5da1264ed331371dbcbf34e1655c3f-a-b-test-en-203.webp" />

2. Choose a period and compare the indicators for each message.

<Image align="center" width="80% " src="https://files.readme.io/461b9fb334a106189594f1923e4a3e97cb1c3eb90f6d4b500ce2e1c152b5090b-using-ab-tests-in-workflows-13.webp" />
