Plugins/CsvImport
=================


[Plugins](../Plugins.1.html "Plugins")

This page is outdated
---------------------------------------------------------------------------------

The information on this page concerns an old or obsolete version of
Omeka. If you are using a more recent version, instead see [the CSV Import 2.0 page](CSV_Import_2.0.html).

About CSV Import
-------------------------------------------------------------------------

The CSV Import plugin allows users to import items from a simple CSV
(comma-separated values) file, and then map the CSV column data to
multiple elements, files, and/or tags. Each row in the file represents
metadata for a single item.

When using this plugin, you may only import one item type (document,
still image, sound, et al) at a time. You may perform multiple imports.

Download
---------------------------------------------------------

You can download the latest and previous versions of the CSV Import
plugin from the [Omeka Plugin Directory](../../plugins.html#csvimport).

If you are using Omeka.net, go to the [instructions for using the plugin in the Help section of Omeka.net.](http://info.omeka.net/build-a-website/manage-themes-and-plugins/csv-import/)

Features 
---------------------------------------------------------

The plugin also has the following features:

-   Specify URLs in a column and the importer will download and attach a
    file to each created item.
-   Automatically tags items with tags specified in column data.
-   The Undo option lets you delete all the files added in an import.
-   Allows users to view a history of all imports.

Preparing for CSV Import
-----------------------------------------------------------------------------------------

[Watch a screencast on preparing for CSV Import](../../files/movies/CSVImport1_1.0.mov)

The best option is usually to use spreadsheet software like Microsoft
Excel or OpenOffice.org Calc to create and organize your data. Both of
these programs can export a spreadsheet into CSV format, and will handle
all the necessary escaping and quoting for you.

However, if you're creating or editing your data by hand, there's a few
things to keep in mind:

1.  You will need to normalize your data before importing. Check to be
    sure that the first row of your CSV file contains column names, and
    that every row has the same number of columns.
2.  Check to see if any of the text contains commas, and if it does
    surround that segment with double-quotes. Many spreadsheet programs
    will do this for you automatically. If you are using a spreadsheet
    program, check the CSV that is exported by opening it in a plain
    text editor to see if the double-quotes are being
    added automatically.
3.  Remember, every row represents 1 item, and all items in the file
    have the same item type.
4.  Look over the Dublin Core and Item Type metadata to be sure you can
    easily map the fields in your CSV file to the Omeka installation.
    Make any modifications in fields or types as necessary. (See
    [Managing\_Item\_Types](https://omeka.org/codex/Managing_Item_Types "Managing Item Types"))
5.  It is possible to import files housed in a digital repository by
    adding the URL to that specific file in a column representing
    a file. You may import more than one file per item. When formatting
    the CSV file, be sure to create columns for each file (name columns:
    File1, File2, or Image1, Image2, et al)
6.  The CSV Import plugin comes with a sample CSV file. You can refer to
    this file for help in formatting your own.

Importing
-----------------------------------------------------------

[Watch a screencast on installing and mapping a CSV file](../../files/movies/CSVImport2_1.0.mov)

1.  Click the CSV Import tab on the admin interface.
2.  Select a CSV file from your computer, the Item Type of the rows, the
    Collection of the imported items, and other optional
    import settings.
3.  Click the Next button.
4.  Map the columns of the CSV file to item elements, tags,
    and/or files.
5.  Click the Import CSV File button

Note: Uninstalling the plugin will *not* delete imported items, but it
will delete the history of importing those items, along with the ability
to undo those imports.

Undo an Import
---------------------------------------------------------------------

1.  Click on CSV Import administrative tab.
2.  Click Status tab.
3.  Click Undo link for the Import you want to undo. This will delete
    all items for this import.

If your import hangs without completing for an extended period but the
link to undo the import does not appear, you can enter the link directly
into your browser address bar according to the following example:

http://\[PATH TO YOUR OMEKA INSTALLATION\]/admin/csv-import/index/undo-import/id/\[IMPORT ID\]

For example, if your Omeka instance was at the root of example.com and
this was your 3rd CSV import, you would use
*http://example.com/admin/csv-import/index/undo-import/id/3*. You can
hover over the links for previous or subsequent imports to deduce the
Import ID.

Troubleshooting 
-----------------------------------------------------------------------

1.  In version 1.1-1.2, if you get the following error message in the
    CSV plugin interface admin/csv-import:

    Your PHP-CLI path setting is invalid.

    Please change the setting in pathtoyourinstallation/application/config/config.ini

    If you do not know how to do this, please check with your system or server administrator.

you must edit the PHP path in the `application/config/config.ini` file.

Some servers run multiple versions of PHP, so ask your web host or
system administrator to assist if you do not know the correct path.
