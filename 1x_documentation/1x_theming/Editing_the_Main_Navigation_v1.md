---
title: Editing the Main Navigation
---
*This documentation is for Omeka Classic versions 1.0-1.5*

The main navigation for most Omeka themes use the `public_nav_main` helper to create the main navigation. You can easily modify the navigation editing `header.php` in your theme, and finding the `public_nav_main` helper. Please note that plugins can filter the `public_nav_main` helper to add links to pages without directly modifying the array in the template. If you want to create a custom navigation list, one that cannot be modified by a plugin, use the `nav` helper instead.

The default navigation for most Omeka themes looks something like this:

``` {.de1}
<?php echo public_nav_main(
               array(
                  'Browse Items' => uri('items'), 
                  'Browse Collections' => uri('collections')
               )
           ); 
?>
``` 

To customize this list, you simply need to change the values inside the array for `public_nav_main`. The syntax for that array is `'Text for Link' => uri('value-for-uri')`. This uses the `uri` helper to generate the uri to a particular page in your theme.

Let's start simple; We're going to keep the links as-is, but only change the text of the links themselves. We can remove "Browse" from the link text, to only have "Items" and "Collections", respectively, like so:

``` {.de1}
<?php echo public_nav_main(
               array(
                  'Items' => uri('items'), 
                  'Collections' => uri('collections')
               )
           ); 
?>
```

We can also add add links. The next example will add a link to the items tag cloud:

``` {.de1}
<?php echo public_nav_main(
               array(
                  'Items' => uri('items'),
                  'Tags'  => uri('items/tags'), 
                  'Collections' => uri('collections')
               )
           ); 
?>
```

We use the word "Tags" for the link text, and `uri('items/tags')` to link to the items/tags page.

You can add any text and any uri to the navigation array. Make sure the URI points to an existing page on your site, though, before adding it to the navigation.
