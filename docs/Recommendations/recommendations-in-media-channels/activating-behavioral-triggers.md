---
title: Activation of Behavioral Triggers
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Activation of Behavioral Triggers | Yespo Guide
  description: >-
    The Professional plan offers advanced trigger algorithms to automate
    customer interactions and boost sales through personalized messaging, with
    setup and customization support provided by the service team
  robots: index
next:
  description: ''
---
Behavioral triggers are automated responses to user actions that allow businesses to engage with potential customers when their interest or purchase intent is highest.

The most common example of a behavioral trigger is the **Abandoned Cart**, which is one of the biggest problems for online stores. According to our data, about 70% of purchases do not reach the final stage. However, with the help of reminders and personalized recommendations, you can bring back a significant part of these buyers: an abandoned cart notification can increase conversions by 10-20%.

Other behavioral triggers, such as personalized offers based on previous purchases, can increase the average check by 10-15%. Therefore, using product recommendations based on user behavior has also become integral to effective marketing strategies for online businesses.

For example, **Amazon** actively uses personalization algorithms to suggest products based on past purchases, views, or abandoned carts. **eBay** uses similar approaches, recommending products to users based on their search and bidding history. **IKEA** provides recommendations of additional products to shoppers to create sets, such as furniture that can be combined.

These platforms integrate behavioral triggers to increase customer engagement and provide personalized experiences that drive purchases.

## Trigger Algorithms of the Professional Plan

The **Professional** plan unlocks the power of trigger algorithms that automate customer interactions and increase conversions through personalized messaging. Below is a brief description of the basic algorithms:

1. The **Abandoned Cart** trigger encourages the completion of a purchase.
2. The **Abandoned View** trigger reminds users of products that they are interested in.
3. The **Cart Products Discounted** trigger allows you to automatically inform subscribers if the price of the products in their cart has decreased. This strategy encourages purchase completion with an attractive offer.
4. The **Abandoned Similar to Cart Products Discounted** trigger recommends alternative products with a reduced price similar to those in the abandoned cart. This expands the choice and can increase sales.
5. The **Viewed Products Discounted** trigger notifies users of discounts on previously viewed products.
6. The **Viewed Similar to Cart Products Discounted** trigger promotes discounted products similar to those the subscriber is interested in.
7. The **Next Best Offer** trigger offers users the most relevant products based on their behavior, purchase history, and interests.
8. The **Reactivate Inactive Customers** trigger engages a segment of your audience that hasn’t purchased or responded to your messages.
9. The **Regular Demand** trigger reminds customers of products they regularly purchase (such as consumables or everyday items). This automation helps maintain customer loyalty.

Algorithms allow you to include up to 6 relevant products in the email, such as products added to the cart. In addition, up to 6 recommended products are added (for example, similar to those in the cart or the most popular). This makes it possible not only to return the user to an unfinished purchase but also to stimulate them to make additional purchases with the help of relevant recommendations.

Reserve funds for the **Professional** plan with the help of the Sales team, and we will configure trigger algorithms for your business on a turnkey basis. You will receive completely ready-to-use campaigns that can be easily customized to your needs.

## Behavior Triggers Settings

Our team performs the main stages of the behavior trigger setup process; your participation is required only at the preparatory stage.

1. **Preparatory stage**

- **[Add a web tracking script to your website](https://docs.yespo.io/docs/how-set-web-tracking-your-website)**. This code allows you to track user behavior, such as product views, adds to cart, and other key actions.
- **[Upload a product feed](https://docs.yespo.io/docs/importing-product-feed) to Yespo.** This is a list of your products with descriptions, prices, availability, and other details needed to personalize recommendations.
- **Set up tracking events** using [JavaScript](https://docs.yespo.io/docs/how-set-web-tracking-sending-events-java-scipt-request) or the [REST API](https://docs.yespo.io/docs/how-transfer-website-behavior-data-through-rest-api).

2. **Our team's work**

After completing the basic settings, our specialists will perform the following actions:

- **Development of a product selection algorithm.** Based on the specifics of your business and customer behavior, we activate a model that automatically determines which products suit a specific trigger workflow.
- **Preparation of message templates.** Dynamic code is embedded in the email template, allowing you to automatically substitute products according to the algorithm and user actions. Dynamic [Velocity variables](https://docs.yespo.io/docs/introduction-to-velocity) are specified in the templates of other media channels.
- **Formation of trigger launch conditions.** Professional triggers are regularly triggered on contacts that match the dynamic segment settings. For example, for the **Abandoned Cart** trigger, a segment of users who added products to the cart but did not complete the purchase within N time is formed.
- **Creation of a workflow.** The entire campaign is configured: the moment of sending, launch conditions, communication channels, etc.

As a result, you get ready-made trigger workflows that immediately start generating profit.

After launching workflows, [the campaign analytics](https://docs.yespo.io/docs/triggered-campaign-report) will give you a clear picture of how users are responding to your messages, which elements are working best, and where there is room for improvement — from the color of the button in the email to expanding the workflow with additional channels, conditions, timers, and more.

## Customizing Settings

Once trigger workflows are activated, you can customize each campaign element according to your audience's needs.

### 1. Workflow

[Workflows](https://docs.yespo.io/docs/introduction-to-workflows) are the basis for triggers. You can:

- Adjust the conditions for starting and stopping the workflow, for example:
  - Remind about a new abandoned cart no more than once every seven days;
  - Stop the workflow if the contact is in the segment of those who have placed an order in the last 24 hours.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a5b7deb4f591feb0734b0484b82dcf5c723bd0d5e443d08cd669481483e9034e-triggers_1.webp",
        "",
        "Start/Stop Configuration"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Add timers to increase or decrease the time interval between messages.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6161860064010084f114bdd338380b2c150bc8362dc35f32ea3dd3b59a8304bb-triggers_2.webp",
        "",
        "Timer"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Extend workflows with additional conditions and checks, such as whether a contact is in a particular segment. For example, if a contact is in a segment of those who have placed an order in the last 30 days, do not send them reminders.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1005f17642dec5021df0651e97c095190d945b3d57e0fcfc8b641a1f294b9325-triggers_3.webp",
        "",
        "Additional conditions and checks"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Integrate multiple channels into the workflow, such as Viber, SMS, Push, etc., to ensure maximum reach. Add the [One of Many](https://docs.yespo.io/docs/using-one-many-block) message block that automatically determines the most effective message option and prioritizes its use.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/612b19bb3da8f77cdb5787875f1d8ca779432f5e66c0d41220ec47cf44a08254-triggers_4.webp",
        "",
        "Integrate channels"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


- Conduct A/B testing of two workflow options with different timers, messages, segments, etc. (the [Split](https://docs.yespo.io/docs/blocks-description-conditions-group#split) block).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8a6a3c7bd5bc3750160326f69aa15cf1c52e4207ba3d74559c85c3da22bf7cd7-triggers_5.webp",
        "",
        "A/B testing"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### 2. Launch Condition

[Dynamic segments](https://docs.yespo.io/docs/how-add-dynamic-segment) that trigger Professional plan triggers are formed based on user behavior and characteristics. You can add any filters to form an audience, such as geolocation, purchase history, interests, etc.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8c4d83d9dc3b46d1411a9ef3827e1d2d582fe2a1cd5901ecb405adb7ebc6a25a-triggers_6.webp",
        "",
        "Launch Condition"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


### 3. Messages

In each email, [product blocks](https://docs.yespo.io/docs/product-blocks) with specific recommendation algorithms will be available, and they will be saved to the module library for easy editing. Then, you can simply drag such a module to any email and edit the display of product cards if necessary. The content of short messages (Viber, Mobile Push, etc.) can be easily changed in the corresponding editors.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9194f73049330f2ca775804a8f4b82ebebf6dbef071cff6a28bdec2306d41c4b-triggers_7.webp",
        "",
        "Editing product block"
      ],
      "align": "center",
      "sizing": "80% "
    }
  ]
}
[/block]


> 👍 Get Started Today!
> 
> Contact Sales at [sales@yespo.io](mailto:sales@yespo.io) to reserve funds for the **Professional** plan while we configure your triggers