---
title: Display a Specific Collection
---
*This documentation for Omeka versions up to 1.5 only*

There may be some instances when you want to display the metadata for a specific collection on your theme. You can use the following methods to display a specific collection:

Set the Current Collection
----------------------------------------------------------------

You first need to set the collection using several helpers: [set\_current\_collection](Theme_API/set_current_collection.html "Theme API/set current collection")
and [get\_collection\_by\_id](Theme_API/get_collection_by_id.html "Theme API/get collection by id"). So, this example requires you to know the ID of the collection you'd like to use.

``` {.de1}
<?php
set_current_collection(get_collection_by_id(4));
?>
```

Displaying the Title and Description
-----------------------------------------------------------------------------------------------------------------

Once we set the current collection, we can then use the [collection](Theme_API/collection.html "Theme API/collection") helper available to display data associated with that collection. We can do something simple like display the *Title* and *Description*

``` {.de1}
<?php set_current_collection(get_collection_by_id(4)); ?>
<h2><?php echo collection('Title'); ?></h2>
<div id="collection-description"><?php echo collection('Description'); ?></div>
```  