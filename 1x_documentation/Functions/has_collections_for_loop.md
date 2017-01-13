---
title: Omeka Classic 1x Functions has collections for loop
---
*This documentation for Omeka versions up to 1.5 only*

The `has_collections_for_loop` helper returns true or false if there are collections available for a loop. Usually used inside an `if()` statement.

Usage
-----------------------------------------------


``` {.de1}
<?php has_collections_for_loop(); ?>
```

Examples
-------------------------------------------------

The following example sets a custom loop of recent collections. It uses the `has_collections_for_loop` to check if there are recent collections to display in the loop. If there are none, the phrase "No recent collections available.":

``` {.de1}
<?php set_collections_for_loop(recent_collections(5)); ?>
<?php if (has_collections_for_loop()): ?>
    <ul class="collections-list">
    <?php while (loop_collections()): ?>
        <li class="collection">
            <h3><?php echo link_to_collection(); ?></h3>
            <?php if($desc = collection('Description', array('snippet'=>150))): ?>
            <div class="collection-description"><?php echo $desc; ?></div>
            <?php endif; ?>       
        </li>     
    <?php endwhile; ?>
    </ul>
<?php else: ?>
    <p>No recent collections available.</p>
<?php endif; ?>
```

