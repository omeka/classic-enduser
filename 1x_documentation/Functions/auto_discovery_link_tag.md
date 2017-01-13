---
title: Omeka Classic 1x Functions auto discovery link tag
---
*This documentation for Omeka versions up to 1.5 only*

This function outputs a &lt;link&gt; tag for the RSS feed so the browser can auto-discover the feed.

Usage
---------------------------------------------------

``` {.de1}
auto_discovery_link_tag()
```

Arguments
-----------------------------------------------------------

This function does not take any arguments.

Return Values
-------------------------------------------------------------------

(string HTML)

Example(s)
---------------------------------------------------------------

Add a &lt;link&gt; to the RSS feed in the &lt;head&gt; of the theme.


``` {.de1}
       <?php echo auto_discovery_link_tag(); ?>
```

The code above should be placed between the &lt;head&gt; tags of the theme's header.php file.

Source File / Version </span>
---------------------------------------------------

-   application/helpers/Functions.php in Omeka 1.0.
