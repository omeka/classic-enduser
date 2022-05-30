# Collection Tree

The [Collection Tree plugin](https://omeka.org/classic/plugins/CollectionTree/){target=_blank} allows Omeka Classic sites to have nested [collections](../Content/Collections.md). One collection can have at most one parent collection, but a collection may have zero or multiple child collections.

Once you have [installed](../Admin/Adding_and_Managing_Plugins.md) Collection Tree, the plugin will create a tab on the left-hand navigation of the admin side of the site. This tab allows you to view your collection hierarchy. To create a child/parent relationship between collections (nest), you must edit the collection.

You can configure the plugin to adjust the display by checking the following options:

- Order alphabetically: This setting orders the Collection Tree alphabetically, but does not affect the order of the collections browse page.
- Browse root-level collections only: This setting limites the public collections browse page so it only includes root collections and does not show subcollections.
- Show subcollections items: This setting includes all of the items from the subcollections in the list of items on the root collections' show page.
- Expand search to include subcollection items by default: This setting expands the universe for a collection search to include the content of the subcollections.

![Configuration page for the Collection Tree plugin with none of the options selected](../doc_files/plugin_images/collectionTree_config.png)

## Create a Collection Tree

You can only nest collections once you have at least two collections. 

To create a new child collection:

1. Go to the Collections tab on the left hand navigation of the admin dashboard. 
1. Click the *Add a Collection* button
1. Add the metadata as needed
1. Go to the *Parent Collection* tab across the top of the Add Collection menu
1. From the dropdown menu, select the parent collection for the current collection. 

![Collection tree parent.png](../doc_files/plugin_images/Collection_tree_parent.png)

To nest an existing collection:

1. Go to the Collections tab on the left hand navigation of the admin dashboard. 
1. Click *Edit* below the title of the collection you want to edit.
1. Go to the *Parent Collection* tab across the top of the Add Collection menu
1. From the dropdown menu, select the parent collection for the current collection. 

## Viewing Collection Trees

To view your collection tree, select Collection Tree in the left Admin navigation available from the Dashboard.

![Collection tree hierarchy, seen on admin side](../doc_files/plugin_images/collectionTree_view.png)

If you wish, you may make the Collection Tree's hierarchy viewable to the public, go to the Appearance tab in the top Admin navigation bar. Then, click on [Navigation](../Admin/Appearance/Navigation.md), and check or uncheck the Collection Page. 

This is what a sample public page looks like:
![Collection tree hierarchy, seen on public side](../doc_files/plugin_images/collectionTree_pubview.png)

