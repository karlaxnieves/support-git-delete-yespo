---
title: Installing Plugin for WooCommerce Sites
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Installing Plugin for WooCommerce Sites | Yespo Guide
  description: >-
    Learn how to transfer contacts' and orders' data from your WooCommerce site
    to Yespo
  robots: index
next:
  description: ''
---
The Yespo <a rel="nofollow" href="https://wordpress.org/plugins/yespo-cdp/#description" target="_blank"> plugin</a> allows you to manage your WooCommerce website’s marketing campaigns within one Customer Data Platform. The plugin allows you to:

* Transfer contacts from your site to Yespo.
* Synchronize order data (historical and new).
* Transfer website events, such as user activity, visited pages, cart and order contents as the plugin installs the tracking script on your WooCommerce site.

After integration, you will be able to:

* Organize automatic onboarding workflow for new contacts.
* Enrich contact profiles with the data from your alternative platforms, such as mobile apps.
* Send bulk omnichannel campaigns.
* Set up transactional message chains.
* Analyze campaigns’ performance in real-time.

When installed, the plugin allows sending the following events to Yespo as described in the table below.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        <div style="width:325px">

        Event

        </div>
      </th>

      <th>
        <div style="width:275px">

        Description

        </div>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        *PageView*
      </td>

      <td>
        This event is sent when a site visitor loads a particular website page. \
        Default event, required for all other web tracking events to work.
      </td>
    </tr>

    <tr>
      <td>
        *ProductPage*
      </td>

      <td>
        The event is associated with actions on your product pages.  \
        It can be used for campaigns involving abandoned view, discount notifications for viewed items, or win-back campaigns.
      </td>
    </tr>

    <tr>
      <td>
        *CategoryPage*
      </td>

      <td>
        It is triggered when a visitor views a product category page.  \
        After receiving this event in Yespo, you can send emails with recommendations of the most popular products in the viewed category.
      </td>
    </tr>

    <tr>
      <td>
        *CustomerData*
      </td>

      <td>
        This event relates to the site visitor’s data received when they register, log in or complete a purchase.  \
        The event links your website visitors to accounts in your system, enabling personalized campaigns.
      </td>
    </tr>

    <tr>
      <td>
        *StatusCart*
      </td>

      <td>
        The event helps to track the status of your customers’ shopping carts.\
        It can be used for running ecommerce workflows, such as the abandoned cart, discount notifications for products in the abandoned cart, and notifications for discounts on products similar to those in the cart.
      </td>
    </tr>

    <tr>
      <td>
        *PurchasedItems*
      </td>

      <td>
        It informs about the purchased items and can be used for compiling lists of popular products for recommendations, upselling, and cross-selling. \
        For example, if a customer purchased a phone, you can send them a message with recommendations featuring a phone case or a charger.
      </td>
    </tr>

    <tr>
      <td>
        *MainPage*
      </td>

      <td>
        It is triggered when a visitor is currently on the main page. Necessary to display recommendations on the site.
      </td>
    </tr>

    <tr>
      <td>
        *NotFound*
      </td>

      <td>
        This event tacks 404 page. Necessary to display recommendations on the site.
      </td>
    </tr>

    <tr>
      <td>
        *ProductImpression*
      </td>

      <td>
        This event is used to show impressions for recommendation blocks in Reports.
      </td>
    </tr>
  </tbody>
</Table>

In case of deactivation, the plugin ceases to perform its functions. 

Uninstalling the plugin removes all components configured during the setup of web tracking, including scripts and functions used for event tracking.

> 📘 Note
>
> * The plugin relies on data transfer via cron jobs. Ensure you have an active cron set up: either the default WordPress cron or a server-side cron on your hosting.
> * If you're using any caching plugins, make sure to install updates through the WordPress repository and clear your cache afterward to ensure all changes are properly applied.

## WordPress & WooCommerce Hooks

For the plugin to function properly, make sure of the following:

* **Standard WordPress system hooks** have not been removed or deactivated in the theme or by other plugins. These hooks are active by default, so if they are missing, it may be due to remove\_action or remove\_filter being used intentionally.
* **Required WooCommerce hooks** are present in the theme and functioning correctly. These hooks are essential for integrating with WooCommerce features and must be available in your setup.

If any standard WordPress hooks have been forcibly removed or if the required WooCommerce hooks are missing, the plugin may not work as expected.

### Action WordPress Hooks

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        <div style="width:325px">Name</div>
      </th>

      <th>
        <div style="width:275px">Description</div>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        `admin_notices`
      </td>

      <td>
        This hook displays messages in the admin notice area. It is part of the WordPress core and is not affected by front-end themes or their customizations. Used by WordPress itself and other plugins.
      </td>
    </tr>

    <tr>
      <td>
        `profile_update`
      </td>

      <td>
        Triggered when a user profile is created or updated. It belongs to the WordPress core and is independent of front-end themes or customizations. Used by both WordPress and third-party plugins.
      </td>
    </tr>

    <tr>
      <td>
        `delete_user`
      </td>

      <td>
        Triggered before a user is deleted. This core WordPress hook functions independently of theme customizations. Utilized by WordPress and external plugins.
      </td>
    </tr>

    <tr>
      <td>
        `wp_privacy_personal_data_erased`
      </td>

      <td>
        Triggered after a personal data erasure request is completed (GDPR). Part of WordPress core and not influenced by front-end theme customizations. Used within the WordPress core.
      </td>
    </tr>

    <tr>
      <td>
        `admin_enqueue_scripts`
      </td>

      <td>
        Used to enqueue JavaScript and CSS files that extend the admin panel's functionality. It is part of the core and not affected by front-end themes. Utilized by WordPress and plugins.
      </td>
    </tr>

    <tr>
      <td>
        `wp_footer`
      </td>

      <td>
        Adds custom code before the closing 

        `</body>`

         tag. Part of the WordPress core, and not impacted by front-end themes. Used by both WordPress and plugins.
      </td>
    </tr>

    <tr>
      <td>
        `wp_login`
      </td>

      <td>
        Triggered after a successful user login. Core hook not affected by front-end customizations. Used by WordPress and other plugins.
      </td>
    </tr>
  </tbody>
</Table>

### Filter WordPress Hooks

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        <div style="width:325px">Name</div>
      </th>

      <th>
        <div style="width:275px">Description</div>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        `cron_schedules`
      </td>

      <td>
        Used to add custom interval cron tasks. Utilized by both WordPress and third-party plugins.
      </td>
    </tr>
  </tbody>
</Table>

### Action WooCommerce Hooks

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        <div style="width:325px">Name</div>
      </th>

      <th>
        <div style="width:275px">Description</div>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        `woocommerce_add_to_cart`
      </td>

      <td>
        Triggered when a product is added to the cart. Part of the WooCommerce core, initialized in 

        `CartController.php`

         in 

        `src/StoreApi/Utilities`

        .
      </td>
    </tr>

    <tr>
      <td>
        `woocommerce_after_cart_item_quantity_update`
      </td>

      <td>
        Triggered when the quantity of items in the cart is changed. Core WooCommerce hook, initialized in 

        `class-wc-cart.php`

         in the includes directory, but not actively used by the plugin itself. Since 

        `includes`

         files are rarely modified, the risk of this hook being broken is low.
      </td>
    </tr>

    <tr>
      <td>
        `woocommerce_cart_item_removed`
      </td>

      <td>
        Triggered when an item is removed from the cart. A core WooCommerce hook, initialized in 

        `class-wc-cart.php`

         under 

        `includes`

        . Actively used by WooCommerce. Since 

        `includes`

         files are rarely modified, there’s minimal risk of this hook being affected.
      </td>
    </tr>

    <tr>
      <td>
        `woocommerce_thankyou`
      </td>

      <td>
        Triggered after an order is placed. Part of WooCommerce core, used in templates to show final order details. Initialized in 

        `thankyou.php`

         under 

        `templates/checkout`

        . Since template files are often customized, there's a higher risk of hook initialization being overwritten.
      </td>
    </tr>
  </tbody>
</Table>

## Installing Plugin

1. Log into your WordPress account.
2. Go to the *Plugins* section.
3. Find Yespo in the search field and click *Install now*.

Or, 

* Go to the WordPress plugins page. 
* Find Yespo in the search field and click *Download*.
* Upload plugin at the Plugins section of your WordPress account.

4. Click *Activate*.
5. Click the *Settings* button under the plugin on the Installed *Plugins* section or navigate to the separate Yespo page.
6. Enter your *full access API key* from the Yespo account and click *Synchronize* to start data synchronization.

<Image align="center" width="80% " src="https://files.readme.io/a362dbd19b3dc3f59164715dc4056f14653c706b48e6c00471bf23be90b1b428-1.webp" />

> 📘 Note
>
> * The access rights for the API key must be “Full access to API”. Read this [article](https://docs.yespo.io/reference/api-keys) to learn about API keys in Yespo.
> * Yespo plugin supports multisite configurations for WooCommerce stores in WordPress. For correct data handling, each WooCommerce store must be connected to a separate Yespo account.

After clicking the *Synchronize* button, the new contacts’ and orders’ data that appear in WooCommerce will be automatically transferred to Yespo. The on-site event tracking configuration will also be completed. To ensure proper operation, make sure to [add the product feed](https://docs.yespo.io/docs/importing-product-feed) to Yespo.

<Image align="center" width="80% " src="https://cdn.yespo.io/photos/shares/Support/Images/AB-Tests-In-Workflows/image-4.png" />

Please [contact us](mailto:support@yespo.io) if you have any questions or problems with integration.
