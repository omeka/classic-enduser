---
title: Omeka Classic 1x Functions display css
---
*This documentation for Omeka versions up to 1.5 only*

The display\_css() helper function prints HTML `link` tags to the page for each stylesheet added with queue\_css(). It is
commonly used in a theme's common/header.php file to print the `link` tags inside the page `head`.

Usage
---------------------------------------------

``` {.de1}
<?php display_css(); ?>
```


Arguments
-----------------------------------------------------------

display\_css() takes no arguments.

Return Value
---------------------------------------------------------------

None. display\_css() prints the tags immediately, it does not return them as a string.

Example(s)
---------------------------------------------------------------

### <span id="Standard_Usage" class="mw-headline"> Standard Usage </span>

In a theme's common/header.php:


``` {.de1}
<?php display_css(); ?>
```

This will print a tag for any script added with
queue\_css(). In a theme, the call to display\_css() should come after the call to plugin\_header() so plugins have a chance to add their own CSS.

Source File / Version
---------------------------------------------------------------

-   application/helpers/AssetFunctions.php in Omeka 1.3.
