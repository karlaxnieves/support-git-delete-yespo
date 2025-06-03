---
title: Birthday Campaign
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Set Up an Automated Birthday Campaign | Yespo Guide
  description: >-
    Learn how to create and send bulk and triggered birthday campaigns. Make
    sure your customers get the right message on their special day.
  robots: index
next:
  description: ''
---
Automate your birthday campaigns so that each contact gets greetings or discount offers on the right day. You can schedule campaign send time before the actual date to give customers time to take advantage of your offer.

In the system, you can set up a birthday campaign in two ways:

* send it to a segment;
* include it in a workflow.

Before getting started with settings, you need to [create a birthday campaign](https://docs.yespo.io/docs/designing-your-email) and save it in the system.

<Image align="center" width="80% " src="https://files.readme.io/ce19f49358d8cba212e3f4a4a7c7e54c8a04b2582a69199a2304f7661470dae6-image20.webp" />

You also need to [import contacts](https://docs.yespo.io/docs/file-uploading). Make sure to check the correctness and validity of the contact data: name, email address, date of birth, phone number (for SMS and Viber campaigns).

## Sending a Birthday Campaign to a Segment

1. Go to *Contacts → Segments*, and click *Add a segment*.

<Image align="center" width="80% " src="https://files.readme.io/654802fcf70c452b934c848557c3d84945870b22a073a6fde9793c2da4e44cda-birthday-campaign-01.webp" />

2. Choose *Dynamic*, and click *Create*.

<Image align="center" width="80% " src="https://files.readme.io/a1a8c480ed034f7f8ff73e58442c4eeca6a84a7c9ed63719ecd980f0a6b3cd5d-birthday-campaign-02.webp" />

3. Fill in general properties:
   * Name (required) — displayed in the general segment list.
   * Purpose (optional) — specify how the campaigns will be used. For example, for triggered emails, regular promo campaigns, etc.
   * [Tags](https://docs.yespo.io/docs/how-add-tags) (optional) — select from the list or add a new one for quick filtering and segment search.
4. Click *Next*.

<Image align="center" width="80% " src="https://files.readme.io/9972f3601b8a51f7f5a2b12ccfa5ac5da6254de91875c0b0350c6a6b07366c31-birthday-campaign-segment-en.webp" />

5. Click *Add card*. In *Fields → Personal  → Date of birth*, choose *today*.

<Image align="center" width="80% " src="https://files.readme.io/f194999e2c36d950035ae9e3162a56dd7e8f7ba7c626b9ea287eb021246f4dfd-birthday-campaign-004.webp" />

6. To see all the contacts included in the segment, click *Preview contacts in the segment*.

<Image align="center" width="80% " src="https://files.readme.io/88e4eb423d07b9f3a298c9abd447b4ca96bd0cd00cfc1cf284261485acabd326-birthday-campaign-05.webp" />

7. Click *Done*. The segment will be saved, and you will be able to see it in the general list in *Contacts → Segments*.

<Image align="center" width="80% " src="https://files.readme.io/b84e5fd3f027023b8e5caa57fce1cceb5301af2e446d60d7c6b54a90891052ee-birthday-campaign-06.webp" />

> 📘 Note
>
> Contacts are updated every day based on this condition. Only contacts with a birthday on the corresponding day are included in the segments. The segment is updated at 3 a.m.

8. To launch a campaign, click *Create campaign* and choose the necessary email.

<Image align="center" width="80% " src="https://files.readme.io/29c8fc2bc1d3b4048e972f0eac841baf8047f279369afa624b1196c237216802-birthday-campaign-07.webp" />

9. In *Send options below*, click *Schedule*, choose *Every day*, schedule the launch of the campaign, and click *Confirm*.

<Image align="center" width="80% " src="https://files.readme.io/162a29afa6a5983a4cc4e313d22f5f5287ee906e905ab4ccd24bd5c303824b91-birthday-campaign-08.webp" />

All scheduled campaigns are listed in *Campaigns → Scheduled campaigns*. If there are no contacts in the segment on any day of sending, the email won’t be sent to anyone.

<Image align="center" width="80% " src="https://files.readme.io/e1366e523507da88838ba46faa73fa94ea095c561ed1dc51f98f96a0f40b6c4b-birthday-campaign-09.webp" />

## Sending a Birthday Campaign from a Workflow

1. Go to *Automation → Workflows*, and click *Add workflow*.

<Image align="center" width="80% " src="https://files.readme.io/601e76d966220923001b662d30c4be87537197fc7304365d260805967eb58672-birthday-campaign-10.webp" />

2. Add and configure the following blocks:

* Start
* Timer
* Email
* End

(See [How to create a workflow in the system](https://docs.yespo.io/docs/workflow-management), [Workflow blocks](https://docs.yespo.io/docs/introduction-to-workflows#workflow-blocks) description)

<Image align="center" width="80% " src="https://files.readme.io/4d39d72b4c6287a7e7aa3ac3dfd5e6403c1d4391030018d219cd8523d3e01c4a-birthday-campaign-11.webp" />

3. In Email settings, you need to choose the message to be sent.

<Image align="center" width="80% " src="https://files.readme.io/90714e19615680bf0c42ec62471acbce32e0150e686d7da4d6d6b15af98d3893-birthday-campaign-12.webp" />

4. In Timer settings, select sending time.

> ❗️ Important
>
> Since segments are updated at 3 a.m, the workflow will be launched at the same time. To avoid bothering your customers at night, set a delay block and specify the desired send time.

<Image align="center" width="80% " src="https://files.readme.io/4309df4ecbe79138a0aef9b0a542eb797d5f97fb42d6301caa2eb4c7a2226226-birthday-campaign-13.webp" />

5. Click *Save and exit.*

The saved workflow will be shown in *Automation → Workflows*.

### Workflow launching and activation

1. Click *Start/Stop configuration.*

<Image align="center" width="80% " src="https://files.readme.io/efedb28dea108eb143a7eecd6b99ca9137ce83911f5133a7be118fb669d87b0a-Workflow.png" />

2. Select the *Regular* tab, the segment to send to, and the start schedule.

<Image align="center" width="80% " src="https://files.readme.io/6b5774fc8a04a76f7d169513b18d7b939dee9d9a66dfd1edd1aa9ff3cb6d721c-birthday-campaign-15.webp" />

3. In the *Process unique events* select *Each time* and click *Apply*.

<Image align="center" width="80% " src="https://files.readme.io/e521870c7aa370f65916de7221ed1c15c84b30c9c259a62819ac9d7df24a7a7e-Workflows.png" />

4. Click *Activate* and launch a workflow.

<Image align="center" width="80% " src="https://files.readme.io/430f734aaeaf75fa230e9ef70d05b63754c914c102899018e076ac454f486dc3-activate.png" />

## Workflow Options

Apart from the standard birthday greetings, you can create different workflows that will help make a gift for the customer, for example, promo code, sales discount, etc. For example, you can send a promo code for a promotion in advance or a belated holiday greeting:

<Image align="center" width="80% " src="https://files.readme.io/71bb9b93a7fcdafc1129b21c441be8637b9ae824cdd994bdb15b5762a219aabe-image17.webp" />

Such a campaign should be sent a few days before or a few days after the birthday. To send it, create the following segment:

1. Go to *Contacts → Segments*, and click *Add a segment*.

<Image align="center" width="80% " src="https://files.readme.io/a407e9df2c419602744a37df032e9241b5b37280f067575d2a4441d28b590e07-birthday-campaign-01.webp" />

2. Choose *Dynamic*, and click *Create*.

<Image align="center" width="80% " src="https://files.readme.io/f8ef6e1108b1caeab0558293405aaaa5500183c69a0fb380323526dce1d59f1a-birthday-campaign-02.webp" />

3. Fill the fields and click *Next*:

<Image align="center" width="80% " src="https://files.readme.io/1bd01de6380a666c88ff454f78abbaa109d957897eebddcd03e4198110c86210-birthday-campaign-19.webp" />

4. Click *Add card* and select *Fields → Personal information → Date of birth → via* *→ 5 → days.*

<Image align="center" width="80% " src="https://files.readme.io/8ed1a961c9b42c1f203ecacea8faf508be39374897786b47c1b771a5c42845f7-birthday-campaign-18.webp" />

> 🚧 Attention
>
> A segment can be created for contacts whose birthday occurred within a specific number of days. This condition is available for all regular [dates](https://docs.yespo.io/docs/how-import-and-match-contact-fields-in-the-system#date).

<Image align="center" width="80% " src="https://files.readme.io/eac8d19513ff5a6830fa2fbf6b19023d1a354b36411ee00e110ed2ad0956ddb2-during-last-days.webp" />

5. Save the segment, and launch the campaign as described above. Contacts from the segment will receive the birthday campaign 5 days before their birthday.

Note that Email is not the only channel you can use to congratulate your customer. You can also use SMS, Viber, Web Push, or Mob Push, or combine any channel in any order. For example, you can [send a Viber message](https://docs.yespo.io/docs/viber-messages-creation) to contacts who haven’t opened the email within 2 days:

<Image align="center" width="80% " src="https://files.readme.io/cfba99febd74eca992b2c6dfa8189c8cc7c9b75bdf8aae84ee2ca39a403202df-birthday-campaign-20.webp" />