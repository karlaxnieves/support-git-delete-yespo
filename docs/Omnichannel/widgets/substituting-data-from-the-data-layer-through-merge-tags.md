---
title: Substituting Data from the Data Layer through Merge Tags
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Substituting Data from the Data Layer through Merge Tags | Yespo Guide
  description: >-
    Step-by-step instructions for accessing the Data Layer, adding Merge Tags to
    widgets, and setting up use cases like displaying product categories,
    abandoned cart reminders, and dynamic order value messages.
  robots: index
next:
  description: ''
---
The **Data Layer** is a structure that stores data about user actions on a website, while **Merge Tags** allow you to insert this data into widgets to personalize their content. For example, a widget can display a discount on products from the category the user is currently viewing.

Let’s explore how to find the necessary data in your website’s Data Layer and add the appropriate Merge Tags to widgets to create a highly personalized user experience, boost engagement, and improve conversion rates.

## Finding Data Layer Types on Your Website

1. Open your browser’s **Developer Tools** (press `Ctrl+Shift+I` on Windows or `Cmd+Option+I` on Mac, or right-click on the page and select `Inspect`).
2. Navigate to the *Console* tab.
3. Type `dataLayer` and press `Enter`.
4. Expand the list to view the current structure and data types stored in the Data Layer.

<Image align="center" width="80% " src="https://files.readme.io/b1e5ae3b1c3a9e5ecf2925135c74dc97dc387b9bd2131369a293c779e02a5ab8-Merge_Tags_1.png" />

## Adding Merge Tags to Widgets

1. Go to *Site → Widgets*, then open an existing widget or create a new one.

<Image align="center" width="80% " src="https://files.readme.io/69c762fa70fd196e77034c5c6e6e9df3c477d91dd3449781a7a4fd61435f30ba-Merge_Tags_2.png" />

2. Select the text field where personalization will occur, click the *Merge tags* option, and choose *Data layer*.

<Image align="center" width="80% " src="https://files.readme.io/a9d7f33bb88aed9bdca7ca9836b8b78ea5f5dd30da0018edae43eaf00a122cb1-Merge_Tags_3.png" />

3. Fill in the following fields:
   * **Data layer event:** Specify the event name.
   * **Variable path:** Enter the exact path to the required data in the Data Layer.
   * **Example value:** Provide a sample value for preview.

<Image align="center" width="80% " src="https://files.readme.io/b2c568bac8c53dc8b028de8bf920dd010fcc7e880e201a422932a754fe0e8cb5-Merge_Tags_4.png" />

> 📘 Note
>
> * The **eventName** field is optional and only required if your Data Layer follows <a rel="nofollow" href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events" target="_blank">Google’s recommended structure</a>. Even if your events lack names, the system will locate the necessary parameters based on the path format, such as `ecommerce.items.0.price`.
> * If multiple similar parameters exist in the Data Layer, or if the Data Layer is duplicated, the system will use the latest instance.
> * Ensure you enter parameter names exactly as they appear in the Data Layer so the system recognizes them. Additionally, parameter names must meet <a rel="nofollow" href="https://developers.google.com/analytics/devguides/collection/ga4/reference/events?client_type=gtag" target="_blank">Google’s requirements</a>.
>
> <Image align="center" width="80% " src="https://files.readme.io/a99e049a4deadbd6c9997c3161d2238afa1742b7c7d026073b1705d37b4c8438-Merge_Tags_5.png" />

## Use Cases

### Displaying the Viewed Product Category in a Widget

* **Scenario:**

A user browses products in a specific category on your website. You want to grab their attention by displaying a pop-up offering a 10% discount if they purchase two items from the category they are currently viewing.

* **Setup:**

1. **Data Layer Event:** Use the `view_item` event to retrieve data.

<Image align="center" width="80% " src="https://files.readme.io/7155b90d094ae271ad673d03ca70efb06da90d45eba9e55af56d4e2b83132884-Merge_Tags_6.png" />

2. **Data Path:** Open Developer Tools, locate the `view_item` event in the Data Layer.

<Image align="center" width="80% " src="https://files.readme.io/f88c1299b5a9e0a0891821ea6fbb81148755b3c0d8d3a5031876a096cff3ad05-Merge_Tags_7.png" />

Define a property containing product category information (in our example, `item_category`).

<Image align="center" width="80% " src="https://files.readme.io/df866ef2a1f4e5d55624aa8d64cd2163b708d94fe72d88a5ccd30fec57d7432d-Merge_Tags_8.png" />

Right-click on the line containing `item_category`, and copy its property path.

<Image align="center" width="80% " src="https://files.readme.io/29292d1979114b03e46636a09d69170485ac966888019dc61d75a67de91c1873-Merge_Tags_9.png" />

Paste it into the *Variable path* field. Remove any array indices at the beginning (e.g., **"13"** in our example).

<Image align="center" width="80% " src="https://files.readme.io/1f8065ad9da895dfb225b1934670d95b8c7056d7e2566fc966ee41a832d895bf-Merge_Tags_10.png" />

3. **Example value:** Enter a sample category (e.g., **"Jewellery"**) in the *Example value* field to preview how the widget will look.

<Image align="center" width="80% " src="https://files.readme.io/66e2ba84ef95b1d52e37c8825d6ddb793fd6984fb04e4090ab29be5e396e520e-Merge_Tags_11.png" />

### Abandoned Cart Reminder with Dynamic Product Information

* **Scenario:**

A user adds an item to the cart but does not proceed to checkout within a certain period. This behavior suggests hesitation or distraction. To re-engage them, you can trigger a pop-up reminding them to complete the purchase, displaying the product names in their cart along with a special incentive.

* **Setup:**

1. **Data layer event:** `add_to_cart`

2. **Variable path:** `ecommerce.items[0].item_name`

<Image align="center" width="80% " src="https://files.readme.io/3b5ba6dd02dd3de120975f2e1e1bd6573ddca833e1514f4a3bc9d3b33ff0a841-Merge_Tags_12.png" />

3. **Example value:** `Item name`

<Image align="center" width="80% " src="https://files.readme.io/eb95a9269190fe2d5c0b2e56a808e947d9c357dd9997816f115fd0e1a2ca9991-Merge_Tags_13.png" />

After saving the pop-up, configure its [calling rules](https://docs.yespo.io/docs/widget-calling), such as **time spent on the site**, **inactivity**, or **mouse movement away from the page**.

<Image align="center" width="80% " src="https://files.readme.io/b0bb6e71c6c2475562adc71af4276a58b0f4ca742953c1706a86a1b6c8edcdd7-Merge_Tags_14.png" />

### Increasing the Total Order Value

* **Scenario:**

To encourage customers to increase their cart total, you can display a dynamic message like: *"Spend $300 to get a 10% discount. Your current cart total is N."* Here, **"N"** is dynamically replaced with the current cart value.

* **Setup:**

1. **Data layer event:** `view_cart`

2. **Variable path:** `checkout.total_value`

<Image align="center" width="60% " src="https://files.readme.io/52a4dca5176e221c30d5175028a087b2191798d66d7cf989e597ca14e85548e8-Merge_Tags_15.png" />

3. **Example value:** `Total value`

<Image align="center" width="80% " src="https://files.readme.io/70a6b0079071859a26f7874266df8eb2f03891545acaccb08e30566f08ee8f15-Merge_Tags_16.png" />

## Potential Issues to Watch Out For

| Issue                                                                 | Outcome                                                                              |
| :-------------------------------------------------------------------- | :----------------------------------------------------------------------------------- |
| Missing Data Layer                                                    | The widget will not display                                                          |
| Invalid Path                                                          | An empty or incorrect path will prevent the system from retrieving the required data |
| Path leads to an object or an array of objects                        | The widget will not display                                                          |
| Path leads to an array of primitive values (e.g., numbers or strings) | Values will be displayed separated by commas and spaces                              |
