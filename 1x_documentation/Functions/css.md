---
title: Omeka Classic 1x Functions css
---
css() is a helper function used when referencing a css file within a theme, and commonly included within a theme's header.php file. It returns the path to a css file located in the css folder of that theme, usually located in themes/YourTheme/css.

**Note:** Starting with Omeka 1.3, the queue\_css helper is preferred to this one for most use cases.

Usage
---------------------------------------------------

``` {.de1}
    css($file, $dir = 'css')
```

Arguments
-----------------------------------------------------------

-   \$file (string) (required) The name of the file to be included. Do not include the .css extension.
-   \$dir (string) (optional, default: 'css') The name of the directory from which the file should be included.

Return Values
------------------------------------------------------

(string) Returns a string with the path to the CSS file passed to the function.

Example(s)
-------------------------------------------------------

### Add a link to a CSS file


``` {.de1}
    <link rel="stylesheet" href="<?php echo css('main'); ?>" />
```

The code above returns an HTML &lt;link&gt; to the stylesheet "main.css" in the theme's "css" directory. The following HTML will be returned.

The following HTML code will be returned when loading the page in your browser:

``` {.de1}
<link rel="stylesheet" 
      href="http://youromekasite.com/themes/YourTheme/main.css" />
```

Source File / Version
--------------------------------------------------------------

-   application/helpers/FileFunctions.php since Omeka 1.0.
