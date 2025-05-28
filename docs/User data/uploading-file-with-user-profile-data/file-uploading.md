---
title: File Uploading
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: File Uploading | Yespo Guide
  description: Learn details on uploading your contact list to Yespo
  robots: index
next:
  description: ''
---
Upload information about your customers or subscribers and use this data for targeting and segmentation.

## File Uploading

1. [Prepare a contact list](https://docs.yespo.io/docs/files-preparation) in one of the following formats: XLS, XLSX, CSV, or TXT. The file must include phone numbers or emails — identifier fields by which the system recognizes unique contacts.
2. Go to the *Contacts → Import* tab and click *Upload file*.

<Image align="center" width="80% " src="https://files.readme.io/2597bfd4fc9182beb9b9ef730320329e4cf2bbffadcf8b97c083f1ad16296ed5-image11.webp" />

3. Drag the file to the upload area or click on it to upload the contact information file.

<Image align="center" width="80% " src="https://files.readme.io/ca157be1a7bbcf6b28c4277b3f18d2b1a6cf617d10b450a905515c7696bebefb-image6.webp" />

You will move on to contact field mapping after downloading the file.

## Mapping Contact Fields

1. Select the field by which the uniqueness of contacts will be established. When importing, a contact will be searched for in this field. If the contact is found in the Yespo database, it will be updated according to the uploaded file. It will be created if the contact is not found

([more about contact IDs and field matching](https://docs.yespo.io/docs/customer-identifiers-and-matching)).

<Image align="center" width="80% " src="https://files.readme.io/af709d12aa61575ce0ef2c2cfba7818b646adef41562ae303e3c18639939785e-image12.webp" />

> 📘 Import
>
> We recommend setting the uniqueness of contacts using an external ID, which allows you to avoid duplicating contact profiles, collect all available data into a single profile, and obtain complete information about the contact’s interaction with your company. [More details >](https://docs.yespo.io/docs/external-id-creating-and-updating-users)
>
> When you assign the External ID value to a column in an imported file, the *Unique contact field by…*  line is automatically set to the External ID and cannot be changed.
>
> If the imported file column assigned as External ID contains empty values, the Yespo system runs a check and reports the number of errors before and after importing the file.

2. Select whether to import empty values. If this option is enabled, filled contact fields will be replaced by empty values from the file when updated as a result of import.

<Image align="center" width="80% " src="https://files.readme.io/04235e35e36c365a85adf6f33b36a1d5f8a298ed1cef9b7cc8824112c454304e-image1.webp" />

3. Select whether to ignore the first line in the file: turn off the option if the contact information begins with the first line or enable it if the information in the file starts with a technical line with column names.

<Image align="center" width="80% " src="https://files.readme.io/99468b11204f05d224cd20615ecc5b0ece83c2e5c4b96b26c0054fc1b967be0a-image9.webp" />

4. Set the correspondence between the fields from the file and [additional fields](https://docs.yespo.io/docs/how-add-additional-contact-fields) in the contact card in Yespo. If you don't need information from a column, set it to *Ignore*.

<Image align="center" width="80% " src="https://files.readme.io/491f8f4089e92fb6f45d0a782dcae3b29322387b755af985bb05840a92e903c7-image3.webp" />

### Data Checking

The value will have a red or orange marker if it does not match the field format.

* Errors in the field identifying the contact (email or SMS) are highlighted in red.
* Warnings about inconsistencies in all other fields are highlighted in orange. 

Contacts with errors are not saved or updated in the system, and fields with warnings are not updated.

The first 100 contacts from the file are available for viewing in the download window. The system automatically calculates the number of errors and warnings in the first hundred. This is done to ensure that the data in the import file is valid and can be loaded correctly into the selected fields.

You can manually correct errors in the preview window (the *Start the search of errors* button) or immediately proceed to the next import stage (the *Next* button).

<Image align="center" width="80% " src="https://files.readme.io/1aa8dc807e7e3120212346b54ffabe0fceafa616fe9f2250bbac1d590fd01b86-image5.webp" />

## Import Parameters

1. Determine which segments your contacts should fall into after import. This can be a new list segment or existing list segments. For a new segment, you can [add tags](https://docs.yespo.io/docs/how-add-tags) to help with filtering and set a name instead of the automatically generated one.

<Image align="center" width="80% " src="https://files.readme.io/b59263874dfbb08d3a7b2eeaac69d1859935817426b0d1b8a69831036b37e630-image10.webp" />

2. If you want to launch a workflow after import, activate the appropriate option. [More on launching a workflow after import >](https://docs.yespo.io/docs/how-to-launch-workflow-upon-import)

<br />

<Image align="center" width="80% " src="https://files.readme.io/499d1b19a023879a001a0933676c3bd620f8a053af8023bf4abc39961254727d-image2.webp" />

3. By importing contacts, you can restore and update the contacts contained in the file. To do this, make the corresponding switcher active.

<Image align="center" width="80% " src="https://files.readme.io/0eb8207a2ae1b41ade8443eb06e0f256d63e17b0554ef5f19d7d63d014876dee-image4.webp" />

4. Confirm that you know the terms and conditions of system use and import.

<Image align="center" width="80% " src="https://files.readme.io/0ef102221dfdc6b853498c61e694eb0f2874d3aacccd1c2a85fe40c837efe527-image7.webp" />

5. Click *Start Import*.

Once completed, the import will appear in the history, where you can see the segments into which the contacts were imported, the user who imported the file, and details regarding the imported contacts (number of new, updated, duplicates, etc.)

<Image align="center" width="80% " src="https://files.readme.io/3fb20250f5d759841417457070346249b7986a056e4102d08217e5b92f900765-image8.webp" />
