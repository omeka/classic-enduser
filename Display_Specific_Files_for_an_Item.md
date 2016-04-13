
Display Specific Files for an Item
==================================

Lets say that you'd like to display a specific file for each item, say
the first file, in a different manner than your other files. To do so,
there are several ways to retrieve the first file for an item. The
following examples can be used on the items/show.php template page, but
could be modified to work anywhere that an Item object is available in
your theme.

The Item Files array
---------------------------------------------------------------------------------

The files for an item are stored in an array, which can be accessed using `$item->Files;` in your template file. To get the first file for an item, we can use the following:


``` {.de1}
<?php
 
$files = $item->Files;
$firstFile = $files[0];
 
?>
```


PHP uses [zero-based arrays](http://en.wikipedia.org/wiki/Zero-based), so the first value in array uses the index "0".

Once we have our file object, we can display the file or metadata associated with it using any number of [theme helpers](Theme_API.html "Theme API"). The next bit of code, building from the previous example, uses the [display\_file](http://omeka.org/c/index.php?title=Theme_API/display_file&action=edit&redlink=1 "Theme API/display file (page does not exist)") helper to display the file in whatever format Omeka thinks is best:

``` {.de1}
<?php
 
$files = $item->Files;
$firstFile = $files[0];
 
echo display_file($firstFile);
?>
```


You can also, as of Omeka version 1.1, display the file metadata for our first file using the [show\_file\_metadata](Theme_API/show_file_metadata.html "Theme API/show file metadata") helper:


``` {.de1}
<?php
 
$files = $item->Files;
$firstFile = $files[0];
 
show_file_metadata(array(), $firstFile);
?>
```

Showing Specific Files with Helpers
---------------------------------------------------------------------------------------------------------------

A few theme helpers allow you to specify which files to display. [Theme
API/item\_image](http://omeka.org/c/index.php?title=Theme_API/item_image&action=edit&redlink=1 "Theme API/item image (page does not exist)"), [Theme
API/item\_fullsize](Theme_API/item_fullsize.html "Theme API/item fullsize"), [Theme
API/item\_thumbnail](Theme_API/item_thumbnail.html "Theme API/item thumbnail"), and [Theme API/item\_square\_thumbnail](Theme_API/item_square_thumbnail.html "Theme API/item square thumbnail") allow you to pass the index number of the file as a parameter.

Showing Only Image Files 
-----------------------------------------------------------------------------------------

The \$item-&gt;Files array will return all the files associated with an
item, regardless of the type of file. If you want to loop through all of your files, and only display the ones that are images, you'll need to check each file to see if it has an thumbnail associated with it. The following code example shows you how:


``` {.de1}
<?php
$files = $item->Files;
if($files) {
    foreach($files as $file) {
        if($file->hasThumbnail()) {
            display_file($file);
        }
    }
}
?>
```
