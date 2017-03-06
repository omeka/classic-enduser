---
title: Display Specific Metadata for an Item
---
*This documentation for Omeka versions up to 1.5 only*

In cases where you want to display specific metadata for an item, in a specific order, you can use the [item](Theme_API/item.html "Theme API/item") helper for each metadata field instead of relying on the
[show\_item\_metadata](Theme_API/show_item_metadata.html "Theme API/show item metadata") helper.

Lets say, for example we want to forgo using the `show_item_metadata` helper, and instead display the Title, Creator, Description, and Tags for every item. Lets use the `item` helper to get the first three fields, wrapping each instance of those fields with an HTML:


``` {.de1}
<h2 id="item-title"><?php echo item('Dublin Core', 'Title'); ?></h2>
<p id="item-creator"><?php echo item('Dublin Core', 'Creator'); ?></p>
<div id="item-description">
    <?php echo item('Dublin Core', 'Description'); ?>
</div>
```

You could do something similar for any of the Dublin Core or Item Type Metadata fields.

For the tags, we'll use another helper function, [item\_tags\_as\_string](Theme_API/item_tags_as_string.html "Theme API/item tags as string"), to display the tags as a comma-separated string, like so:

Since we're not passing any parameters to the `item_tags_as_string`, we'll use the defaults.

All of the code, written together, would look like this:

``` {.de1}
<h2 id="item-title"><?php echo item('Dublin Core', 'Title'); ?></h2>
<p id="item-creator"><?php echo item('Dublin Core', 'Creator'); ?></p>
<div id="item-description">
    <?php echo item('Dublin Core', 'Description'); ?>
</div>
<div id="item-tags">
    <?php echo item_tags_as_string(); ?>
</div>
```

This would generate:


``` {.de1}
<h2 id="item-title">Item Title</h2>
<p id="item-creator">Jane Doe</p>
<div id="item-description">
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing 
elit, sed do eiusmod tempor incididunt ut labore et dolore 
magna aliqua. Ut enim ad minim veniam, quis nostrud 
exercitation ullamco laboris nisi ut aliquip ex ea commodo 
consequat. Duis aute irure dolor in reprehenderit in voluptate 
velit esse cillum dolore eu fugiat nulla pariatur. Excepteur 
sint occaecat cupidatat non proident, sunt in culpa qui 
officia deserunt mollit anim id est laborum.</p>
</div>
<div id="item-tags">
    Lorem, ipsum, dolor, sit, amet
</div>
```
