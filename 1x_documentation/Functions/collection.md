---
title: Omeka Classic 1x Functions collection
---

Description
---------------------------------------------------------------

The `collection()` helper will return the value of a specific field for a collection object.

Usage
---------------------------------------------------


``` {.de1}
<?php echo collection($fieldName, $options = array()); ?>
```

Arguments
-----------------------------------------------------------

-   **\$fieldName** (string) - The name of the field you'd like
    to return. Available fields for collection:
    -   Name - Returns the collection name.
    -   Description - Returns the description of the collection.
    -   ID - Returns the ID of the collection.
    -   Public (boolean) - Returns true if a collection is flagged as public.
    -   Featured (boolean) - Returns true if a collection is flagged as featured.
    -   Date Added - Returns the date the collection was added to Omeka.
    -   Date Modified - Returns the date the collection was modified.
    -   Collectors - Returns an array of collectors associated with a collection.
-   **\$options** (array) - One option is available:
    -   snippet - (integer). Setting `snippet` to a particular number will truncate the return text to that number of characters.

Examples
---------------------------------------------------------

### Show the Collection Name
Set to "true" by default, the show\_empty\_elements option allows you to limit the fields displayed to all fields or to non-empty fields for an item. Setting this to "false" will only display fields that have data.


``` {.de1}
<?php 
 
echo collection('Name'); 
 
?>
```


### Show the Description using Snippet
The following example returns a collection's Description field, using the snippet option to return only the first 200 characters of the field's value:

``` {.de1}
<?php 
 
echo collection('Description', array('snippet' => 200)); 
 
?>
```

