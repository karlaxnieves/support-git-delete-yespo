---
title: Launching a Workflow After a Contact Import
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Launching a Workflow after a Contact Import | Yespo Guide
  description: >-
    Your website is not integrated with our system and contacts are added
    manually using import? Or you don’t have a website, but there is a database
    of contacts, and you need to launch notifications? Launch a workflow after
    importing contacts into the system.
  robots: index
next:
  description: ''
---
Use this feature if:

* your website is not integrated with our system, and contacts are added via [import](https://docs.yespo.io/docs/file-uploading);
* you don't have a website subscription form, but you have a contact list and want to launch messages for these contacts.

## 1\. Creating a Workflow

1. Go to *Automation → Workflows* and click *New workflow*.

<Image align="center" width="80% " src="https://files.readme.io/2da06f2deb4e16e000f85ff5dc2cefe4665e072f2db2e3c4869c0c9aebd776ae-launching-a-workflow-after-a-contact-import-001.webp" />

2. Enter the workflow title and [tags](https://docs.yespo.io/docs/how-add-tags) (optional). Build a chain of actions and add the following blocks:
   * *Start* (will be added automatically);
   * *Email to Segment* (select the message and skip the *Segment* field);
   * *End*.

<Image align="center" width="80% " src="https://files.readme.io/bfe46df0411b5a35ea228c10ea83192811b403fb2a754096d47e8c4da9dfe66b-launching-a-workflow-after-a-contact-import-008.webp" />

3. Save the workflow.
4. Go to *Start/Stop configuration*

<Image align="center" width="80% " src="https://files.readme.io/6692c505c8f7b0e73d0c72724df1dfd3fec1d0c5f904b396e07edc30e4d3cba5-launching-a-workflow-after-a-contact-import-201.webp" />

5. In *Start configuration*, select *Event-based* and select the event *Imported new contacts* in *Event*. Set up processing unique events each time. Click *Apply*.

<Image align="center" width="80% " src="https://files.readme.io/4e91f58cec5dd3579b74e0d6000fa672d401275a091f1a8cd6e0f1bd04424ad6-launching-a-workflow-after-a-contact-import-003.webp" />

6. Click the *Activate* icon and start the workflow.

<Image align="center" width="80% " src="https://files.readme.io/c30b896b9367a1f20fb25a4a70fe2a7b054ffa5522fb230b4cc719fd7b4adf7e-launching-a-workflow-after-a-contact-import-202.webp" />

## 2\. Contact Import

To start an import:

1. Go to *Contacts* → *Import* and click on *Upload File.*

<Image align="center" width="80% " src="https://files.readme.io/bea4bd7d283e644c36e6608f8462538d1e0b68292233dc07da225a8b846b1135-launching-a-workflow-after-a-contact-import-005.webp" />

2. Download the file, map contact fields,
3. Enable *Launch a workflow after the import* switcher in the Parameters, and select the event type from the dropdown menu.

<Image align="center" width="80% " src="https://files.readme.io/be8547262cda8b16625cd7db6d517bc8ff59af3874e0c6bf2fa61f84283d287d-launching-a-workflow-after-a-contact-import-006.webp" />

The workflow will be launched after the import is finished.

## FAQ

**1\. Why my workflow doesn’t start?**

The workflow launch may fail if:

* Contacts from the imported file already exist in the system;
* Contacts have been deleted or restored from the previously deleted contacts;
* The workflow uses the *Email* block instead of the *Email to Segment* block;
* The message isn’t selected in the block settings.

To test the created workflow, import a test contact list including several contacts. Once you've made sure everything works correctly, download the main contact list. At the end of the import, the campaign will automatically appear in *Campaigns → Scheduled Campaigns*.

<Image align="center" width="80% " src="https://files.readme.io/0fc60c2bbc0a209e710496758fb72ef2fee6f277a8fb0bf86ad4d0269879ac9b-launching-a-workflow-after-a-contact-import-007.webp" />

Once a moderator approves it, the emails will be sent.

**2\. Can I use other messages (SMS, push notifications) in my workflow?**\
Yes, you can. The procedure is the same as for email. Create the necessary message templates, insert the corresponding blocks ([Message to Segment](https://docs.yespo.io/docs/message-to-segment-blocks)) and select the created message from the dropdown menu in the block settings.
