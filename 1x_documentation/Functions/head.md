---
title: Omeka Classic 1x Functions head
---
*This documentation for Omeka versions up to 1.5 only*

This function includes the file `header.php` in a theme. A view script needs to use this function along with foot() to create the structure of the
page.

Usage
---------------------------------------------------

``` {.de1}
<?php
head($vars = array(),
    $file = 'header');
?>
```

Arguments
-----------------------------------------------------------

 *array* `$vars` {{\#if
:   array() | (optional)}}
:   Variables to be passed to `header.php`.
:   {{\#if: array() | Default: `array()`}}

 *string* `$file` {{\#if
:   'header' | (optional)}}
:   Name of the file to include (without the .php extension).
:   {{\#if: 'header' | Default: `'header'`}}

Hooks
---------------------------------------------------

The [public\_theme\_header](../1x_documentation/Hooks/public_theme_header.md) (for public pages) and [admin\_theme\_header](../1x_documentation/Hooks/admin_theme_header.md) (for admin pages) are fired by `header.php`.

Example(s)
-------------------------------------------------------

### Include header.php in a theme

``` {.de1}
<?php head(); ?>
```

This code could be included near the beginning of a theme file to include `header.php`.

Source File / Version
----------------------------------------------------------------

-   application/helpers/Function.php in Omeka 1.0.
