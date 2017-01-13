---
title: Theme Configuration
---
*This documentation for Omeka versions up to 1.5 only*


Starting with Omeka 1.2, theme writers have the ability to add
configuration options to themes. These options are stored in the Options table in Omeka, and are called using the
[get\_theme\_option](Theme_API/get_theme_option.html "Theme API/get theme option") 
helper in the theme.

Adding a Configuration Form to your Theme
----------------------------------------------------------------------------------

Before end-users can configure a theme, you must include a `config.ini` file in your theme. This config file uses methods from Zend Form to create a configuration form available in the Omeka admin. Adding this file will make a "Configure" button appear next to the name of the currently-active theme.

Each field should be indicated by prepending a 'fieldname' before all the options in the `config.ini` file.

-   fieldname.type: The type of field. Possible values include 'file', 'text', 'textarea', 'checkbox', and 'select'.
-   fieldname.options.label: The form label for the field
-   fieldname.options.description: The explanatory text for the field. This will display below the field in the form

### Example 'checkbox' field type

The following creates a field called 'display\_featured\_item' that uses a `<input type="checkbox">` input.

``` {.de1}
display_featured_item.type = "checkbox"
display_featured_item.options.label = "Display Featured Item"
display_featured_item.options.description = "Check this box if you wish to show the featured item on the homepage."
display_featured_item.options.value = "1"
```

### Example 'file' field type

The following creates a field called 'logo' that uses a
`<input type="file">` input.


``` {.de1}
logo.type = "file"
logo.options.label = "Logo File"
logo.options.description = "Choose a logo file. This will replace the site title in the header of the theme. Recommended maximum width for the logo is 500px."
logo.options.validators.count.validator = "Count"
logo.options.validators.count.options.max = "1"
```

### Example 'select' field type

The following creates a field called 'style\_sheet' that uses a
`<select>` input.

``` {.de1}
style_sheet.type = "select"
style_sheet.options.label = "Style Sheet"
style_sheet.options.description = "Choose a style sheet"
style_sheet.options.multiOptions.spring = "Spring"
style_sheet.options.multiOptions.summer = "Summer"
style_sheet.options.multiOptions.autumn = "Autumn"
style_sheet.options.multiOptions.winter = "Winter"
style_sheet.options.value = "winter"
```

### Example 'textarea' field type

The following creates a field called 'homepage\_text' that uses a `<textarea>` input.

``` {.de1}
homepage_text.type = "textarea"
homepage_text.options.label = "Homepage Text"
homepage_text.options.description = "Add some text to be displayed on your homepage."
homepage_text.options.rows = "5"
homepage_text.options.attribs.class = "html-input"
```

Using Configuration Options in your Theme
----------------------------------------------------------------------------------

Once a user has saved some configuration options, you can then use the values for those options anywhere in your theme. The easiest way to do this is to define a PHP variable using the
[get\_theme\_option](Theme_API/get_theme_option.html "Theme API/get theme option") helper, like so:

``` {.de1}
<?php $optionValue = get_theme_option('Option Name'); ?>
```

In another example, the Rhythm theme includes a custom function inside the `custom.php` file for retrieving and using the 'Style Sheet' option:

``` {.de1}
function rhythm_get_stylesheet($styleSheet = null)
{    
    if (!$styleSheet) {
        // If the 'Style Sheet' option has a value, use it. Otherwise, use 'fall'  
        $styleSheet = get_theme_option('Style Sheet') ?
                      get_theme_option('Style Sheet') : 
                      'fall';
    }
    return $styleSheet;   
}
```

This code will return the value for get\_theme\_option('Style Sheet').
If the option doesn't have a value, it will use 'fall'.

The theme then uses this function in `header.php` to call the
appropriate style sheet:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="html4strict source-html4strict">

``` {.de1}
<link rel="stylesheet" media="screen" 
    href="<?php echo html_escape(css(rhythm_get_stylesheet())); ?>" />
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Theme\_Configuration](Theme_Configuration.html)"

</div>

<div id="catlinks" class="catlinks catlinks-allhidden">

</div>

</div>

<div id="secondary">

<div class="portlet">

Documentation
-------------

-   [Home](http://omeka.org/codex/)
-   [Screencasts](http://omeka.org/codex/Screencasts)
-   [Themes](http://omeka.org/codex/Managing_Themes_2.0)
-   [Appearance](http://omeka.org/codex/Managing_Appearance_2.0)
-   [Plugins](http://omeka.org/codex/Plugins2.0)

</div>

<div class="portlet">

Page View
---------

-   <div id="nav-page">

    </div>

    [Page](Theme_Configuration.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Theme_Configuration&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Theme_Configuration&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Theme_Configuration&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Theme_Configuration.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Theme_Configuration.html)
-   <div id="t-specialpages">

    </div>

    [Special pages](http://omeka.org/codex/Special:SpecialPages)

</div>

[![Creative Commons
License](https://i.creativecommons.org/l/by/3.0/us/88x31.png)](http://creativecommons.org/licenses/by/3.0/us/)\
Omeka Documentation is licensed under a [Creative Commons Attribution
3.0 United States
License](http://creativecommons.org/licenses/by/3.0/us/).

</div>

</div>

</div>

<div id="footer">

<div class="padding">

<div id="sitemap">

<div class="section">

### About

-   [Project](../index.html%3Fp=2.html)
-   [Staff](../index.html%3Fp=3.html)
-   [News](../blog.1.html)
-   [License](http://www.gnu.org/copyleft/gpl.html)

</div>

<div class="section">

### Help

-   [User Forums](../forums/topic/mysqli-stmt.bind-result.html)
-   [Documentation](http://omeka.org/codex/)
-   [Dev Listserv](http://groups.google.com/group/omeka-dev)
-   [Contact](http://omeka.org/contact/)

</div>

<div class="section">

### Downloads

-   [Download Omeka](../download.1.html)
-   [Plugins](../plugins.html)
-   [Themes](../download/themes/index.html)
-   [Packages](../index.html%3Fp=222.html)

</div>

</div>

<div id="chnm-meta">

<span id="chnm-logo">[![Roy Rosenzweig Center for History and New
Media](http://omeka.org/ui/i/rrchnm-logo-regular.gif)](http://chnm.gmu.edu)</span>
Omeka is a project of the [Roy Rosenzweig Center for History and New
Media](http://chnm.gmu.edu), [George Mason
University](http://www.gmu.edu). Copyright © 2007–2016 CHNM.

</div>

</div>

</div>

</div>
