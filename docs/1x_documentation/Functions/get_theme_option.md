---
title: Omeka Classic 1x Functions/get theme option
---

*This documentation for Omeka versions up to 1.5 only*

Since Omeka 1.2, the `get_theme_option` is available to get the value for a theme option. The [Theme Configuration](../1x_documentation/1x_theming/Theme_Configuration.md) page has an explanation of how to use options for theme configuration.

Usage
---------------------------------------------------

``` {.de1}
<?php get_theme_option($optionName, $theme = null); ?>
```

Arguments
-----------------------------------------------------------

-   optionName (string) - The name of the option.
-   theme (string) - The name of the theme for which to get the option. Default is null.

Changelog
-------------------------------------------------

-   Since 1.2.

Examples
-------------------------------------------------

The following will look for an option called 'Style Sheet' in your theme options, and define a variable with that option value:

``` {.de1}
<?php 
$styleSheet = get_theme_option('Style Sheet');
?>
```

You can then use this code in your public theme. The following example takes the code above and uses it in a theme's common/header.php file:

``` {.de1}
<?php 
$styleSheet = get_theme_option('Style Sheet');
?>
<link rel="stylesheet" href="<?php echo $styleSheet; ?>" />
```
