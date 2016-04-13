Plugins/ItemOrder
=================

[Plugins](../Plugins.1.html "Plugins")


Item Order allows users to order items for public display on the
Collection browse pages.

Order Items in a Collection 
-----------------------------------------------------------------------------------------------

-   Follow instruction for [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin").
-   Click the Collections tab in /admin
-   Find the collection you wish to order and click on the name of the
    collection (*note: do not edit the collection*).
-   On this admin/collections/show/, scroll to the bottom of the page
    where you will find the heading Item Order. Click the link to Order
    Items in this Collection.
-   A complete list of all items in that specific collection will appear
    on the page. Drag and drop the items in the preferred order.
    -   Dragging automatically reorders the items for the public
        collection browse page. The URL of the page will look like this:
        yoursite.org/items/browse?collection=1 (where 1 equals the
        number of the collection you modified).

Restore Original Order
-------------------------------------------------------------------------------------

-   Click the Collections tab in /admin
-   Find the collection you wish to order and click on the name of the
    collection (*note: do not edit the collection*).
-   Scroll to the bottom of the page where you will find the heading
    Item Order.
-   Click "Reset Items to their Default Order."

Note on Upgrading from version 1.0
-------------------------------------------------------------------------------------------------------------

**We highly recommend that you upgrade from 1.0.** That version if
broken and is not supported.

There's a possibility that upgrading from version 1.0 to any other
version will corrupt your item order. This is due to a bug in 1.0 that
could not be corrected by subsequent versions.

When you upgrade from 1.0 and find that your items are incorrectly
ordered and cannot be reordered as normal, you must uninstall and
re-install the plugin. Unfortunately, you will lose all ordering data
and will have to reorder from scratch. We apologize for this
inconvenience.
