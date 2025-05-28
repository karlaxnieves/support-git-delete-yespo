---
title: Setting Up Smart Containers
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Smart Containers | Yespo Guide
  description: >-
    The document explains how to set up smart containers for emails for
    auto-filling data in product cards
  robots: index
next:
  description: ''
---
A smart container is a template element consisting of basic blocks (image, text, button), the content of which is automatically inserted from the site. 

If your website uses Open Graph (OG) tags that provide structured data about the content of the web page, it allows the system to automatically insert information about products into the email.

When data from the website is not supplied, or additional product parameters need to be displayed, you must manually add parameters to existing cards.

This guide will cover how to check if the content card autofill is functioning and how to manually adjust settings if necessary.

## Automatic Data Substitution from the Website

You only need to copy the product's URL and paste the link into the container to implement this method. After that, the system will automatically fill in the corresponding data in the email.

1. Go to *Messages → Messages → Email*. Open an email or create a new one.

<Image align="center" width="80% " src="https://files.readme.io/4accb860dba089f7880910889effdd6562f851f219c8cc3e7c6b69fbbdbd2d03-setting-up-smart-containers-01.webp" />

> 📘 Note
>
> When using an email with a [custom design](https://docs.yespo.io/docs/designing-your-email), the design styles are immediately applied to all objects added from the module library.

2. Go to *Modules → Advanced*. Select the *Product Cards* category and add the ready-made module.

<Image align="center" width="80% " src="https://files.readme.io/67fad87babe9bc20dbc117971347a9ed880eb9ceef410d399db77089751795ea-setting-up-smart-containers-02.webp" />

For example, let's take a module with cards containing:

* Product image
* Name
* Price
* Button

3. Drag the card to the email.

<Image align="center" width="80% " src="https://files.readme.io/8665029f3d8c664b1263e112b0739d4c52edc55b1dbc992894a8f40640e812dc-setting-up-smart-containers-03.webp" />

### Data Substitution 

1. Open the product page and copy the URL.

<Image align="center" width="80% " src="https://files.readme.io/926328841eedc694b1ae5703fa3e2d5c9f3c45d243a77492bf34ce552ea1f769-setting-up-smart-containers-04.webp" />

<br />

2. Click *Smart-Container → Data → Smart* in the menu on the left and paste the copied URL in the *Link* field.

<Image align="center" width="80% " src="https://files.readme.io/f97d00f0e5335a62680f019a91273df303cf989bbe47cd85a54e5305527c0365-setting-up-smart-containers-05.webp" />

3. The system will substitute the data:

<Image align="center" width="80% " src="https://files.readme.io/4506b03e6db0b8c8d401c3c4b453e776c434d056246ccbb34409d1be08d43338-setting-up-smart-containers-06.webp" />

4. All parameters will be filled except for the [button](https://docs.yespo.io/docs/creating-cta-button) name, so change it and duplicate the module further.
5. Paste the copied URLs for each product in the email.

<Image align="center" width="80% " src="https://files.readme.io/6ca638c9dcdf203704e6c21363fe3a223ce43ed57ade73403909da3de7c9bf31-setting-up-smart-containers-07.webp" />

6. Save your customized [structure](https://docs.yespo.io/docs/adaptive-email-builder-review#structures) to the module library for use in other emails.

<Image align="center" width="80% " src="https://files.readme.io/52c59aaf9951eac7b1c18d045cd5125e72c615788afee1bf1346e9bd499d7469-setting-up-smart-containers-08.webp" />

## Adding Parameters to Existing Cards

This method of setting up smart containers is more labor-intensive and requires certain technical skills; however, it provides a more flexible approach to customizing email content.

When using this method, you can add various product parameters, such as color, article number, country of origin, discount amount, promotion duration, etc. This is especially useful if you have diverse products with different characteristics.

To set it up, you need to perform the following steps:

* Add blocks to the email, specify variables and matching rules for them,
* Substitute a CSS selector element.

Let's consider an example where you need to add information about the availability of a product to an existing module.

### Editing HTML Code

1. Add a *Text block* with the “Product availability​​” text to the container. 
2. Click on the *Smart-Container* located at the top of the container.

<Image align="center" width="80% " src="https://files.readme.io/60b9eec185e540022bc5937aefebee01e5fb807e34d1b6f38fb2296fd32e2c04-setting-up-smart-containers-09.webp" />

3. Click the *Code* icon on the editor panel and open the code for this block.

<Image align="center" width="80% " src="https://files.readme.io/1ddffa7e019f595fd1c5c0f2acba78453e58b324689f1520bd8564440e66222b-setting-up-smart-containers-10.webp" />

4. Add the class attribute to the "Product availability​​" field: **class="Availability"**.

<Image align="center" width="80% " src="https://files.readme.io/bab1ec9f87e7fe3e75b16ce46e5eaa5ffc70f4c3554c32ab9973de80229a7dac-setting-up-smart-containers-11.webp" />

### Adding Variables and Matching Rules

1. Go to \_Data → Smart → Configuratio\_n in the container settings.

<Image align="center" width="80% " src="https://files.readme.io/f7da83febc9b8458f167218119626e93eaa473b081def9e36a20e59b4f79714e-setting-up-smart-containers-12.webp" />

2. Click  *\+→ Variable var* .

<Image align="center" width="80% " src="https://files.readme.io/80608af37eda701fd9291315fae150014405c128cd55bd6314bf194fd35fc233-setting-up-smart-containers-13.webp" />

3. Add the *p\_availability* variable and name it *Availability*.

<Image align="center" width="80% " src="https://files.readme.io/f6e6fc7900efcc7e775dd57df71799fd28c7b9a36aeab89218e01e662f6d8b31-setting-up-smart-containers-14.webp" />

4. Go to the *Matching rules* section, select the *Internal* tab, and, specify the “**.Availability**” selector -  for the *p\_availability* variable. Leave the *Attribute* field empty.

> 🚧 Important
>
> The CSS selector's name is case-sensitive and must match exactly the class attribute name specified in the code.

<Image align="center" width="80% " src="https://files.readme.io/2cddeceb7f4ea5b6f4f53d4fad9d8dd2c7d84c82edf25735e5c37b94e6e349ec-setting-up-smart-containers-15.webp" />

5. Go to the *Appearance* tab. If everything is done correctly, the *Availability* field should appear.

<Image align="center" width="80% " src="https://files.readme.io/7e1d31b542c6350a19dbd0887ec195ae089dc4a829492fcc070a422db7be9fd2-setting-up-smart-containers-16.webp" />

### Substitute the CSS Selector

1. Go to the product page in your browser.

> 📘 Note
>
> The example covers the basic way of inspecting elements on a web page using DevTools in Google Chrome for Windows. If you use another browser or operating system, refer to the documentation for using DevTools and inspecting elements specific to that platform.

2.  Press *Ctrl + Shift + I* or F12 on your keyboard to open *DevTools* and Inspect the page element.
3. Press *Ctrl + Shift + C* or click the cursor icon in the top left corner of the *DevTools* panel to select the *Inspect Element* option.

<Image align="center" width="80% " src="https://files.readme.io/3a86dc6805b60ce28617d7bcc6e50998ddae7117818af723e29076de26aa3670-setting-up-smart-containers-17.webp" />

4. Select an element on the page by clicking the left mouse button. In our case, it is *In stock*.

<Image align="center" width="80% " src="https://files.readme.io/321a0b9c75148c521cda953a429531d2ca4ba86fb5b9d348d3a4e6e81823a424-setting-up-smart-containers-18.webp" />

5. In the code editor, right-click and select *Copy selector* from the drop-down menu.

<Image align="center" width="80% " src="https://files.readme.io/1d712e8841c2246f312cf827f08592840d0cac4c009bc25d5599cb0c5ebad103-setting-up-smart-containers-19.gif" />

6. Go to the *Matching rules* section in the smart container and select the *External* tab.

<Image align="center" width="80% " src="https://files.readme.io/9a277e24cf9e910bc94f8a247bda9372a81bbcc8c201e0b8a4762f8241e22888-setting-up-smart-containers-20.webp" />

7. For the *p\_availability* variable, paste the copied selector into the *CSS selector* field. Leave the *Attribute* field empty.

Information about the availability from the product page will be inserted into the container.

<Image align="center" width="80% " src="https://files.readme.io/eea72c9e1d4b9dee3e0fcf48240318f55c4cb209bd564efc7d9284af581fa572-setting-up-smart-containers-21.webp" />

> 📘 Note
>
> Websites usually use standard CSS selector names. Setting up smart containers should work for most pages following CSS standards. However, some pages may have unique selector names and attributes. These might need advanced settings or creating new smart containers.

The steps to set up a new container will be similar to those outlined in the [*Adding Parameters to Existing Cards*](https://docs.yespo.io/docs/product-blocks-generator#adding-parameters-to-existing-cards) section. However, adding variables and mapping rules need to be specified for each element.

If you have questions about setting up smart containers, please contact us at [support@yespo.io](mailto:support@yespo.io).
