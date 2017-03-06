---
title: Omeka Classic 1x Functions display files
---
*This documentation for Omeka versions up to 1.5 only*

Displays a set of files based on the file's MIME type and any options that are passed. This is primarily used by other helper functions and will not be used by theme writers in most cases.

The `display_files` function does the actual work for the `display_files_for_item` helper function.

Usage
---------------------------------------------------

``` {.de1}
<?php
 
display_files(
    $files,
    array $props = array(),
    $wrapperAttributes = array('class'=>'item-file')
);
 
?>
```

Arguments
-----------------------------------------------------------

-   files - An array of File records to display
-   props - An array of properties to customize display for different file types.
-   wrapperAttributes - An array of attributes for the wrapper div  around each item. Default includes a class attribute with the value 'item-file'.

Examples
-------------------------------------------------

It is recommended that themes use the `display_files_for_item` helper function, however, the following is an example which could be used.

``` {.de1}
<div id="itemfiles" class="element">
    <h3>Files</h3>
    <div class="element-text">
        <?php echo display_files(get_current_item()->Files); ?>
    </div>
</div>
```