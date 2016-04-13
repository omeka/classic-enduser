Plugins/CSV Import 2.0
======================


[Plugins](../Plugins.1.html "Plugins")

About CSV Import 
-------------------------------------------------------------------------

The CSV Import plugin allows users to import items from a simple CSV
(comma-separated values) file, and then map the CSV column data to
multiple elements, files, and/or tags. Each row in the file represents
metadata for a single item.

When using this plugin, if you plan to map to specific Item Type
metadata fields, then you may only import one item type (document, still
image, sound, et al) at a time. You may perform multiple imports.

The plugin has the following features:

-   File importing: If you specify permanent file URLs in a column, the
    importer will download and attach a file to each created item. NB:
    file import only works for files hosted online; you cannot import
    files from a local source (ie, your computer)
-   Tag imports: You may include tags in your CSV file and those words
    will be imported as tags.
-   Undo Imports: The Undo option lets you delete all the files added in
    an import.
-   Set custom delimiters: you now have the option to set separate
    delimiters for columns, files, tags, and elements.

Preparing for CSV Import 
-----------------------------------------------------------------------------------------

The best option is usually to use spreadsheet software like Microsoft
Excel or OpenOffice.org Calc to create and organize your data. Both of
these programs can export a spreadsheet into CSV format, and will handle
all the necessary escaping and quoting for you.

However, if you're creating or editing your data by hand, there are a
few things to keep in mind:

-   You will need to normalize your data before importing. Check to be
    sure that the first row of your CSV file contains column names, and
    that every row has the same number of columns.
-   Check to see if any of the text contains commas, and if it does
    surround that segment with double-quotes. Many spreadsheet programs
    will do this for you automatically. If you are using a spreadsheet
    program, check the CSV that is exported by opening it in a plain
    text editor to see if the double-quotes are being
    added automatically.
-   You can specify a unique delimiter for columns, files, tags,
    and elements. Once you do, be sure to be consistent in formatting.
-   Remember, every row represents one item, and all items in the file
    must be the same item type.
-   Look over the Dublin Core and Item Type metadata to be sure you can
    easily map the fields in your CSV file to the Omeka installation.
    Make any modifications in fields or types as necessary. (See
    [Managing\_Item\_Types\_2.0](../Managing_Item_Types_2.0.html "Managing Item Types 2.0"))
-   It is possible to import files housed in a digital repository by
    adding the URL to that specific file in a column representing
    a file. You may import more than one file per item, by comma
    separating the urls within a cell. You must use a permanent link for
    this step.

Installing 
-------------------------------------------------------------

Download and unzip the CSV plugin. See
[Managing\_Plugins\_2.0](../Managing_Plugins_2.0.html "Managing Plugins 2.0")
for additional instructions.

If you are using Omeka.net, go to the instructions for using the plugin
in the [Help section of Omeka.net](http://info.omeka.net/build-a-website/manage-themes-and-plugins/csv-import/).

Importing 
-----------------------------------------------------------

A quick note about CSV formats and importing: The column delimiter is
the basic building block of the CSV file, and it is a comma by default.

Each of the remaining delimiter inputs simply accepts a character that's
used to separate multiple values within one "cell" of the CSV.

If you are placing multiple values in single cells, the character you're
using to separate those values is the delimiter. The plugin allows you
to specify different delimiters for cells that contain tags, links to
files, or normal element data.

-   To import, go to the CSV Import tab in the left navigation bar in
    the admin Dashboard.
-   Select a CSV file from your computer and select the appropriate
    import settings. You may choose an item type for each of your items
    to be designated, and you may place your items in a collection using
    the pull-down menus.
-   At this time you may also make your items public or featured if
    you wish.
-   You must tell the plugin how to deal with your data. If your CSV
    file does not use a comma to separate your columns, indicate which
    character you did use. Note: You may not use a tab or an
    empty space.
-   The plugin assumes you have used commas to separate tags within
    individual cells in your CSV file. If you have used a different
    character, you must indicate that in the Choose Tag Delimiter field.
    Note: You may not use a tab or an empty space.
-   The plugin also assumes that you have used commas to separate
    multiple URLs within a cell (if you are importing items from an
    outside repository, for example). If you have used a different
    character, indicate that in the Choose File Delimiter field. Note:
    You may not use a tab or an empty space.
-   The plugin assumes that each metadata field has only one element
    in it. If any of your metadata fields has more than one element (if
    your item has more than one creator, for example), please tell the
    plugin what character you used to separate the elements. If you have
    more than one element in a a field but leave this blank, the plugin
    will treat the entire text block as one element. Note: You may not
    use a tab or an empty space.

Note: If you are importing a CSV file that was exported by Omeka, you
may simply select "Use an export from Omeka CSV Report" and your
metadata will be directed to the proper fields for you.

[![CSV1.png](https://omeka.org/c/images/8/89/CSV1.png)](../File:CSV1.png.html)

[![CSV2.png](https://omeka.org/c/images/4/40/CSV2.png)](../File:CSV2.png.html)

-   Click the Next button.
-   On the next screen, you will see a table which includes each of the
    Dublin Core fields in Omeka, the text from your CSV file that is
    designated for that field, and a pull-down menu to allow you to map
    your columns to the appropriate field. Make sure you select an
    element for each of the fields that is populated.

[![CSV3.png](https://omeka.org/c/images/8/84/CSV3.png)](../File:CSV3.png.html)

-   Click the Import CSV File button.
-   You may check on the progress of your import using the Status tab.

Undo an Import
---------------------------------------------------------------------

-   Click on the CSV Import administrative tab.
-   Click the Status tab.
-   Click the Undo link for the Import you want to undo. This will
    delete all items for this import.

[![CSVUndo.png](https://omeka.org/c/images/a/a2/CSVUndo.png)](../File:CSVUndo.png.html)

If your import hangs without completing for an extended period but the
link to undo the import does not appear, you can enter the link directly
into your browser address bar according to the following example:

http://\[PATH TO YOUR OMEKA INSTALLATION\]/admin/csv-import/index/undo-import/id/\[IMPORT ID\]

For example, if your Omeka instance was at the root of example.com and
this was your 3rd CSV import, you would use
<http://example.com/admin/csv-import/index/undo-import/id/3>. You can
hover over the links for previous or subsequent imports to deduce the
Import ID.