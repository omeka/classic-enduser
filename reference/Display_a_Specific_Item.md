Display a Specific Item
=======================


You can easily display metadata for a specific item anywhere in your theme. Using the following methods, you can display item metadata on your homepage, on your items/browse page, or any theme page you'd like.

Set the Current Item 
---------------------------------------------------------------------------------

You first need to set the item using several helpers: [set\_current\_item](Theme_API/set_current_item.html "Theme API/set current item")
and [get\_item\_by\_id](Theme_API/get_item_by_id.html "Theme API/get item by id"). So, this example requires you to know the ID of the item you'd like to use.

``` {.de1}
<?php
set_current_item(get_item_by_id(24));
?>
```

Displaying Specific Metadata
-------------------------------------------------------------------------------------------------

Once we set the current item, we can then use any item helper available
to display data associated with that item. We can do something simple
like display the *Title* and *Description*


``` {.de1}
<?php
set_current_item(get_item_by_id(24));
?>
<h2><?php echo item('Dublin Core', 'Title'); ?></h2>
<div id="item-description"><?php echo item('Dublin Core', 'Description'); ?></div>
```

You can display any specific field using the [item](Theme_API/item.html "Theme API/item") helper.

Displaying All Metadata 
---------------------------------------------------------------------------------------

You can also use the [show\_item\_metadata](Theme_API/show_item_metadata.html "Theme API/show item metadata") helper to display all the item metadata:


``` {.de1}
<?php
set_current_item(get_item_by_id(24));
?>
<h2><?php echo item('Dublin Core', 'Title'); ?></h2>
<?php echo show_item_metadata(); ?>
```

