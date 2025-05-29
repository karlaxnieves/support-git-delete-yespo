---
title: Opening a CSV File After Export
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: Opening a CSV File After Export | Yespo Guide
  description: >-
    Learn how to set up correct displaying of the contact data in the imported
    from Yespo file
  robots: index
next:
  description: ''
---
Yespo provides the following options for exporting contacts to a `CSV` file:

* From the general contact list
* From the segment list
* From reports

## Export from General Contact List

1. Go to the **Contacts → All Contacts** tab and select a contact category from the left menu. By default, all categories are selected.

Any categories are available for export except duplicates.

<Image align="center" width="80% " src="https://files.readme.io/38d13ca2ba63a71c065670ed26576c3ad898cf89b1a86d9bfae648ec402c93c4-opening-csv_1.png" />

2. Click the **Export** button and select **To CSV** from the drop-down menu.

<Image align="center" width="80% " src="https://files.readme.io/3fe523c226bb45af13363e88946a7d01c50de36e2eff9ff94ada35128bf7aaf7-opening-csv_2.png" />

## Export from Segment List

1. Go to the **Contacts → Segments** tab.

2. Select a segment, click the three dots next to it, and select the **To CSV** export option.

<Image align="center" width="80% " src="https://files.readme.io/bee6bdfbbf8b6adb4a67c1aba23b40ca6282cf2bc6b61aa2bdc5ce6754554693-opening-csv_4.png" />

> 📘 Important
>
> Only users with export rights can upload contacts. After clicking the **To CSV** button, you will receive an email with a link to download the file at the email address you used to log in to your account. The file will be available for download within 3 days.

## Export from Reports

Exporting contacts from reports is described [in the manual](https://docs.yespo.io/docs/exporting-subscriber-groups-reports).

After you have exported contacts using one of the options listed above, you can proceed to work with the file.

## Working with a CSV File

A file with comma-separated values contains text information, and the delimiter can be either a comma or a semicolon (depending on the language version of the system that generated the `CSV` file).

For the data in the file to be displayed correctly, you may need to

* Specify the appropriate encoding and delimiter character;
* Split the text into columns.

### Specifying Encoding

When opening a `CSV` file in Excel, the encoding and delimiters may not match, and you may see a set of unreadable characters or text that is not divided into columns.

<Image align="center" width="80% " src="https://files.readme.io/513b09111e5c5980438e0a109ad3f14c02dd4f1ebe44017656b0aba01fdb03aa-opening-csv_5.png" />

In this case, take the following steps:

1. Open Excel and create a blank sheet.

2. Go to the **Data → Get & Transform Data** tab, and select **From Text/CSV**.

<Image align="center" width="80% " src="https://files.readme.io/c8bbe2e40bd328852ac4bfa73b42e056691dbbd72efb7ebf11be083b67143e9b-opening-csv_6.png" />

3. In the **Import Data** window, navigate to the exported file's location, select it, and click the **Import** button.

<Image align="center" width="80% " src="https://files.readme.io/994b76415b4e6cef25ff748fe79a4c224c8d924f9c644726a68fbce9d942eda8-opening-csv_7.png" />

4. Next, specify:

* **File Origin:** **Unicode (UTF-8)** or **Cyrillic (DOS)** are the most popular options and are most often suitable for working with files. Refer to the preview to check which encoding is suitable.
* **Delimiter:** Semicolon or another delimiter, depending on the result in the preview area (you can also specify a custom character).

Other parameters usually do not need to be adjusted.

When finished, click **Load**.

<Image align="center" width="80% " src="https://files.readme.io/7070d81adedc5ea0048a43e8172edece6c95abff88e0ef656a3811819b37b745-opening-csv_8.png" />

The result of choosing the appropriate encoding and delimiter is a correctly displayed `CSV` file in Excel:

<Image align="center" width="80% " src="https://files.readme.io/a2b481ae56f301151711f878d4dbb4f52915a0a9c60db437c957e3eb329f82e1-opening-csv_9.png" />

> 📘 Note
>
> By default, when you open a `CSV` file through Libre Office, it prompts you to select the encoding and delimiter: follow the instructions above.

### Splitting Text into Columns

You may need to split text into columns, for example, to divide first and last names.

1. Add the empty column to the right of the column with first and last names.

<Image align="center" width="80% " src="https://files.readme.io/7ad28efddafa21b60d6bc62a86ff34ef60625acef5f81b3623e3c8246caf2127-opening-csv_10.png" />

2. Highlight the column with first and last names and click the **Text to Columns** button.

<Image align="center" width="80% " src="https://files.readme.io/0acd6253d2c336dcba3e750c55df230d1d7cc95aa599e702110abc0fd588e8e1-opening-csv_11.png" />

3. Specify the **Delimited** format and click the **Next** button.

<Image align="center" width="80% " src="https://files.readme.io/dafab501f6edf2a9488717584e0a713c398c99d37d339526fa754f0a2faf4316-opening-csv_12.png" />

4. Select the **Space** delimiter. Check how the data is split in the preview area. If necessary, you can specify another delimiter.

If everything is correct in the preview, click **Next**.

<Image align="center" width="80% " src="https://files.readme.io/794555c91b76a6e8877377ffc1669c22d0e8b933b7494f2ff35e947c253b7614-opening-csv_13.png" />

5. In the last step, you can change the column format by selecting the one you want in the preview.

Click **Finish**.

<Image align="center" width="80% " src="https://files.readme.io/fba70be0db80516e2517483f9fdc86a3a01dea4e9e82f7b471cfb35867056f46-opening-csv_14.png" />

Confirm replacing data.

<Image align="center" width="80% " src="https://files.readme.io/87b263a779fa3648feb803183fa51d3cd7b5e51a679607786bff924bd8a19577-opening-csv_15.png" />

The result is a table with first and last names separated by columns.

<Image align="center" width="80% " src="https://files.readme.io/b666744de9c87dc710136df5daaa2844ef23c924dfcdb85e7f24b5609407eb55-opening-csv_16.png" />