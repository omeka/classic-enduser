---
title: Omeka Classic 1x Functions display random featured item
---
*This documentation for Omeka versions up to 1.5 only*

Returns the HTML markup for displaying a random item that has been marked as "featured." This helper is most commonly used on the home page of public themes. Since the HTML is pre-formatted, any changes to the HTML syntax must be made by writing out the necessary code instead of using the helper function. 

Usage
---------------------------------------------------

``` {.de1}
<?php display_random_featured_item($withImage); ?>
```

Arguments
-----------------------------------------------------------

-   **\$withImage**: boolean (default false) - specifies whether or not the featured item must have an image associated with it in order to be displayed. If set to true, this will either display a clickable square thumbnail for an item, or it will display "You have no featured items" if there are none with images.

Examples
---------------------------------------------------------

To print the random featured item content, with an image, use the following code:


``` {.de1}
<?php echo display_random_featured_item(); ?>
```

To print the random featured item content, without an image, use the following code:

``` {.de1}
<?php echo display_random_featured_item(false); ?>
```

Here are the contents of display\_random\_featured\_item() for your reference:


``` {.de1}
<h2>Featured Item</h2>
<h3><a href="http://example.com/item/show/44">Item Title</a></h3>
<img src="http://example.com/archive/square_thumbnails/thumbnail.jpg" class="image" />
<p class="item-description">Item description here....</p>
```
