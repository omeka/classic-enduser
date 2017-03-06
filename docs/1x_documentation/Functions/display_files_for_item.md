---
title: Omeka Classic 1x Functions display files for item
---

Description
---------------------------------------------------

The `display_files_for_item` helper will display any files associated with an particular item. The helper attempts to display the file using proper HTML (&lt;img /&gt; for images, &lt;object /&gt; for movies and audio). If the helper cannot determine the proper format for a file, it simply creates a link to the file for direct download.

Usage
----------------------------------------------

``` {.de1}
<?php
 
display_files_for_item(
    $options = array(), 
    $wrapperAttributes = array('class'=>'item-file'), 
    $item = null
);
 
?>
```


Arguments 
-------------------------------------------------

-   options - An array of options. Available options include:
    -   imageSize - (string), e.g. ('imageSize' =&gt; 'thumbnail').         Valid values include: thumbnail, square\_thumbnail,         and fullsize)
    -   showFilename - (boolean)
    -   linkToFile - (boolean)
    -   linkAttributes - (array) An array of attributes for the         file link.
    -   filenameAttributes - (array) =&gt;array('class'=&gt;'error'),
    -   imgAttributes - (array)
    -   icons - (array) An array of icon files to associate with a         particule file MIME type.
-   wrapperAttributes - An array of attributes for the wrapper div     around each item. Default includes a class attribute with the     value 'item-file'.
-   item - The item object for which you want to display files. If null, the current item is used.

Examples
------------------------------------------------


``` {.de1}
<div id="itemfiles" class="element">
    <h3>Files</h3>
    <div class="element-text">
        <?php echo display_files_for_item(); ?>
    </div>
</div>
```
