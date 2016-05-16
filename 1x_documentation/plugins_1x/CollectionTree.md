Plugins/CollectionTree
======================

[Plugins](../Plugins.1.html "Plugins")


Collection Tree plugin allows Omeka sites to have nested collections.
One collection can have at most one parent collection and one collection
can have zero OR more child collections.

Version Requirements
---------------------------------------------------------------------------------

1.5 and above

Installation
-----------------------------------------------------------------

1.  Upload and install the Collection Tree plugin (see
    [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin"))
2.  Once activated, the plugin automatically creates a tab in the Admin
    navigation called Collection Tree where you may view relationship
    between collections. To create those relationships, first start in
    the Collections tab (admin/collections).

Nesting Collections
-------------------------------------------------------------------------------

As with all Omeka Collections, first create a collection and then you
can create the nested relationships.

-   Start by creating the main or "parent" collection following the same
    procedures as you would for creating any collection, see
    [Managing\_Collections](https://omeka.org/codex/Managing_Collections "Managing Collections").
-   At the bottom of the Add Collection page, you will find a heading,
    **Parent Collection**. In that section, you will determine the main
    or parent collection of the one you are currently adding. Here we
    are creating the parent, called "Cars," and so we will not choose
    a collection.
-   To nest sub-collections, we create new collections as we did above,
    (named "Cadillac," "Hudson," Oldsmobile") and then in the **Parent
    Collection** section, select "Cars" as the parent for each.
    -   Now, Cars is the parent, or main collection, and Cadillac,
        Hudson, Oldsmobile are child or sub-collections.
-   To view the hierarchy of all collections in your Omeka site, click
    on the Collection Tree tab (/admin/collection-tree) to see
    these relationships.
-   This process also works when editing existing collections. You may
    return to collections created before adding the Collection Tree
    plugin and create parent-child relationships.
    -   *Please note that one collection can have at most one parent
        collection and one collection can have zero OR more
        child collections.*

Adding Items to Collections
-----------------------------------------------------------------------------------------------

-   When Adding or Editing an Item, go to the Collection tab to choose a
    collection from the dropdown menu.
-   As a reminder of the current relationships of parent and child
    collections, the collection tree displays in this screen.
-   You may choose to associate the item with a child or a parent
    collection, depending on how you wish to organize your items.
    -   Your still image of a Phaeton probably will be organized into
        the Cadillac collection, which we know is already a
        sub-collection of Cars.

Public Display of Collections and Relationships
---------------------------------------------------------------------------------------------------------------------------------------

-   Only parent collections appear by default on the public /collections
    browse pages.
-   Clicking on a parent collection brings you its collections/show
    page, with a section called Collection Relations. Child collections
    are listed below that heading, with a link to each. The parent Cars
    would list Cadillac, Hudson, Oldsmobile and link to the
    collections/show page for each of those child/sub-collections.
-   Child/sub-collection show pages contain a link back to its parent.
-   On public item pages, the collection that the item is associated
    with will be displayed only (not the parent, if there is one).
    -   The collection displayed on the Phaeton item page will
        be Cadillac.

Customizing Public Display of Plugin Info
--------------------------------------------------------------------------------------------------------------------------

-   Edit the CollectionTreePlugin.php file found in the plugin's main
    directory to edit the text of headings on the Collections/show
    pages, or to modify the plugin's functions.

