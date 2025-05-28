---
title: Setting Up Data Substitution Using SRT Blocks
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Setting Up Data Substitution Using SRT Blocks | Yespo Guide
  description: >-
    Using Yespo CDP you can easily create automated content for your emails
    based on external data sources and email modules from your library. Read
    more in our article.
  robots: index
next:
  description: ''
---
The Yespo system can automatically create content for emails using external data sources and email modules from your library.

As a result, the converted data is connected to the modules in special stripes.

<Image align="center" width="80% " src="https://files.readme.io/0bda2a93e4442a1d2d545166399256f65b0e3ffad88e1656bff7b932bed4bcb7-SRT_1.webp" />

SRT defines the appearance and rules by which the system will insert data into the strip. The constructor has 3 sections:

* Start section – determine which modules to place at the beginning of the automatically generated area.
* Repeatable section – set a rule for displaying modules in each cycle. 
* Tail section – set a rule to display a specific module in case there are not enough items (products) in your data source to complete the entire cycle from the repeatable area.

<Image align="center" width="80% " src="https://files.readme.io/05747020b35d2d25176602c0fcbbb93828aeb4d9dcbf59db0e39b8e4fdcbb2d3-SRT_2.webp" />

## Theory. Basic SRT Settings

Before starting work:

* [connect one of the data sources](https://docs.yespo.io/docs/external-data-sources) (Google Sheets, recommendations);
* [set up smart containers](https://docs.yespo.io/docs/product-blocks-generator) for the selected source and save them to the module library.

Then you can start setting up the appearance of the blocks for substitution.

### Email preparation and SRT setup

Add a stripe to the email. Click on the background around the email in the editor and click on the “+”.

<Image align="center" width="80% " src="https://files.readme.io/ddfa1c5bccf611275334149f7c3519ed1c678d51cf604e4cc6ca30c7986ced9d-SRT_3.webp" />

Go to the *Data → Dynamic tab*:

<Image align="center" width="80% " src="https://files.readme.io/f19991e05c6c94029744e9289d86f2d36e1b0406e05197d53d1ba20ebfa11938-SRT_4.webp" />

Fill in the following fields:

<Image align="center" width="80% " src="https://files.readme.io/9a9dec38d7d0795f2a2dd8f0b9c9c96a957d4a1fd20507c8d4580469ae57eec6-SRT_5.webp" />

* Element name. 
* Data source.
* Select from the drop-down list what action to perform if the data source is empty:
  * Hide element,
  * Display element,
  * Do not generate email message. 

<Image align="center" width="80% " src="https://files.readme.io/9e2723e4b0d10c644084ac199a5785fd5ce08f4af5433ce16bf961e279ae6063-SRT_6.webp" />

Double-click on the stripe to enter values to substitute:

<Image align="center" width="80% " src="https://files.readme.io/2c6a73b3938ae6440ed072ac1121ed04df9ac48ee627409ce518b9c22b96a4ec-SRT_7.webp" />

Select the required structures from the module library and drag them into the email body:

1\. Start section\
Modules should be placed at the beginning of the dynamic element.

2\. Repeatable section\
Cycle modules and block substitution rules.

3\. End section\
Modules should be placed at the end of the dynamic element.

Completing all sections is optional. Sections #1 and #3 are used for static elements, which will be displayed as you define them. 

Let’s consider the second section for repeatable elements.

<Image align="center" width="80% " src="https://files.readme.io/991d266674811e383720174720e570e2dd89e250f9730a2715cf0b4aafa98c53-SRT_8.webp" />

### Setting up SRT (Repeatable section)

Use the repeatable section to flexibly control the appearance of the inserted data and the rules for displaying it in the email. For example, you want to substitute the products  in the following form:

* a module with three products per line;
* a module with two products per line;
* a module with one product per line (if one product is left in the source).

<Image align="center" width="80% " src="https://files.readme.io/89ae29ac629c17f44c2bea678a514d10bb2f34d8e4eb735d1af633fc1b61f0b9-SRT_9.webp" />

The system will insert products from the data source into the specified blocks and rotate them in the order 3+2+3+2 when sending an email. A single structure will be displayed if only one last item is left in the file.

Select the type of structure from the *My Modules* tab or the *Advanced* tab:

<Image align="center" width="80% " src="https://files.readme.io/c30231a2cb71987ba1b69b1fbb303d1050ffbbb3d02715d870cccc02930f0d4b-SRT_10.webp" />

Drag it into the email. An empty structure will be displayed, which you need to fill with smart containers.

<Image align="center" width="80% " src="https://files.readme.io/6314c3c2f8c35bf84c4ca98abb5b7790256aeb71d186af746870385ca895acdb-SRT_11.webp" />

> 📘 Note
>
> The container must have smart properties so that the system correctly substitutes the content from the data source.

You can immediately [proceed to test email](https://docs.yespo.io/docs/data-substitution-srt-blocks#sending-a-test-message) or set specific rules for displaying modules in emails. 

You can set the rules for displaying the entire structure

<Image align="center" width="80% " src="https://files.readme.io/4b3f7e8876fb00d25549fb218135a3b04e820cfdb973a64e92b9a103406bb91a-SRT_12.webp" />

or each container separately.

<Image align="center" width="80% " src="https://files.readme.io/947ff6c2ebeda371ad89066c8b270f9b09e3300cdbb3a89e024ee351074fbfa2-SRT_13.webp" />

Here are examples of which setting option to choose:

**1\. Structure settings.** Two products must be displayed in the structure. But the feed can contain an odd number of products.

Then we add two structures: for 2 products and below — for 1 product. For the structure for 1 product, add the rule *Apply only if a specified field is present in the data source* and write the value *1*. If there are 4 products in the feed, they will be displayed 2+2. If there are 5 products in the feed, they will be displayed sequentially 2+2+1.

**2\. Сontainer settings.** For example, there is a discount only for certain products, and you want to display crossed-out prices. To do this, create two containers:

* the first – new price + crossed-out old price;
* the second — only the current price.

Add a rule: if the product has the *oldPrice* field, show the first container, if not, the second.

#### Structure settings

To set the structure settings, select the desired block. A menu will open on the left, where you can:

* *Leave current* – the appearance of the block will match the added one. Use this option when you need static data. For example, a banner or description: *You have viewed these products, You will be interested...*
* *Apply another* – only an empty structure will be displayed, which must be filled with smart blocks for data substitution.

<Image align="center" width="80% " src="https://files.readme.io/15d3ed107c60670500fabf83c81292f033642559501f5071e4a25e726c50e275-SRT_14.webp" />

*Columns* will become available for the latter option after adding smart blocks, where you can set rules for each horizontal or vertical column separately.

<Image align="center" width="80% " src="https://files.readme.io/539fc76356cba94cc8d5ad5f1fbff55e08f46216ff3ad97cea6f01dc30559098-SRT_15.webp" />

There must be no empty structures in the option with columns: everything needs to be filled with data since empty elements will not be displayed.

Then you can add rules that are the same for blocks and structures.

#### Container settings

Please note that you cannot change the appearance of containers in the SRT constructor itself. You can edit it in a parallel tab or return to the email. After making changes, you need to update the block in the library.

By settings, we mean the rules for displaying content in email and filling it with content.

You can choose whether to fill it with data or not for the container.

<Image align="center" width="80% " src="https://files.readme.io/55c1386075d49553dedc31017fd9a9134709531028c92f4ab5b8ce3285820157-SRT_16.webp" />

If you select *No*, the information will remain unchanged, the block will be static.

For example, *No* is selected for the left block and it remains static, while Yes is selected for the right block, and cards change in it.

After choosing an option, you can proceed to the rules or directly to testing.

### Rules for Blocks and Structures

#### Option 1. Apply only if a specified field is present in the data source

<Image align="center" width="80% " src="https://files.readme.io/30fd806ed14aeafdfc3e7bdc26d548bc1643666b4e83a0226774a79c9509bf56-SRT_17.webp" />

**How it works**\
For example, we want to display the old price of products that have a discount.

1\. First of all, we create an alternative container for which the *Or* mark will appear:

<Image align="center" width="80% " src="https://files.readme.io/63acaa1509be43a880b8bcfd16515ea0a575479ee863668fd1d0f8354c939b4f-SRT_18.webp" />

2\. Set the settings for the lower container, taking the required variable from the data sources. In our case, this is the name of the *oldPrice* column.

3\. Write the variable in the field precisely as indicated in the table.

<Image align="center" width="80% " src="https://files.readme.io/32c901e176189f734a86db3f5040da7d9bcd44aaf23a975f3154166687adad94-SRT_19.webp" />

Thus, for products with the old price, it will be displayed in the card.

#### Option 2. Apply only if there is a specified number of records left in the data source

<Image align="center" width="80% " src="https://files.readme.io/e5572b331bfd100aa95a537ba97caf5c8cce499cba61f638557d838f8481b822-SRT_20.webp" />

**How it works**\
For example, the source uses an odd number of products.

<Image align="center" width="80% " src="https://files.readme.io/ca217cfb58f4dc8a176145dea013215a7be6b92a9be1b64cd39858a760e5245a-SRT_21.webp" />

The data structure will be displayed only if all the products have already been included in the email and there is only one left.

#### Option 3. Apply only to a specified cycle (loop)

<Image align="center" width="80% " src="https://files.readme.io/1012f53ee667d8a3cc5822003820bddcf8ca682d6f4f98e2d90a743804ce1387-SRT_22.webp" />

**How it works**\
For example, we have 12 products and need to show the CTA button after 6 products.

<Image align="center" width="80% " src="https://files.readme.io/e3739be4be47bf20a529f5e3303c5bb1229a34d53d01a079bb8b64e1e790a2c6-SRT_23.webp" />

We add a structure with a button and specify that it should only be used for the 3rd cycle.

It turns out that the first two cycles contain 3 products each. After their substitution, the CTA button will be added, then products.

> 📘 Important
>
> The condition is applied to the loop once.

#### Option 4. Apply only to cycles with a value that is multiple of a certain number

<Image align="center" width="80% " src="https://files.readme.io/337292715c74b2c0c3aa0245cf871f65dc9cfe47c04f9af2307976525daf6c8f-SRT_24.webp" />

**How it works**\
The setting is similar to the previous option, but will apply to all cycles that are multiples of our value.

For example, we have 12 products, and we need to show the CTA button after every 6 products.

<Image align="center" width="80% " src="https://files.readme.io/85bedd45ab322d9090012fc16969ec24d6e81ed39a8806b4304c8d9f5ed4fc63-SRT_25.webp" />

We add a structure with a button and specify that it should be applied for every loop with three products.\
Cycle #1 and #2 contain 3 items each. After substituting them, the CTA button will be added to cycle #3, then again two cycles of 3 products each — and the button will be displayed again.

#### Option 5. Apply to all cycles starting from a specified one

<Image align="center" width="80% " src="https://files.readme.io/30c29e0d13747fb44a05a19fb929d09de9f4ce0305a78543942bbb0f3d723e65-SRT_26.webp" />

**How it works**\
This rule will help us to use different layout options and display products differently from the selected cycle.

For example, it is necessary that at first, there was a layout of blocks of 3 products in a row, then it changed to 2 products.

We specify 5 for a block with 2 products, which will display this type of layout only from the 5th cycle.

<Image align="center" width="80% " src="https://files.readme.io/b4cd8844fdad369275f41dfedb1d009bfbf3c6724aef50289a93fc6a8ac08024-SRT_27.webp" />

#### Option 6. Apply until a specified cycle (loop)

<Image align="center" width="80% " src="https://files.readme.io/946e841b1eb92ad1ddcf4f979285ae28914f60eecb8b1defea990589d2d234e3-SRT_28.webp" />

**How it works**\
This rule, similar to the previous one, will help you use different layout options, but only UNTIL the selected cycle.

For example, it is necessary that at first there was a layout of blocks of 3 products in a row, then it changed to 2 products.

We specify 5 for a block with 3 products, which will display this type of layout only up to the 5th cycle.

<Image align="center" width="80% " src="https://files.readme.io/92b68f0525567bd599729c1ef6e61638369e015f7fa81067ae95e52a3f85fe99-SRT_29.webp" />

Starting from the 6th cycle, the appearance will change to two products in a row.

#### Custom code

The custom code is generated when you make changes through the SRT constructor, or you can write it yourself. For example, if you need to copy a code from another email or view the stripe structure.

<Image align="center" width="80% " src="https://files.readme.io/edaaa5935303add44005840298c92582d73fb8730857ea9b1ff8f6a528a49417-SRT_30.webp" />

## Part 2. An Example of Creating SRT Email

Before creating a letter, connect at least one data source in your account (*Settings → Data sources*).

### Creation of email blocks. Preparatory stage

You can create an email completely in a dynamic stripe by filling in all sections or partially using only one. Consider creating an email with filling in all sections.

1\. Create and save the *Header* structure to the block library.

<Image align="center" width="80% " src="https://files.readme.io/d05a1ade4c24fbd8716d42635c2aee441bedc35fcaa67345daba988a8b883bb8-SRT_31.webp" />

2\. Create an empty structure with two containers and add it to the module library:

<Image align="center" width="80% " src="https://files.readme.io/f504a7f98a2d80e83d43e22edb70685572c45435e5ff0032b7d20d0f10d0fc83-SRT_32.webp" />

3\. Separately create a smart block in the structure for two containers and save it to the library. In our case, the data source is Google Spreadsheet. The field names in the table are our substitution variables.

<Image align="center" width="80% " src="https://files.readme.io/8b628a6cdb14e89ce10be3f396711d63c08d114f95f602d75a52a1e9f3896dcc-SRT_34.webp" />

You can use ready-made smart blocks from the library: *Modules → Advanced → Product cards*.

 You only need to change the names of the variables and save the updated block to the library. It could be easier and faster than creating your own blocks.

Please note that it is the containers you need for substitution in SRT. Therefore, you can save the blocks and structure separately to make it easier to fill the SRT strip.

4\. Create a smart block with the old price crossed out in the structure for two containers and save it to the library.

<Image align="center" width="80% " src="https://files.readme.io/940c0e2a1b046b08ea9b030d4a6b9458db12700836587005a596c0181ce86322-SRT_35.webp" />

Use variables from a data source; for example, in Google Sheets variables are the names of the columns.

5\. Create and save a structure with a button to the module library.

<Image align="center" width="80% " src="https://files.readme.io/b8a3e23c0fe15c4efe9feb0e93b6fe58d521112c4913b71e073568d79fa459de-SRT_36.webp" />

### Setting up SRT in email

1\. Go to the strip settings and click *Dynamic*. Then we give the name of the element, select the data source specified in the smart blocks, and what to do if the source is empty.

<Image align="center" width="80% " src="https://files.readme.io/5ed22c03355da85732971543bdde60c81b51e1d672a36247996bd2e30edb0b1e-SRT_37.webp" />

2\. By clicking on the SRT stripe, open the constructor:

<Image align="center" width="80% " src="https://files.readme.io/70cc14e65434a34c67ea4d221af5ee2a0837ea1882b800835361ab76d340b0ef-SRT_38.webp" />

Optionally, add the *Header* structure from the modules to the start section, click on it and select *Leave current* on the left:

<Image align="center" width="80% " src="https://files.readme.io/0c1240d5f2edeaa8f8b02a021c16f8e54de7e38351de93381ef523fcf108fc15-SRT_39.webp" />

3\. Add an empty structure from the modules to the repeatable section:

<Image align="center" width="80% " src="https://files.readme.io/2478b7b940590ab3a9416f5a950674c664c0cffdb148b428f5dcd3dca68d6b4b-SRT_40.webp" />

4\. Drag smart blocks with the old price into it.

<Image align="center" width="80% " src="https://files.readme.io/e734ac002fb6b2afd31f038194843680d4b8606ac7448e4ad28f8548f6200e13-SRT_41.webp" />

Drag smart blocks without the old price under them.

5\. Select each container with the old price and add the rule *Apply only if a specified field is present in the data source*. If there is *oldPrice*,  the customer will see the old price crossed out.

<Image align="center" width="80% " src="https://files.readme.io/5164a74adc17266bae4ed415975067a8e4c671d6bfef08efb8c82346b0bbb34f-SRT_42.webp" />

6\. Add a structure with one product in case there is an odd number of records in the source. We select the rule *Apply only if there is a specified number of records left in the data source* for it and write *1*. 

<Image align="center" width="80% " src="https://files.readme.io/4f51be2231b918ff74ce74046eee8c5ee5ae3927f8dfff711f2d9055bc5aa0ba-SRT_43.webp" />

The structure with data will be displayed only if all the products have already been included in the email and only one is left.

7\. Optionally, add a structure with a button from the modules to the closing section, click on it and select the *Leave current* switch.

8\. Save changes.

### Sending a test message

To test the data substitution, send email via the *Test* button in the editor.

<Image align="center" width="80% " src="https://files.readme.io/3a32b308bc049b9065ef0fcede21c07d53e49b5a1009cb6a57ab2d45e85c8633-SRT_44.webp" />

Or send the test in the message list through the *Create campaign* button,

<Image align="center" width="80% " src="https://files.readme.io/bcffca159160777f2badc4716ece2ef7fbb73798d3a9c40d2ff6c7b8879a15b5-SRT_45.webp" />

by selecting the recipient in the *Contacts* tab.

<Image align="center" width="80% " src="https://files.readme.io/e93f1624e751e05da44c6641cdfa6ffff3eff72903657617688a2e01986a2ebf-SRT_46.webp" />

Read also [how to set up a recommendation email](https://docs.yespo.io/docs/designing-recommendations-email).
