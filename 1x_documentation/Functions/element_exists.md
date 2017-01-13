---
Title: Function element exists
---
*This documentation for Omeka versions up to 1.5 only*

Checks to see if a given element exists, and is part of a specified element set.

Usage
---------------------------------------------------

``` {.de1}
<?php element_exists($elementSetName, $elementName) ?>
```

Arguments
-----------------------------------------------------------

-   \$elementSetName (*string*): The element set to check.
-   \$elementName (*string*) The name of the element to check

Example
-------------------------------------------------------

This function can generally be used to check if an element exists before displaying it


``` {.de1}
<?php 
if ( element_exists('Dublin Core', 'Date Added') ) {
    echo item('Dublin Core', 'Date Added');
}
?>
```

Source File/Version
-------------------------------------------------------------

-   application/libraries/globals.php since Omeka 1.3