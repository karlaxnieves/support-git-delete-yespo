---
title: Integration with Wix Forms
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Integration with Wix Forms | Yespo Guide
  description: >-
    This is a guideline for integration with contact collection forms published
    on sites built on Wix.
  robots: index
next:
  description: ''
---
This is a guideline for integration with contact collection forms published on sites built on Wix.

Before getting started with integration, you need to:

* [Create additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) in the system. They should be similar to the fields of the form.

## Step 1. Form Creation

1. Go to **Site → Integrated forms** and click the **New integrated form** button.

<Image align="center" width="80%" src="https://files.readme.io/e5cd13320315b5da6f441498b8ac2e221cc4d411cd2915a1edda88c21406cd5b-Integrated-forms-05-07-2025_11_31_AM.png" />

2. Enter the form name and select **Wix** in Services. Click **Next**.

<Image align="center" width="80%" src="https://files.readme.io/dae921890246895862d8759458f491ae2b1087a089176bbf78b340faf134b07f-Subscription-form-05-07-2025_10_25_AM.png" />

3. In **Add contacts to**, enable a segment where the contacts who fill in the form will be added.

* For the **New segment**, create a segment.
* For the **Existing segment**, select a segment from the list.

<Image align="center" width="80%" src="https://files.readme.io/d20fd93-Wix_3.png" />

4. Select what contacts to collect:

* **New**. Select to collect new contacts. Further, you will need to set Double Opt-In and select a confirmation email that will be sent to new subscribers automatically.
* **All**. Select to collect both new and existing contacts. For new contacts, you will need to set **Double Opt-In** and select a confirmation email that will be sent to new subscribers automatically. Existing contacts will not be sent a confirmation email.
* **Additional data only for existing contacts**. New contacts will not be able to subscribe through this form.

<Image align="center" width="80%" src="https://files.readme.io/29faa15-Wix_4.png" />

5. Click **Next**.

## Step 2. Integration with Wix

1. In **Wix websites**, enter your site URL.

<Image align="center" width="80%" src="https://files.readme.io/39589eb-Wix_5.png" />

2. Copy the Webhook URL and enter it in your Wix account as described below.

<Image align="center" width="80%" src="https://files.readme.io/e49a7305fccf6efb0cc0007f633de0dd6d91decd6883092855af7f91e8585e6e-Subscription-form-05-07-2025_01_35_PM.png" />

* In your Wix account, go to **Automations → New Automation**.

<Image align="center" width="80%" src="https://files.readme.io/58704c4fc6fa7a4f6a21133121ae9c14d415c1442a44d388f7cbeb772eace887-image4.png" />

* Select **Start from Scratch**.

<Image align="center" width="80%" src="https://files.readme.io/272a2a4d5797ff47f5df2e853628d4ea5bf0c4f476e7f0489a67df94805bf58e-image6.png" />

* Select **Wix Forms → Forms submitted** in trigger settings.

<Image align="center" width="80%" src="https://files.readme.io/bdd738961071f5ab0aff984e732261aefe68911ca6173aeae4f7110d3de0d16f-image9.png" />

* Select any or specific forms.

<Image align="center" width="80%" src="https://files.readme.io/f0d6cd50049987ab534f268abc60895086b86fda94686020cf88023cf48d2e71-image7.png" />

* Click + to add a step.

<Image align="center" width="80%" src="https://files.readme.io/4a9c1604830284fdd7db7cbe34450e0a54f39f6cdc552bdccae75bce37077520-image8.png" />

* Select **Action**.

<Image align="center" width="80%" src="https://files.readme.io/cb1b12080c04d82826b7bea78b9c9a1c5eb9baf5a55b1bb7b71e2a390e309cb2-image1.png" />

* Select the action type — **Send HTTP request**.

<Image align="center" width="80%" src="https://files.readme.io/700768324c3d47d8d022fa6b1ebdf1947c8f9aee041b3305816fd4ae19ba7090-image5.png" />

* Paste the Yespo Webhook URL and click **Apply**.

<Image align="center" width="80%" src="https://files.readme.io/e76eb3eb756bce62e6855c48483fd1bb6f703c2b67ea98a0aac2fa1649f6c874-image3.png" />

## Step 3. Field Mapping

1. Fill out the form and send the submitted data.
2. Click **Show data from Wix**.
3. Map it to the contact field.
4. Click **Done**.

<Image align="center" width="80%" src="https://files.readme.io/0633419315d0f68cd26d0eb2c734a12390347b70444bfdc39ba646b0aea21634-image1.png" />

## Step 4. Setting Parameters

Check and edit form parameters and actions after subscription on the **Parameters** tab.

<Image align="center" width="80%" src="https://files.readme.io/10eb319-Wix_12.png" />

When everything is set and checked, click **Save**. The created form will appear in the general forms' list.

<Image align="center" width="80%" src="https://files.readme.io/b6885431f5b61b425f3899ea34e0ff1eeac2bffb8c0fd3f6d766a6044befcf17-Integrated-forms-05-07-2025_11_29_AM.png" />

Here you can see the statistics on requests and the last update. To delete the form, click the three dots icon on the right.

> 📘 Note
>
> Requests display how many times the form has been filled and not the number of new contacts. One person can fill the form more than one time or fill the form but not subscribe.