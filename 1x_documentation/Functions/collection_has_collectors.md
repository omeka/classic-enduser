---
title: Omeka Classic 1x Functions collection has collectors
---

The `collection_has_collectors` returns true or false if a given collection has collectors associated with it.

Usage 
----------------------------

``` {.de1}
<?php collection_has_collectors(); ?>
```

Arguments
-----------------------------------------------------------

None

Examples
---------------------------------------------------------

The following example, which can be used on the collections/show.php template file in your theme, checks to see if the collection being viewed has collectors, and if so, displays the collectors using the [collection](../Theme_API/collection.html "Theme API/collection") helper:

``` {.de1}
<?php if(collection_has_collectors()): ?>
    <p><?php echo collection('Collectors', array('delimiter'=>', ')); ?></p>
<?php endif; ?>
```
