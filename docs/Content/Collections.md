# Collections

Collections are groups of Omeka items. Collections are a flexible means of organizing and presenting Omeka items, and may be used in a variety of contexts that make the most sense for your objects.

In Omeka Classic, an item can only belong to one collection. Collections can, of course, have multiple items. The concept of Omeka collections originates from museum and archives collections; one cannot put a document into more than one box. It is not necessary to follow a traditional interpretation of a collection, say by owner or donor. 

Collections have no hierarchy, unless you install the [Collection Tree plugin](../Plugins/CollectionTree.md) in order to have a nested collections. Items in collections have no set order, unless you install the [Item Order plugin](../Plugins/ItemOrder.md) in order to rearrange your items. 

The following screencast covers creating collections and adding items to those collections, as well as how to use the Collection Tree and Item Order plugins:

<div style="padding:62.5% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/194553469?h=015e0c53a1" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/194553469">Managing Collections in Omeka Classic</a> from <a href="https://vimeo.com/omeka">Omeka</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

You can also use [tags](Tags.md) to organize similar items into categories. Tags can provide the multi-category flexibility that collections don't offer. 

The following screencast can help you determine when you would like to use collections or tags:

<div style="padding:51.99% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/102040465?h=00bd26943c" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/102040465">Omeka Classic: Managing Collections and Tags</a> from <a href="https://vimeo.com/omeka">Omeka</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

Create a collection
-----------------------------------------------------------
1.  Click on the "Collections" tab in the left navigation bar from the Dashboard. Any collections you have created will be listed on the `admin/collections` page.
2.  To create a new collection, click, "Add a Collection".
3.  You may assign a full complement of Dublin Core metadata to any collection, or simply create a title and description.
4.  To make your collection public, check the "Public" box under the "Add Collection" button. Likewise, to feature your collection, check "Feature".
5.  When you are finished adding metadata, click the "Add Collection" button to save it.

Now that you have created a collection you may associate an item with this collection, from the `items/add` or `items/edit` pages. Read more below.

![A screenshot of the Add a Collection page, with no metadata entered](../doc_files/collectionAdd.png "A screenshot of the Add a Collection page, with no metadata entered")

Adding items to collections
-------------------------------------------------------------

To add items to a collection, you must first create the collection. See the [Items documentation](Items.md) to read more about associating an item with a collection. An item may only belong to one collection at a time. You may switch an item from one collection to another at any time.

Items can only be added to a collection from the "Browse Items" page, at `/admin/items`, or from an individual item's editing interface.

From the item edit page, use the dropdown menu on the right hand side, under the "Save Changes" button, to select a collection.

![Dropdown menu in the item edit page is emphasized with a teal arrow](../doc_files/collectionAddItem.png "Dropdown menu in the item edit page is emphasized with a teal arrow.")

From the "Browse Items" page, you can use the batch-edit option to add multiple items to a collection, again using a dropdown menu to select the existing collection.

![Dropdown menu in the batch item edit page is emphasized with a teal arrow](../doc_files/collectionAddBatch.png "Dropdown menu in the batch item edit page is emphasized with a teal arrow.")

The thumbnail image for a collection is automatically derived from the primary file of the most recently created item in the collection, and cannot be edited. 

Edit a collection
---------------------------------------------------------------

To edit a collection, click the "Edit" link underneath the title from the Collections page, at `/admin/collection`. Edit in any fields you wish, and click the "Save Changes" button to the right of the screen.

Browsing collections
---------------------------------------------------------------

By clicking the Collections tab, you may browse through the collections in your archive. They are listed with very basic metadata: Title, Contributors, Date Added, and Total Number of Items. You may sort collections by clicking Title or Date Added.

On the public interface, you can find the Browse Collections page at `yoursite/collections/browse`. A link is automatically added to the site navigation pointing to `yoursite/collections/browse`, and can be turned off in the [Navigation settings](../Admin/Appearance/Navigation.md).

