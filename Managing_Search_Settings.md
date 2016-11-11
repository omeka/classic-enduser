---
title: Managing Search Settings
---

Settings
---------------------------------------------------------

Settings section dedicated to search functionality. It is important to note that the site-wide search encompasses all record types in Omeka (items, files, collections, as well as Simple Pages and Exhibit content), but can also be can be constrained to particular types.

### Select Record Types

As an Omeka site Super administrator, you may choose which Omeka record types you wish to be searchable: items, collections, files. 

![Search settings page, with Item, File, and Collection checkboxes active](/doc_files/searchSettings.png)

Using the checkboxes found to the left of each record type, choose which ones you want discoverable by the site-wide search. 

The basic options are: Item
- Item
- File
- Collection

Additionally, if you installed the Simple Pages and Exhibit Builder plugins you may make that content available as well. Other plugins may make their content available for searching as well.

Please note that the "Exhibit" record type includes exhibit descriptive information, and an "Exhibit Page" is the actual content of the exhibit.

Be sure to save changes if you check or uncheck boxes. 

Once records types are selected, searchers use the ellipses button to choose from the options you have provided, in both admin and public site-wide searches.

![Expanded search options](/doc_files/searchExpanded.png)

### Indexing 

Indexing means to collect, parse, and store data to facilitate fast and accurate searches. Omeka will automatically index individual records as they are created and saved. Re-indexing is necessary when updating from an earlier version of Omeka or after you customize which records will be searchable.

Click on the "Index Records" button to re-index your records.

Troubleshooting
---------------------------------------------------
If you are having trouble finding by search words you know are in your install, the following may be part of the problem:

-   MySQL by default does not index any words shorter than 4 letters long.
-   Exact match searches will look for the exact string given by the user, anywhere in the record. For example a search for 'poe' would also return 'poem'.
-   MySQL considers terms that appear in over 50% of indexed items to be so common that it excludes them from keyword searches. The easy way to tell if a term meets the the 50% threshold that's at fault is to choose the "boolean" search, as MySQL does not apply the 50% limitation to boolean searches

