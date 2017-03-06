---
title: Omeka Classic 1x Functions collection is featured
---
*This documentation for Omeka versions up to 1.5 only*

The `collection_is_featured` helper returns whether the current
collection is featured.

Usage
---------------------------------------------------


``` {.de1}
<?php collection_is_featured(); ?>
```

Arguments
-----------------------------------------------------------

None

Examples
---------------------------------------------------------

The following example will print 'Featured Collection' on the collections/show.php page, if the collection your are viewing is a featured collection.



``` {.de1}
<?php if(collection_is_featured()) echo 'Featured Collection'; ?>
```
