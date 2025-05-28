---
title: Creating Dynamic Segment
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Creating Dynamic Segment | Yespo Guide
  description: >-
    Learn how to create dynamic segments based on your customers’ behavior and
    offer them more relevant content.
  robots: index
next:
  description: ''
---
A dynamic segment is created based on dynamic conditions, which you can choose depending on your contact base. The segment cards can change based on whether the contact matches the chosen conditions. This feature can apply to [birthday emails](https://docs.yespo.io/docs/how-set-automated-birthday-campaign), [reactivation emails](https://docs.yespo.io/docs/how-automate-customer-reactivation), split between customers and subscribers, etc.

## Adding a Dynamic Segment

1. Go to *Contacts → Segments* and click *Add segment*.

<Image align="center" width="80% " src="https://files.readme.io/0f3c6587fb8ac73b980ebb9ed304d7463458395beb7d2cb5b270c0d81c7f91bf-creating-dynamic-segment-01.webp" />

2. Select the *Dynamic* segment type and click *Create*.

<Image align="center" width="80% " src="https://files.readme.io/01ff7ea1e18f874c2846b8fa89d67ceafd93955e8e29dbb8813f91b6a9dada6c-creating-dynamic-segment-02.webp" />

3. Fill in general properties:

* Name (required) — displayed in the general segment list.
* Purpose (optional) — specify how the campaigns will be used. For example, for triggered emails, regular promo campaigns, etc.
* [Tags](https://docs.yespo.io/docs/how-add-tags) (optional) — select from the list or add a new one for quick filtering and segment search.

4. Click *Next*.

<Image align="center" width="80% " src="https://files.readme.io/026ad784c61cef599d122dacba67653f278524fc41329e088cb1e60747749a74-atributions-en.webp" />

5. Add condition.

For example, you need to select all subscribers who have read emails this month. 

6. Go to the *Channels tab → Contact activity by Email → Last opened → During → This month.*

<Image align="center" width="80% " src="https://files.readme.io/3dacaf7b795e67282aca5b4e5ef5a6874174b5af233afd37e8b7488c0d3c4d13-creating-dynamic-segment-04.webp" />

7. To see what contacts have been added, click on *Preview contacts in the segment*.

<Image align="center" width="80% " src="https://files.readme.io/dddfe021d3cb10230b39c448888eccbc33566399a0af6ba8ecd8c77c52552a02-creating-dynamic-segment-05.webp" />

8. To see how many contacts are in the segment, click on *Recalculate contacts*.

<Image align="center" width="80% " src="https://files.readme.io/aa35971269ed4119eed15120345eb915c8e1fadbb01609cc9994f0cdc4c1ca13-creating-dynamic-segment-06.webp" />

9. If you need to create a custom condition for creating a segment, scroll down the list of conditions and click *Set up segmentation*.

<Image align="center" width="80% " src="https://files.readme.io/665af4be5fa4ed11703236740bf6069c4a0b2587dc51b5d94d56d9965e299e61-creating-dynamic-segment-07.webp" />

10. In the window, select the following type of settings:

* Contact field management
* Segmentation by custom events
* Segmentation by events for eCommerce retailers

<Image align="center" width="80% " src="https://files.readme.io/5c35d67ee02e1641f00d909fd7459e59b4d1834f6bf90543b4b48efa97ae35a4-creating-dynamic-segment-08.webp" />

11. When all the necessary conditions are specified, click the *Done* button. The new segment will be available in the general list of groups.

<Image align="center" width="80% " src="https://files.readme.io/6dc576a14a66ebb9cc21d3d558c1ab53fa047c96d6c915e84b5bee499cda7183-creating-dynamic-segment-09.webp" />

## Dynamic Segment Conditions

Let's take a closer look at how to create a segment with multiple conditions.

### 1. Card conditions

You can create an unlimited number of cards, each having unlimited conditions.

#### Conditions inside the cards

When adding conditions to a card, the segment will include only those contacts that match the specified conditions.

For example, you add two conditions:

* Last opened this year;
* Average order check greater than $1,000.

<Image align="center" width="80% " src="https://files.readme.io/8bd5acfab338dfd34ae7691737b8865962f10578a3ec6c0d59db3d1bc66d4ac5-creating-dynamic-segment-10.webp" />

The segment will include only those contacts who have opened emails over the past year, with an average order value of more than $1,000. The card will look like this:

<Image align="center" width="80% " src="https://files.readme.io/7fa074bfd0e56be8ec398790aea8d0175464e6f3a0380cdc66b00690a1ea7d97-creating-dynamic-segment-11.webp" />

To add the contacts that match any condition, choose the corresponding option in the header of the card:

<Image align="center" width="80% " src="https://files.readme.io/6db3771afbf0c6fc192e6fac6fb571369752c54812fbe906223c39aa2f762df5-creating-dynamic-segment-12.webp" />

For example, you add the following conditions:

* Last clicked week ago;
* Last opened week ago

The segment will include the contacts that either clicked on links in the email or read an email a week ago.

<Image align="center" width="80% " src="https://files.readme.io/2eb97794921904005b8e42c72b663e3c94675fee430ec507a20405d413ac256d-creating-dynamic-segment-13.webp" />

#### Excluding Conditions from a Card

Any of these conditions can be made negative. Click on ≠ to exclude any condition from the card.

<Image align="center" width="80% " src="https://files.readme.io/97d832c5fbe73f56dadfc979242e7f7597e48ccbd4cc253324709395f073fff3-creating-dynamic-segment-14.webp" />

For example, you want to add to the card all the contacts that have opened emails over this month, with an average order value less than $1,000. Exclude the last condition, and the segment will include only the contacts that have opened emails during the last month and their average order value is more than $1,000.

#### Excluding the Entire Card

You can exclude the whole card. Such a card will be highlighted red and will have a not prefix in the segment equation.

<Image align="center" width="80% " src="https://files.readme.io/c2dd3b4ef561826ceb8a7d34749ee3e72393ea73a3b2e1fb465bbfa130a556b0-creating-dynamic-segment-15.webp" />

#### Excluding a Condition from the Segment

With many cards, when you need to exclude a particular condition from the entire segment, use the right column. Contacts that match the conditions from the right column will not be included in the segment.

<Image align="center" width="80% " src="https://files.readme.io/971fa9f50b0b9de69002bb6c445749bb13757c84572e2034484db475bf464606-creating-dynamic-segment-16.webp" />

You can exclude several cards with different conditions.

### 2. Equation Operators AND/OR

For convenience of operation, you can group conditions in several cards using the following operators:

AND — the segment will include all the contacts that match the conditions of all cards.

OR — the segment will include the contacts that match the conditions of any card.

<Image align="center" width="80% " src="https://files.readme.io/66ded032744a87cca5fa14321633124d5530f7b66a1470207306cec9c3a00f77-creating-dynamic-segment-17.webp" />

### 3. Segment Equation

With many cards, the segment equation is displayed in the following formula: (A or B) – C.

<Image align="center" width="80% " src="https://files.readme.io/8794cdbfdc26261cb7a9e9fa78cc5612851e3efb2af1154a59c4933fc58055e2-creating-dynamic-segment-18.webp" />

* The equation shows in what order the cards are processed.
* Brackets are put automatically to unite the cards based on the processing priorities.
* The letters in the equation match the cards. A cursor on the letter automatically highlights the corresponding card.

<Image align="center" width="80% " src="https://files.readme.io/04529d1f41b823d45041b93efda78160c4aaf3278a53e832aab7f000ada6159d-creating-dynamic-segment-19.gif" />

* If the card isn’t displayed on the screen, hover over the corresponding letter in the equation to see the conditions.

<Image align="center" width="80% " src="https://files.readme.io/6fd2d3997b5a34c1da3896d24df82aab117dadbff568ee6617f9d754a74b6ced-creating-dynamic-segment-20.gif" />

> 🚧 Important
>
> By default, the contacts that are processed first are united by AND operator. In the equation, such cards are enclosed in brackets.

<Image align="center" width="80% " src="https://files.readme.io/ee40bb08ec4c9db7ac704f5a3b0cc0a2073b618b52437fce4f022d34afa7e8e8-creating-dynamic-segment-21.webp" />

For example, the equation “(A and B) or C” will be processed as following:

1. First, the system will find the contacts that match the conditions in A and B cards.
2. Next, it will add the contacts that match the conditions in C card.

## Useful Features

For more convenience, all the features are now available right in the segment interface after you’ve created a card:

### 1. Export a dynamic segment to the list

You can export all the contact details as a static segment to the existing list. This is relevant for triggers so that a [campaign for a segment](https://docs.yespo.io/docs/how-launch-regular-workflow-segment-support) can be launched instantly.

<Image align="center" width="80% " src="https://files.readme.io/6c5af132d0cee5f7cab5be8494c77ff9b1531a7db286e340e5f2bdaf5f14417f-creating-dynamic-segment-22.webp" />

### 2. Splitting a Segment

This might be useful for A/B testing.

<Image align="center" width="80% " src="https://files.readme.io/858f4d3015254a0ec969b87b480042a53c640b620121b543e00e31c8bf71adeb-creating-dynamic-segment-23.webp" />

> 🚧 Important
>
> You can split a segment only if it includes more than 10 contacts. We recommend conducting split tests with more than 2,000 active contacts to avoid inaccurate results.

### 3. Tutorial

For any information on the segment creation, see *Tutorial* at the top of the page.

Hints are divided into 5 categories:

* Conditions inside cards
* Formula for contacts calculating
* Operator "NOT"
* "AND", "OR" between cards
* Excluding contacts

<Image align="center" width="80% " src="https://files.readme.io/3e3f1c178cccabdbb7a246a43d335453fcbe86ccf32665bbe5b6c1cace4d4376-creating-dynamic-segment-24.webp" />

### 4. Searching Events and Parameters

The search logic of events and parameters allows you to quickly and easily set the conditions for forming a dynamic segment.

The search works both in the first column (names of event types and contact parameters) and in the second (names of event parameters and additional contact fields).

If both the event and its parameter match the search query, you will see the corresponding events in the first column, and in the second column, not only the parameters that match the search query but also all the parameters of the events from the first column.

<Image align="center" width="80% " src="https://files.readme.io/1d163906b7acafb47781f8f450c3fb7f3ed21507f920c1873dc54cb4f6ac8ba2-search-1.webp" />

If you need to find all events that contain a certain parameter, enter its name in the search field. The first column will display the corresponding events, and the second column will display a list of event parameters indicating which event contains the parameter from the search query. 

<Image align="center" width="80% " src="https://files.readme.io/369d8a282d1b3168f200eeba5cfa53f5401e007c9735c633b766fd0b78c5d18c-search-2.webp" />

When you hover over a parameter in the first column, the name of the event type containing this parameter is highlighted.

<Image align="center" width="80% " src="https://files.readme.io/e9adbe0376bfafa98f445bfc155c5796484d17dd88b4e6a88a1dd0571ae9e71d-search-3.webp" />

Click on a specific event's name to see a list of all parameters. The parameter that matches the search query is highlighted.

<Image align="center" width="80% " src="https://files.readme.io/753f8f6241f2523e57bb66a4f4646e16313cdc4568c22b85b26e34949f0ccf30-search-4.webp" />
