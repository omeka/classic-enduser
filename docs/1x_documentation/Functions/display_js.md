---
title: Omeka Classic 1x Functions display js
---
*This documentation for Omeka versions up to 1.5 only*

The display\_js() helper function prints HTML `script` tags to the page for each script added with queue\_js(). It is commonly used in a theme's common/header.php file to print the `script` tags inside the page `head`.

display\_js() will also include Omeka's "default" JavaScript files.

Usage
--------------------------------------------

``` {.de1}
<?php display_js($includeDefaults = true); ?>
```

Arguments
-----------------------------------------------------------

-   \$includeDefaults (boolean) (optional) (default: true) Whether or not to include Omeka's default scripts in the output. By default, the scripts will be included.

Return Value
-----------------------------------------------------

None. display\_js() prints the tags immediately, it does not return them as a string.

Example(s)
-----------------------------------------------------------------

### Standard Usage

In a theme's common/header.php:

``` {.de1}
<?php display_js(); ?>
```


This will print a tag for any script added with [queue\_js()](../1x_documentation/Theme_API/queue_js.md), as well as Omeka's default scripts. In a theme, the call to display\_js() should come after the call to [plugin\_header()](../1x_documentation/Theme_API/plugin_header.md) so plugins have a chance to add their own JavaScript.

### Exclude Default Scripts

``` {.de1}
<?php display_js(false); ?>
```

Adding the false parameter to display\_js() causes it to only print tags for scripts specifically added with [queue\_js()](../1x_documentation/Theme_API/queue_js.md). You may wish to do this on specific pages you know do not need Omeka's default scripts, or to avoid conflicts with custom JavaScript.

Note: it is not recommended to use this form of display\_js() in a theme's common/header.php. This will exclude the default scripts from all pages, and will likely cause Omeka and many plugins to malfunction.
 
Source File / Version
----------------------------------------------------------------

-   application/helpers/AssetFunctions.php in Omeka 1.3.
