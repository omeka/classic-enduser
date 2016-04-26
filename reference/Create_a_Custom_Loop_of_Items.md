Create a Custom Loop of Items
=============================


There may be some cases where you will want to display a custom loop of items, on your homepage or elsewhere in your theme.

Step 1: Getting your Custom List of Items
-----------------------------------------------------------------

The first thing we need to do is get the array of items we want to loop through. We do this using the [get\_items](https://omeka.org/codex/Theme_API/get_items "Theme API/get items")
and [set\_items\_for\_loop](https://omeka.org/codex/Theme_API/set_items_for_loop "Theme API/set items for loop") helpers in tandem. Let's say, for example, we want a loop of ten recent items that are Documents (item type) and are tagged 'history'. We'll use the `get_items` helper to query the database for items matching that criteria, and place that query inside the `set_items_for_loop` help to "set" those items for the loop we'll create later:

``` {.de1}
<?php
set_items_for_loop(get_items(array('recent' => true, 
'tags' => 'foo, bar', 'type' => 'Document'),10));
?>
```


Step 2: Start the Loop
--------------------------------------------------------------

Once we have set the items to loop through, using the `get_items` helper, we can now build a loop. First, we'll want to check to make sure there are in fact items that match the criteria we've used. This can be done using a simple `if` statement:

``` {.de1}
<?php
set_items_for_loop(get_items(array('recent' => true, 
'tags' => 'foo, bar', 'type' => 'Document'),10));
?>
<?php if(has_items_for_loop()): ?>
 
   <!-- Loop for items -->
 
<?php else: ?>
 
    <!-- Message if there are no items -->
    <p>No Documents tagged "history".</p>
<?php endif; ?>
```

Notice that we've left a place to display a message if there are no posts matching the criteria we've given.

Now that we have the `if` statement in place, we can now add our loop code. We need to use the `loop_items` helper to actually start the loop itself.

``` {.de1}
<?php
set_items_for_loop(get_items(array('recent' => true, 
'tags' => 'foo, bar', 'type' => 'Document'),10));
?>
<?php if(has_items_for_loop()): ?>
 
   <!-- Loop for items -->
    <?php while(loop_items()): ?>
 
    <?php endwhile; ?>
 
<?php else: ?>
 
    <!-- Message if there are no items -->
    <p>No Documents tagged "history".</p>
<?php endif; ?>
```

Step 3: Display Item Metadata
---------------------------------------------------------------------

Now that we have our loop of items ready, we can now add helper functions to retrieve specific bits of metadata for each item in the loop. Because this is a loop through ten items, you'll only need to use the helper functions once; The page will display the same metadata for each of the ten items sequentially.

Inside our `while(loop_items())` loop, lets add some HTML markup to separate each item. We'll also use the [link\_to\_item](https://omeka.org/codex/Theme_API/link_to_item "Theme API/link to item") helper to generate a link to the item's show page. And, we'll use the [item](https://omeka.org/codex/Theme_API/item "Theme API/item") helper to retrieve the description for each item:

``` {.de1}
<?php
set_items_for_loop(get_items(array('recent' => true, 
'tags' => 'foo, bar', 'type' => 'Document'),10));
?>
<?php if(has_items_for_loop()): ?>
 
   <!-- Loop for items -->
    <?php while(loop_items()): ?>
    <div class="item">
        <h2><?php echo link_to_item(); ?></h2>
        <p><?php echo item('Dublin Core', 'Description'); ?></p>
    </div>
    <?php endwhile; ?>
 
<?php else: ?>
 
    <!-- Message if there are no items -->
    <p>No Documents tagged "history".</p>
<?php endif; ?>
```

This code will then display the title and description for each of the ten items retrieved. It will wrap each item in a `<div>` with a class attribute of "item".

If you want to retrieve more metadata about an item, using any of the available [Theme API](Theme_API.1.html "Theme API") helpers for items, just remember to put them inside that `while` loop of items.
