---
title: Changing Exhibit Themes to Public Themes in Omeka Classic 1x
---
*This documentation for Omeka versions 1.3-1.5 only*

Omeka 1.3 and Exhibit Builder 1.0 changed how Exhibit Builder handles themes. There are no longer themes specific to Exhibit Builder, instead you can choose any available public themes. As such, any themes created specifically for Exhibit Builder will need to be converted to a public theme by following this process.

Essentially you will simply need to move your existing files into a new directory structure and place that into your themes folder.

The new directory structure is as follows:

-   ThemeName
    -   css/
        -   screen.css
    -   common/
        -   header.php
        -   footer.php
    -   exhibit-builder/
        -   exhibits/
            -   summary.php
            -   show.php
            -   item.php
    -   theme.ini

This new theme should just be placed in your theme directory (omeka/themes/), and you should then be able to select the theme in Exhibit Builder.

There are also a few changes you need to make to individual files. First, note you need to add a theme.ini file containing some metadata about the theme. Here is an example, just change the values as needed:

``` {.de1}
;;;;;;;
; Theme Settings
;;;;;;;
[theme]
author = "Ken Albers & Jeremy Boggs"
title = "Berlin"
description = "Abstraction of the Making the History of 1989 theme."
license = "GPL"
website = "omeka.org"
omeka_minimum_version="1.3-dev"
omeka_tested_up_to="1.3-dev"
version="1.3"
tags="minimal, modern, white, blue, orange, sans-serif"
```

Additionally, we have changed how styles are handled in header.php. Wherever you called a css file using

``` {.de1}
<link rel="stylesheet" media="screen" href="<?php echo css('style'); ?>" />
```

you now need to use


``` {.de1}
<?php 
    queue_css('style');
    display_css(); 
?>
```

Finally, in your files in the exhibits directory (summary, show, and items) you now call the header and footer with `head()` and `foot()` instead of `exhibit_builder_exhibit_head()` and
`exhibit_builder_exhibit_foot()`.
