---
title: File Preparation
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: File Preparation | Yespo Guide
  description: Learn the details on formatting the file with contact data
  robots: index
next:
  description: ''
---
Before [importing the contact base](https://docs.yespo.io/docs/file-uploading), look at the main principles of file preparation.

1. Validate your base to verify the contact list and delete non-valid and fake contacts.
2. Available email and/or phone number are a must for import: the system uses them to recognize unique contacts. A file with names and addresses only will not be downloaded.
3. Prepare a file with contacts in one of the supported formats.

* **XLS** - table with columns created in Excel version 97/2000/XP. Standard format for tables.

<Image align="center" width="80% " src="https://files.readme.io/856968e0c2522c67870404ae5ae9c7e6505307db29fb84262b4429939cec31a6-68ba3b0-image3.webp" />

* **XLSX** - table with columns created in Excel 2003. Standard format for tables.
* **CSV** - text file with comma-separated values. Can be created in Notepad or in Excel.

<Image align="center" width="80% " src="https://files.readme.io/fbbe89a71b265476eedcdba08be8cb2547054fc3bfc481cc346db0cd69f4bd29-60a9853-image1.webp" />

* **TXT** - standard format for Notepad text files. The file structure should be similar to CSV files.

<Image align="center" width="80% " src="https://files.readme.io/19995e96ff8715eabf4423d10a60da9985fba3488ecefec0dd32f0ec6c4b677b-e55a103-image4.webp" />

4. It should be saved in one worksheet. If the file contains two or more worksheets, the system will not process them: only the contacts from the first worksheet will be imported.
5. Text fields of the list should have no spelling mistakes (gmeil.com, gmai.com, etc.). Fields with errors will not be imported into the system. See more detailed requirements for contact fields.
6. Phone number fields should be saved in the international format.
7. Your contact list file size shouldn’t exceed 300 MB. If it’s over 300 MB, split the file into several parts by removing the unused columns.

You can download file examples from the Yespo system to see how every format should be organized.

<Image align="center" width="80% " src="https://files.readme.io/c257d0c22c7d691ecac2903776d72f54a954ccb4f91bc925e1589a1fac67a0d5-import-example-en.webp" />
