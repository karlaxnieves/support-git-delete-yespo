---
title: Editing Cards in the Products Block
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Editing Cards in the Products Block | Yespo Guide
  description: >-
    Learn how to edit product cards in the Products block, which allows you to
    display recommendations in an email without using code
  robots: index
next:
  description: ''
---
The *Products* block displays recommended offers in the email. Let's consider how to change its appearance and save the product card as a module for use in other messages. Using the same algorithm, you can save the footer and header of the *Products* block as modules.

> 📘 Note
>
> Before editing cards of the block, [set up its structure and data substitution rules](https://docs.yespo.io/docs/product-blocks)

## Editing Card

1. In the *Messages → Messages* section, open or create an email and drag the *Products* block into it.

<Image align="center" width="80% " src="https://files.readme.io/e374c54edfa21ba0a9047ce1fb882d96079ec37d9e9c66261264ab20ea53c936-products-1.webp" />

2. Open the *Structures* tab on the left panel.

<Image align="center" width="80% " src="https://files.readme.io/b1cc6a90aa8e8a7de0899a628b4c72217c54caddc077783d713ab5685fd5eb8f-products-2.webp" />

3. Drag the desired structure anywhere in the content. The structure's location in the email does not matter since it must be deleted after editing and updating.

We recommend choosing a structure with the same number of containers as in the *Products* block.

The example adds a structure with two containers.

<Image align="center" width="80% " src="https://files.readme.io/864c9e1afb989cb726c760787d4c2ce3f374e664aac8baaf55219f130a7dbaf8-products-3.webp" />

4. Click on the *Products* block in the email and go to the *Modules* tab.

<Image align="center" width="80% " src="https://files.readme.io/aa155112007d3b242f8007c67be381cf390615b8ab9c1917e11166c5227310ab-22-modules-tab22.png" />

5. In the *Product* card section, copy the module's name used in the block.

<Image align="center" width="80% " src="https://files.readme.io/40f80e034c59c175db6ce80ebc52cd1be152cd9779b77b67c8f1dc6ea7516125-22-card-name.png" />

6. On the left panel, open the *Modules* tab.

<Image align="center" width="80% " src="https://files.readme.io/c2d6757ef0fa025a15a27516479ff1a135ad87e721fcf2613e7186e54e921616-products-6.webp" />

7. On the *My modules* tab, paste the module name you copied in step 4 into the search field. If the module is not found, this means that by default, the *Products* block uses a module from the general library, which is presented on the *Advanced* tab. Open it and find the appropriate module.

<Image align="center" width="80% " src="https://files.readme.io/3b84e336dd6738db8045a894dfab6ad75402b4f52de64ddd02acb71dd2dedd8f-products-7.webp" />

8. Drag the module into the structure added at the beginning of the settings. In the example, the module is dragged into the left container.

<Image align="center" width="80% " src="https://files.readme.io/4f9f362237837ec3122de44996541542bb8b7c26f440c2928029429dfb2a7f47-products-8.webp" />

9. Make changes to the card using the options on the left panel. In the example, the color of the button has been changed.

<Image align="center" width="80% " src="https://files.readme.io/c2e0f612ac010afe0705421a1609ca84049bbcc3b73dc21838a3915ddba577fe-products-9.webp" />

> 📘 Note
>
> To change price currency and format, leave a request to [support@yespo.io](mailto:support@yespo.io)

### Adding Product Parameters to Card

By default, variables for the following parameters are available in the product card:

* Link
* Name
* Title
* Description
* Image
* Old Price
* New Price

You can add any other parameter from the product feed to the card, such as the book author's name.

Follow these steps:

1. Add a block to the container of the product card to display the parameter (for example, a text block for author data). For convenience, insert the corresponding text (*Author*) into it.

<Image align="center" width="80% " src="https://files.readme.io/b8d9825f312d5647639023e828aa9f8899e5d5ae312d5984f46400af528064e7-add-parameter-1.webp" />

2. Open the code of this block by clicking the corresponding icon on the editor panel and add the class attribute to the *“Author” field: class="Author".*

<Image align="center" width="80% " src="https://files.readme.io/82dab7a5778bc8e639cb24faf7d2c5860f404291541a8639a282d2aeaecf1bb9-add-parameter-2.webp" />

3. Select the Smart container, go to the *Data → Configuration* tab, and click the + icon.

<Image align="center" width="80% " src="https://files.readme.io/49a3cf1857d49821b58ba75e463fab9d6f392b2cd5943a7f158a6a7615874489-add-parameter-3.webp" />

4. Select the *Variable* option from the list.

<Image align="center" width="80% " src="https://files.readme.io/7b998c3878c48cdb427ce768b0b103165e1309a381928a2fe9567b4cbbb2ff0e-add-parameter-4.webp" />

5. Enter the name of your product feed parameter in the *Variable* field and a custom name in the *Name* field.

<Image align="center" width="80% " src="https://files.readme.io/38d9d9078a78cf3b0cb6089ca5e1d8d91f2ba68bf0037d9d85eb4d01ea7d4360-add-parameter-5.webp" />

6. Go to the *Matching rules* section, select the *Internal* tab, and specify the email block selector (in our case, *.Author*). In most cases, the *Attribute* field can be left empty.

<Image align="center" width="80% " src="https://files.readme.io/1b8290abfe428b786c59792b83c9d1f099e2c562a9518afcfd9187496e5b8ed1-add-parameter-6.webp" />

> 📘 Note
>
> The CSS selector name of the element is case-sensitive and must match the class attribute name specified in the email code.

7. Go to the *Appearance* tab to check that the corresponding field has appeared there.

<Image align="center" width="80% " src="https://files.readme.io/152418cd086d0eeb704da7f2569c851ed51da865710499067f2fcf34ddba57d6-add-parameter-7.webp" />

8. Go to saving the card as a module.

## Saving a Card as a Module

1. After making changes, select the entire module, hover over the additional menu (3 dots), and click *Save as module*.

<Image align="center" width="80% " src="https://files.readme.io/5972f362692a87870896822efe609ed064046f413db98cd8341fbab34b4431eb-products-10.webp" />

2. Click *Save* or *Update* at the bottom of the left panel.

<Image align="center" width="80% " src="https://files.readme.io/ba86132148d2976fbbb29f22e64a132821972de913a3b7e552079f42392cf923-products-11.webp" />

If the module is being created and not updated, the block in the email must be updated manually:

1. Click on the *Products* block in the email and go to the *Modules* tab.

<Image align="center" width="80% " src="https://files.readme.io/e8dc3b7b0c5f00e0a7a8e674d3f583fa2b743be0e9d30de6cca2973f955edf10-11-modules-tab.png" />

2. Click the *Replace* button in the *Product card* section.

<Image align="center" width="80% " src="https://files.readme.io/7975bc5473cadade5b5296eaa3a73512d688cc6c92bf1e26e8ac4c89dcb565ca-products-13.webp" />

3. Select the product card module you just saved.

<Image align="center" width="80% " src="https://files.readme.io/c0ea2d52404353e7ec1d4ccfc5f66e6a15dc443e17d857320c1eb15055e0f1e5-products-14.webp" />

The *Products* block will be updated after the selection window is closed.

<Image align="center" width="80% " src="https://files.readme.io/5adcd39d74ede21f51b94d4a0fec29c7b826d227ea2d3a111551602d5cb4d0e3-products-15.webp" />

### Updating Modules in Messages

If you have updated a module in the module library, and it is already used in the *Products* block in a message, that block will be marked with the *Off* icon, and a warning will appear on the *Modules* tab. This indicates that the library has new versions of the modules, while those used in the message are outdated.

<Image align="center" width="80% " src="https://files.readme.io/ac578559429e40264d51167b8dcdaf2dbf06fd1d64a747f0c5c190d269e156fa-module-update-01.webp" />

To update the module in the email to the latest version, follow these steps:

1.  Select the block and go to the *Modules* tab.

<Image align="center" width="80% " src="https://files.readme.io/dfc0e79bc614b82519b5aa3cff5480462420ef054c9d6c6721e11db1b9d9e92c-module-update-002.webp" />

2. Click the *Update module* button.

<Image align="center" width="80% " src="https://files.readme.io/f0db344c7e2d771fd471bcdf062e13e477e763275808d029366ed304521813f3-module-update-003.webp" />

3. Save the changes in the email.

<Image align="center" width="80% " src="https://files.readme.io/d992728154aeacbcaa3980f945a14539dd97a7e6fd698aae222490ed5af329a5-module-update-004.webp" />

> 📘 Note
>
> Module updates are the same for headers, footers, and product cards.
