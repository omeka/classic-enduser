---
title: Managing Items
---

Items are the Archive
----------------------------------------------------------------
To build a digital archive, you must first add items.

Before Adding Items 
----------------------------------------------------------------

You may want to consult the [Site Planning Tips](../Site_Planning_Tipes.md) page to think about how to build your site and what you want to do with your items.

You may also want to think about what type of information you plan to share using the [Dublin Core Metadata](http://dublincore.org/documents/usageguide/) fields before adding and describing items. You may also want to read the [Describing Items](../Describing_Items.md) page for a brief explanation of using metadata in Omeka Items.

Screencast 
-------------------------------------------------------------

Watch a Screencast on [managing items in your Omeka
site](../files/movies/ManagingItems1.0.mov).

Add an Item 
---------------------------------------------------------------

1.  From your dashboard (mywebsite.org/admin) click "Add new item to
    your archive."
2.  This takes you to the admin/items/add page where you see a     navigation bar on the left pointing you to different sections of adding an item. At any time, you may check the “Public and/or “Featured” boxes at the top of the item form. You may also change this status from the /admin/items page without needing to re-open the individual item.
3.  The first tab shows the Dublin Core metafields. These are available for every item in the archive. Each field can have multiple values; Simply click the "Add Input" link below each field title to add a new input for that field.
4.  The [item type](Item_Types.html "Item Types") section lets you     choose a specific item type for the object you are adding. Once you choose the type, relevant metadata fields appear for you     to complete. (See [Managing Item Types](Managing_Item_Types.html "Managing Item Types") for information about adding/editing item types.) 
5. The Collection section allows you to add this item to a collection. Collections must already exist in the system before you can add an item to the collection. (See [Managing Collections](Managing_Collections.html "Managing Collections") for information about adding/editing collections.)
6.  The Files section lets you upload multiple files to an item. Clicking the "Add Another File" link will reveal another field for adding a file. You can associate any number of files to an item. Read more about [Managing\_Files](Managing_Files.html "Managing Files").
7.  The Tags tab allows you add keyword tags to your item.
8.  A tab called "Additional Item Metadata" will be present if you have installed plugins that use this, or if you have upgraded from Omeka version 0.9. (This tab will hold any legacy metadata from older versions.)
9.  Be sure to click the "Add Item" button to save your data.

### Adding HTML elements to Items

Each metadata field's text may be enhanced using basic HMTL tags. Check the HTML box below the text box to enable a visual HTML editor. For more instructions, see: Using HTML Editor TinyMCE

### Diagram of Items in an Archive
-   Items: Each item contains Dublin Core and Item Type metadata; an item can belong to one collection at a time, and have an infinite number of tags. Items may contain many or no files.
-   Collections: May be comprised of different items. Items may only
    belong to one collection a time.
-   Tags: Tags can be added to any item, and an item may contain an
    infinite number of tags.

[![Archive itemsrelations
wiki.jpg](http://omeka.org/c/images/f/f8/Archive_itemsrelations_wiki.jpg)](File:Archive_itemsrelations_wiki.jpg.html)

Edit an Item 
-----------------------------------------------------------------

1.  Access the Items from the tab in the top navigation bar in your
    /admin interface (/admin/items).
2.  Find the item you want to edit from the list of most recently-added
    items or by searching.
3.  At the far right end of the item listing, click on the "edit" button
    which takes you to the /edit/item/\# page.
4.  You will be presented with the same interface for adding an item.
    Find the appropriate field to edit. Be sure to click the "save
    changes" button. If you do not hit save, your changes will be lost.

Delete an Item 
---------------------------------------------------------------------

You can delete an item by visiting that item's edit page, and clicking
the "Delete this Item" button at the bottom of the form.

Batch Editing & Deleting, Versions 1.4 + 
-------------------------------------------------------------------------------------------------------------------------------

-   Click Items tab from the Dashboard or admin screen (admin/items).
-   Find items that you wish to edit or delete in a batch by browsing,
    sorting, or searching.
-   Use the check boxes to the left of an item's title to select it for
    batch editing, or select the box to the left of the Title heading to
    select all items available on that page.
-   Once items are checked, the Edit Selected Item buttons turns green.
    Click on that button, which will open a lightbox giving you options
    for editing.

[![Batch editscreen1
4.jpg](http://omeka.org/c/images/4/48/Batch_editscreen1_4.jpg)](File:Batch_editscreen1_4.jpg.html)

-   You may make the following changes for each batch of selected items:
    -   Make public or un-public,
    -   Feature or un-feature,
    -   Change Item Type,
    -   Switch or associate selected items with a Collection,
    -   Add Tags to all selected items,
    -   Delete Items,
    -   Include Item Relations, if the [Item
        Relations](http://omeka.org/codex/Plugins/ItemRelations "Plugins/ItemRelations")
        plugin is installed.

Check the list of items to be edited or deleted in the box to the right.
Un-check box to the left of items if you marked one by mistake.

Browse Items (in Admin)
-------------------------------------------------------------------------------------------

Clicking on the Items tab from the Dashboard or /admin page takes you to
a list of items listed by default in order of most-recently-added.

Clicking on Detailed View, shows image thumbnails plus additional
metadata, including Collection name if the item belongs to a collection.

### Version 1.3 +

Sort the browsing results by clicking on the heading for each column
including: ID, Title, Creator, Date Added, Public, or Featured.

###Versions 1.4 + 

Sort the browsing results by clicking on the heading for each column
including: Title, Creator, Public, Featured, or Date Added.

Clicking Show Details button shows image thumbnails, together with the
item's Title, Collection Name, any tags, and whether item is public or
featured. Also, available are quick links for editing or deleting the
item.

Output Formats 
---------------------------------------------------------------------

Once you have items in an archive, item data may be shared in a variety
of [Output\_Formats](Output_Formats.html "Output Formats").
