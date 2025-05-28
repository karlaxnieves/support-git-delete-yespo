---
title: Managing Data Collected via AMP Forms
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: How to Manage Data Collected via AMP Forms | Yespo Guide
  description: >-
    For emails with AMP forms, you can receive and store users’ feedback with
    the built-in data service in Stripo.email. It collects information in its
    internal storage and transfers it to external storages via Zapier.
  robots: index
next:
  description: ''
---
When you create emails with AMP forms in our platform, you can receive and store users’ responses using the built-in data service in Stripo.email. A data service collects information in the internal storage of Stripo.email and transfers it to external storages via Zapier.

[Guidelines on creating an AMP form](https://docs.yespo.io/docs/how-create-amp-form)

## How to Create a Data Service in Stripo.email

Stripo.email allows free storage of responses from AMP forms.

1. Create an account in <a rel="nofollow" href="https://stripo.email/" target="_blank"> Stripo</a> and log in.
2. In the toolbar on the left, click *Data → Create your service*.

<Image align="center" width="80% " src="https://files.readme.io/6f9dd26b36208e92fed340b026221c71da2fd379d77adfe4f1c98a84ebcab250-image4.webp" />

3. Enter the service name and description. Other fields will be filled automatically. Leave *Stripo storage* enabled. If you plan to use external platforms for data storage via Zapier, enable *External storage resources*.
4. Copy the generated URL address.

<Image align="center" width="80% " src="https://files.readme.io/4cb03892ac4e837daeaa29b3ceb6525c04b0f8bc97abff95920f04d879ece99f-service-configuration.webp" />

5. Go to your account in our service and open the corresponding email with the AMP form. Click *ϟHTML* to open the settings. Insert the copied URL in *Service for data collection*.

<Image align="center" width="80% " src="https://files.readme.io/157436f840e64074303543c9a75447177eab2e3bccd825e13059ad30d0d38b18-managing-data-collected-via-amp-forms-001.webp" />

The data service is created.

All data provided by recipients will be stored in your Stripo account and can be downloaded as a CSV file.

<Image align="center" width="80% " src="https://files.readme.io/42ddc741030733a8fadba835cd552fae8b3973cc1525fe1b87b85aa52c0194d8-image16.webp" />

## How to Transfer Data to External Platforms via Zapier

You can transfer data from AMP forms to external storages such as Google Sheets. To do this, you need to set up a connection between your Google account and Stripo via Zapier.

You'll have to pay Zapier for the data transfer if monthly tasks exceed 100 (1 task equals data transfer to one line of the sheet).

<Image align="center" width="80% " src="https://files.readme.io/f1d6d115cf91c679e2505f65b75dbfa491dc2842ac088de7a68a5f347ba18bc3-image19.webp" />

1. In your Stripo account → *Data → Data storage*, disable *Stripo storage*.
2. Enable *External storage resources*.
3. Add the webhook URL. See below how to get it.

<Image align="center" width="80% " src="https://files.readme.io/478bc20e81863187075b554ae8d73db72a705be487b1b8670b6c27da79d0c0d1-external-storage-resources.webp" />

### How to Get a Webhook URL

1. Create an account in Zapier or log in.
2. Click *MAKE A ZAP*.
3. Enter zap’s name.
4. In *Built-In Apps*, select *Webhooks by Zapier*.

<Image align="center" width="80% " src="https://files.readme.io/f705926de0915bf9f174c289d523381694d63754c396b7b6b03021500e1f46b8-image13.webp" />

5\. In *Choose an Event*, select *Catch hook* and click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/3a739b883c246f9e97e56f9e67b469efe3f482c79c9b42f603aa149d15c417a0-image18.webp" />

6\. Copy the generated URL.

<Image align="center" width="80% " src="https://files.readme.io/9c0fca3f9bd0a7871f11c41b12dd227095af4fd31315e20a087e3dba06d3bcd3-image5.webp" />

7. Insert it to *Webhook URL* in your Stripo account.

<Image align="center" width="80% " src="https://files.readme.io/f096065d0e2ccffdbd35a1286392288cdfca6f2c2003927fb1d97a4d23412ff2-data-stor.webp" />

8. Copy the URL address.

<Image align="center" width="80% " src="https://files.readme.io/f0fe0014005f3edfcd1ab9ee278445f843a99dfc73328ba398103633ccb7ce57-copy-url.webp" />

9. Go to your account in our system and open the corresponding email with the AMP form. Click *ϟHTML* to open the settings. Insert the copied URL in *Service for data collection*.

<Image align="center" width="80% " src="https://files.readme.io/5ff9e4bcab3416472362b26df988bd4d649590ccdfe24ffee93e0fb5133ceb6b-managing-data-collected-via-amp-forms-001.webp" />

9. Go back to Zapier → *Customize Request* and click *Continue*. Click *Test trigger → Skip test* and click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/b2f3e623bbc8ea9ea762e21575ece7a22e42cb3543ba84191b394df6baf2c596-image14.webp" />

10. In *Your Apps*, choose *Google Sheets*.

<Image align="center" width="80% " src="https://files.readme.io/d07f8fc34b20cc18d2f630d5fb81aad0d0f348ea0b493fca0058321ea41fefca-image7.webp" />

11. Choose *Create Spreadsheet Row* and click *Continue*.

<Image align="center" width="80% " src="https://files.readme.io/17dbe1158dd4f538010133a953b8744f97bef683066e766a4b32451bbff74db8-image8.webp" />

12. Click Sign in to *Google Sheets* and allow Zapier access to your account.
13. Create a Google Spreadsheet where the corresponding data will be exported: name, email address, answer, etc.

<Image align="center" width="80% " src="https://files.readme.io/6e5e7a74d1769376af77602ab0678e33d9300130fe5c6df866dda0e536417fbe-image17.webp" />

14. In Drive, select *My Google Drive*, and choose the necessary spreadsheet and worksheet. Click *Continue*. Zapier will extract field names from the worksheet.

<Image align="center" width="80% " src="https://files.readme.io/4eea08d5cf4d3525a00eb87c332f034c924372a18727f65e223945587ca38d75-image12.webp" />

15. Test the connection: the data from the form should be transferred to the corresponding columns of the table.
16. If everything works fine, click *TURN ON ZAP*.

> 📘 Important
>
> If you want to transfer data to both Stripo and external storage, enable both toggles. Add a link to the Stripo data service in the template in our platform. The answers will be sent to the internal Stripo store and to Google Sheets via Zapier.

<Image align="center" width="80% " src="https://files.readme.io/c191dd9774759813031e1469e3097e22b0bc4f5c336a3fb8e9199620a3101973-image15.webp" />
