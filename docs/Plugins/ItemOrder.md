# Item Order

The [Item Order plugin](https://omeka.org/classic/plugins/ItemOrder/){target=_blank} allows users to use a drag-and-drop interface change the order in which items display on the public Collection browse pages of your Omeka Classic site. It adds a new section to collection information pages in the administrative dashboard, where items can be manually rearranged. 

This screencast includes information on how Item Order can modify your item displays:

<div style="padding:62.5% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/194553469?h=015e0c53a1" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/194553469">Managing Collections in Omeka Classic</a> from <a href="https://vimeo.com/omeka">Omeka</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

## Order items in a collection

Item Order does not have any configuration settings, and will be available once [installed](../Admin/Adding_and_Managing_Plugins.md) and activated.
 
To use Item Order, go to the Collections tab in the sidebar of the admin dashboard. Find the collection whose items you want to reorder and click on the name of the collection (do not click on "Edit").

On the collections page (`admin/collections/show/`), scroll to the bottom of the page where you will find the heading "Item Order". Click the link to "Order items in this collection."

![Collection management page with the Item Order section called out in a blue box. Arrow points to the link for Order Items in this Collection.](../doc_files/plugin_images/itemorder_1.png)

A complete list of all items in that collection will appear on the page. Drag and drop the items into the preferred order. Changes are saved automatically.

Dragging automatically reorders the items for the public collection browse page. 

To see the public page, either click the link that states "**Click here** to return to the collection show page" and then click on "View Public Page", or navigate to `yoursite.org/items/browse?collection=1` (where 1 equals the number of the collection you modified).

![mouse hovering over the Click Here To Return button](../doc_files/plugin_images/Itemorderc.png)

### Restore original order

Click the Collections tab in the sidebar of the admin dashboard, find the collection you want to order and click on the name of the collection.

Then, scroll to the bottom of the page to the heading "Item Order" and click the "Reset Items to their default order" button.

![Cursor hovers over the green Reset button](../doc_files/plugin_images/Itemorderreset.png)
