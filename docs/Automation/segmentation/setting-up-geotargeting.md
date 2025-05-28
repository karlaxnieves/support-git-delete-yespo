---
title: Setting Up Geotargeting
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Geotargeting | Yespo Guide
  description: >-
    Yespo allows you to target users based on their location using IP addresses,
    enabling personalized geotargeted campaigns through dynamic segments.
  robots: index
next:
  description: ''
---
Yespo lets you target users based on their location. The location is defined from their IP address.

Send personalized information to people from different regions. Bet on quality rather than on quantity.

Use our [dynamic segments](https://docs.yespo.io/docs/how-add-dynamic-segment) for geotargeted campaigns.

> 📘 Note
>
> * Geotargeting is included in all plans except *ADVANCED*.
> * Currently, `IPv4` addresses are supported.

## How Geo-tracking Works In Yespo

Yespo receives contact location data when

* A contact clicks a link in any marketing email message
* Web push message is delivered
* A contact uses a mobile application
* Our script sends the following widget-related events:
  * View
  * Click
  * Subscribe
  * Submit (for request forms)
* The contact is identified from the *webcontact* [web tracking](https://docs.yespo.io/docs/web-tracking-overview) event; data about the language can be obtained from the headers of this event if the *Language* field is empty in the card of such a contact.

Each time one of the above actions is performed, the contact's location data is updated (except the web tracking event, which does not update, but only records the relevant data if it is not in the contact card).

<Image align="center" width="80% " src="https://files.readme.io/bcceece2072497c69c81185f6cd480e0c49b1aca97c9677ffbe19b2ec601021d-setup_geotargeting_001.webp" />

Also, you can [import](https://docs.yespo.io/docs/importing-historical-data) location user data to our system. The principle of its updating will be the same.

## Creating Dynamic Segment for Geotargeting

1. Go to *Contacts → Segments → Add Segment → Dynamic*.

<Image align="center" width="80% " src="https://files.readme.io/46fefd45a63dd5eb821663a19b6dcece7d6ff6576025998894c635de2005584d-setup_geotargeting_002.webp" />

2. Fill in the general properties:

* Segment name: it will be displayed in the general segments list.
* Segment purpose: for example, for regular promo campaigns, etc.
* [Tags](https://docs.yespo.io/docs/how-add-tags): they'll help find and filter the segments in the general list.

<Image align="center" width="80% " src="https://files.readme.io/154e1852cc5e1750b45d80a55459d426f7467da5ac02814b9237d7d8523a11d9-setup_geotargeting_003.webp" />

Click *Next.*

3. Click *Add condition* and create *Include* card.

<Image align="center" width="80% " src="https://files.readme.io/0b0f74c6189540fb6d0d77a3e68f49909233e63d7bafe5451c3ada52d886dc60-setup_geotargeting_004.webp" />

In the left sidebar, go to *Location → Country/Region/City*→ *one of* → *Specify value*, and select the values you want to apply to the targeted segment. Click *Done* to save settings.

<Image align="center" width="80% " src="https://files.readme.io/653cf0116f64dec6e18b062020cf6aac75e6ea106b5c6c1fc704b36e2df11727-setup_geotargeting_005.webp" />

To select a regional center and the whole region, choose the condition *Contact matches any of the conditions*.

<Image align="center" width="80% " src="https://files.readme.io/e72545ed3b7d93d840723d6a5f70f0682db4f0dc2e24ba5d6790d4f53dc6c257-setup_geotargeting_006.webp" />

If you need to exclude a city from the region, click *Add condition* and create a corresponding *Exclude* card:

<Image align="center" width="80% " src="https://files.readme.io/3facc7d9b69e0dfec2d7b2b55990732f608d7155e995100404e452f24c2c7f8a-setup_geotargeting_007.webp" />

You may set geotargeting within one country:

<Image align="center" width="80% " src="https://files.readme.io/5dc549306b3fc0b61ca1248fbf92637291f09c414ed160bc2f7858d648c55ea2-setup_geotargeting_008.webp" />

Or within the selected regions/cities in different countries:

<Image align="center" width="80% " src="https://files.readme.io/e5d547d365128cb8435ce2e72c46dc3cf9434762e471ac3bb1eb23499e6edc0e-setup_geotargeting_009.webp" />

> 📘 Note
>
> When you choose several conditions in one card, pay attention to the operator.
>
> * `AND` – the segment will include contacts that match all conditions in the card.
> * `OR` – the segment will include contacts that match of any conditions in the card.
