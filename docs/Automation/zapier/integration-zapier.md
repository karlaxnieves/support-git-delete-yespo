---
title: Integration via Zapier
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Integration via Zapier | Yespo Guide
  description: >-
    Save your time with the CDP / Zapier integration. Automate processes,
    connected with uploading/downloading files between two services,
    applications, or/and CRM in several clicks.
  robots: index
next:
  description: ''
---
Zapier is a service that allows you to connect different platforms and tools to automate data transfer and perform routine tasks. With Zapier, you can easily set up actions that happen automatically when certain events or conditions occur.

Here are some of the main benefits of using Zapier:

* **Improved productivity:** automation of routine tasks, such as sending emails or notifications via instant messengers; Zapier allows you to reduce manual work and focus on more important tasks.
* **Integration of programs and tools:** connecting platforms that do not have built-in integration tools; for example, you can create connections between your CRM systems, email, social networks, etc.
* **Marketing automation:** sending emails, nurturing leads, working with social networks, and other tasks to attract customers.
* **Improved communication:** notifications from the chat messaging service about important messages.
* **Analysis and reporting:** automate the collection and transfer of data to analytical tools for analysis and reporting.

## What is Zap

A Zap is a connection between one or more platforms consisting of 2 elements:

* **Trigger** — an event whose data needs to be transferred from platform 1 (for example, filling out a Google Form);
* **Action** — an action that must be performed on platform 2 (for example, creating a contact in Yespo).

<Image align="center" width="40% " src="https://files.readme.io/6457fef44de186c83ea9babb652e5c5bcf10eedcabfc1689c15e4920544cb129-image16.webp" />

## Possibilities of Zaps in Yespo

List of Yespo events that you can stream in Zap:

* **New Contact** — triggers when a new contact is added;
* **New Contact in Segment** — triggers when a new contact is added to a segment.

<Image align="center" width="80% " src="https://files.readme.io/4a603c20a85a8d9047f2dd875f4749b45953e6637107f6aced79284a0a769220-image4.webp" />

> 📘 Note
>
> Thanks to [dynamic segments](https://docs.yespo.io/docs/how-add-dynamic-segment), the *New Contact in Segment* event becomes extremely multifunctional. For example, you can set up an alert if a new contact appears in dynamic segments of customers with an average bill of more than $1000.

List of actions in Yespo that can be performed after submitting a Zap:

* **Add/Update Contact** — adds confirmed contact or updates existing contact;
* **Send Email** — sends an email using a specified message template;
* **Send Event** — sends an event to user;
* **Send SMS** — sends SMS using a specified message template;
* **Subscribe Contact** — subscribes a contact.

<Image align="center" width="80% " src="https://files.readme.io/c0a19087ec9cc66f229098955be624c46465b86db8a5a3b94ce40198196223f2-image3.webp" />

## Setting Integration (Using Google Forms as an Example)

Create a Google Form to collect contact data and configure sending responses to Google Sheets.

<Image align="center" width="80% " src="https://files.readme.io/e8e49f9e452f8054b877b58c6f61fdce3ed4582762ada9bc6058d1787cebddda-image19.webp" />

Fill out the form — Google Sheets should record your answers.

Proceed to a Zap creation.

### Creating a Zap

1. Sign up in <a rel="nofollow" href="https://zapier.com/sign-up/" target="_blank"> Zapier</a>.
2. Click *Create Zap*.

<Image align="center" width="80% " src="https://files.readme.io/3cdc44edb9b3e26dc17972b4ee1a67178b7973dbc14b4a141d87d4027af3b42c-image15.webp" />

3. Enter Zap name.

<Image align="center" width="80% " src="https://files.readme.io/6759d1a92120d30262155c8f53d2b9e919af54a6cfa1cca49f0de6019d1f6ec8-image14.webp" />

#### Creating an Event

1. Click on the *Trigger* spacer.

<Image align="center" width="80% " src="https://files.readme.io/ca4e922d1065f213ba8bef2a7379ba1516307d89a32776434eb13dea9eabdd92-image17.webp" />

2. Select Google Sheets.

<Image align="center" width="80% " src="https://files.readme.io/5046027ca8ac2a9c24c528b4a6d5cf0875b4b7e8a769cdeb19e9666058618c9a-image5.webp" />

3. Select *New Spreadsheet Row* from the list to create an event every time a new row appears in the spreadsheet.

<Image align="center" width="80% " src="https://files.readme.io/f7f0f8c8d5a66f4c9ee264d6f7f0538292c9f4779ff34fc34b464f026c4b3d5c-image24.webp" />

4. Click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/be9ae0f69c7189202c56e493df7f2eef21fd5c14179a1ab72290a7b456670438-image22.webp" />

5. Log in to Google Sheets and click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/9e2e1dbd6250cbdba20cede57b8de8526a6fc244761497759918f4c135c437cd-image21.webp" />

6. Specify the spreadsheet and worksheet where the data from the form is transferred; click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/9e467cb0c8be8c6aec586fbedda2cef8210222dac88bf8cce884b08810672d03-image1.webp" />

7. Test the connection.

<Image align="center" width="80% " src="https://files.readme.io/67ae85e1a73f8438d8597ee6e035f482c72d62ca603684d4806bee73f6e03c27-image25.webp" />

As a result, you should see the data you entered into the form. Click *Continue* *with the selected record* to go to the action settings.

<Image align="center" width="80% " src="https://files.readme.io/b0410de48050775cd1bf207270c0fedeafcaa63640987297739dd993dec9891e-image11.webp" />

#### Creating an Action

1. Choose an action: enter Yespo in the search field and click on the corresponding spacer.

<Image align="center" width="80% " src="https://files.readme.io/a998aea194ec160401239f34721631604133d55406fed5bbdafd6dabbd38afa9-image7.webp" />

2. Select the *Subscribe Contact* event from the list.

<Image align="center" width="80% " src="https://files.readme.io/43fffa840b045398b93ccb2613252440f1ec47b88f947a9d126e90950ef41f9d-image9.webp" />

3. Click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/ea38fdb4e713c045b2ddcfb0619b525975f5b84096d0c0a143afb59c68fb6bf9-image20.webp" />

4. Log in to Yespo and click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/18934605070f3d0e191e79a0523d147295a675c114945c43765470c5acaadede-image18.webp" />

5. Match the contact fields in your Yespo account with the answers in the table.

<Image align="center" width="80% " src="https://files.readme.io/451e1263b2a5e53c30184ee11abade3a995509bd134cd83ca3a76dd968bab25c-image23.webp" />

You can also choose in the *Action* list:

* segment to which contacts from the form should be added (*Segments* field)
* form name (*Form Name* field).

<Image align="center" width="80% " src="https://files.readme.io/bdbc5ebd063532da2135f581c171047354cc7982dbf136cecb1cdb0f90b90c91-image10.webp" />

> 📘 Note
>
> The form name appears in the event name that is sent to Yespo. For example, suppose you specify the **Test** form name in the Zap settings. In that case, when the contact fills out the form for the first time, the **subscribeFromApi-Test** event will be sent to Yespo, and when they fill it out again, **subscribeUpdateFromApi-Test** will be sent. You can connect [the double opt-in workflow](https://docs.yespo.io/docs/subscription-form-configuration) to the first event; the workflow for the second event can include a block to check if the contact has confirmed the subscription and other blocks depending on your tasks.

6. Click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/eb07eb995d956f36132d5e2a60bf8f813e4c70addb0f319482704bae1acd49c0-image8.webp" />

7. Test the connection with Yespo.

<Image align="center" width="80% " src="https://files.readme.io/01363d6dd0a9a4f2ee153e4c74477e4bedbce610034ab438366b58f99c16c3b7-image12.webp" />

As a result, you should see the contact data that you entered in the form in Yespo contacts (*Contacts → All contacts* tab).

<Image align="center" width="80% " src="https://files.readme.io/66d780a4259011c9c7dfe8f4b7cb5f193cc5496d246159c4cf9a707bf576e3ae-image13.webp" />

Also, you should see the subscribeFromApi(-form name) event with the corresponding contact details in the event history (*Automation → Event history* tab).

<Image align="center" width="80% " src="https://files.readme.io/2dd6da24f399549f3b992b53d6a3dc510aa331ec073bd0aa349e84012af9748e-image6.webp" />

Click *Publish* to activate the Zap.

<Image align="center" width="80% " src="https://files.readme.io/fe8a11e3a89a26365b0e262494622f68fc51f5aa51d3bb6da24a9cbe17d088bf-image2.webp" />

## Other Examples of Integrations with Yespo via Zapier

Below is a list of common examples of integrations with Yespo via Zapier. It is incomplete but is intended to give you ideas based on the specifics of your business.

* **Integration with CRM.** Connect Yespo to your CRM system (such as Salesforce, HubSpot, or Zoho CRM) to automatically add contacts to mailing lists, generate leads, or perform other CRM actions when contacts sign up for a newsletter or interact with your messages.
* **Integration with social networks.** Submit new leads from Facebook, Instagram, etc., to Yespo to increase the number of touchpoints and get more contact information.
* **Integration with analysis and reporting tools.** Transfer data on email openings, clicks, and other events in Yespo to analytical services to create reports and analyze campaign results.
* **Integration with Slack or Microsoft Teams.** Set up alerts on your communication platforms for essential events in your campaigns, such as email openings or unsubscribes.
* **Integration with other marketing automation tools.** Connect Yespo with marketing platforms like HubSpot or Marketo to create complex campaigns.
* **[Integration with survey services](https://docs.yespo.io/docs/how-create-survey).** Transfer the results of questionnaires and surveys to external storage for further processing.
