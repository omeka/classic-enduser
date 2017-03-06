---
title: Display Specific Metadata for an Item File
---
*This documentation for Omeka versions up to 1.5 only*

Suppose you want to display specific metadata for an item file. You can retrieve any Dublin Core or Omeka Legacy element metadata. For example, suppose you want to print all of the Dublin Core Title data for the item files.


``` {.de1}
<?php
$elementSet = 'Dublin Core';
$elementName = 'Title'; 
while(loop_files_for_item()) {
    $fileTitle = $this->fileMetadata(get_current_file(), $elementSet, $elementName);
    echo '<p>' . $fileTitle . '</p>';
}
?>
```


You can retrieve the following internal metadata an item file:

-   id
-   archive filename
-   original filename
-   size
-   mime type
-   date added
-   date modified
-   authentication
-   mime type os
-   file type os
-   uri
-   fullsize uri
-   thumbnail uri
-   square thumbnail uri
-   permalink

Suppose you want to loop through the files for the current item, and create a link to that file. Then put the following code in your item/show.php page of your theme:



``` {.de1}
<?php 
while(loop_files_for_item()) {
    $fileTitle = $this->fileMetadata(get_current_file(), 'Dublin Core', 'Title');
    $fileDescription = $this->fileMetadata(get_current_file(), 'Dublin Core', 'Description');
    $fileURI = $this->fileMetadata(get_current_file(), 'uri');
    echo '<div>';
    echo '<a href="' . $fileURI . '">' . $fileTitle . '</a>';
    echo '<p>' . $fileDescription .  '</p>';
    echo '</div>';
}
?>
```

