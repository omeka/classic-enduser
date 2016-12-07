---
title: Collection Item Thumbnails
----
AOrdine 2011

Problem
-------------------------------------------------------

I wanted to add items with images to my collections browse page.

Solution
---------------------------------------------------------

I made a loop of featured items for each collection and displayed thumbnails that linked to the collection show page.

### Functions Used

-   [get\_items()](../Functions/get_items.html "Functions/get items")
-   [link\_to\_collection\_for\_item()](../Functions/link_to_collection_for_item.html "Functions/link to collection for item")

By default the collections browse page (collection/browse.php) shows each collection title, description, collectors and a link to the collection.


``` {.de1}
<div class="pagination"><?php echo pagination_links(); ?></div>
        <?php while (loop_collections()): ?>
            <div class="collection">
 
                <h2><?php echo link_to_collection(); ?></h2>
 
                <div class="element">
                <h3>Description</h3>
                <div class="element-text"><?php echo nls2p(collection('Description', array('snippet'=>150))); ?></div>
                </div>
 
                <div class="element">
                <h3>Collector(s)</h3>
                <?php if (collection_has_collectors()): ?>
                    <div class="element-text">
                    <p><?php echo collection('Collectors', array('delimiter'=>', ')); ?></p>
                    </div>
                <?php endif; ?>
                </div>
 
                <p class="view-items-link"><?php echo link_to_browse_items('View the items in ' . collection('Name'), array('collection' => collection('id'))); ?></p>
 
            <?php echo plugin_append_to_collections_browse_each(); ?>
 
            </div><!-- end class="collection" -->
        <?php endwhile; ?>
```

I inserted five featured item thumbnails for each collection above the "view-items-link".

``` {.de1}
<div class="collection-items">
<?php
$items = get_items(array('collection'=>get_current_collection()->id, 'featured' => true), 5);
set_items_for_loop($items);
while(loop_items()):
if (item_has_thumbnail()): 
    echo link_to_collection_for_item(item_square_thumbnail(),  array('class' => 'collection-img')); 
endif; 
endwhile; 
?>  
</div>    
<p class="view-items-link"><?php echo link_to_browse_items('View the items in ' . collection('Name'), array('collection' => collection('id'))); ?></p>
```


This uses `get_items()` to get items in the current collection, that are featured, with a limit of 5. Since I did not want to link directly to the item, I made each item's thumbnail a `link_to_collection_for_item`. I also added the class `collection-img` for styling.
