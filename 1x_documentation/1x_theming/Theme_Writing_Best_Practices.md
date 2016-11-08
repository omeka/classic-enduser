<div id="wrap">

[Skip Navigation](Theme_Writing_Best_Practices.html#content)
<div id="header">

<div class="padding">

<span
id="logo">[![Omeka](http://omeka.org/ui/i/logo-horizontal-288px.gif)](../index.html)</span>
<div id="search-form">

</div>

-   <div id="nav-showcase">

    </div>

    [Showcase](../showcase.1.html)
-   <div id="nav-involved">

    </div>

    [Get Involved](../index.html%3Fp=124.html)
-   <div id="nav-addons">

    </div>

    [Add-Ons](../add-ons.1.html)
-   <div id="nav-forums">

    </div>

    [Forums](../forums/topic/mysqli-stmt.bind-result.html)
-   <div id="nav-documentation">

    </div>

    [Documentation](http://omeka.org/codex/)
-   <div id="nav-download">

    </div>

    [Download](../download.1.html)

</div>

</div>

<div id="content">

<div class="padding">

<div id="user-meta">

-   <div id="pt-login">

    </div>

    [Log
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20Writing%20Best%20Practices)

</div>

Theme Writing Best Practices
============================

<div id="primary">

<span id="Naming_Your_Theme" class="mw-headline"> Naming Your Theme </span>
---------------------------------------------------------------------------

The folder name of your theme is stored in the database. This means if
you later change the folder name, the theme will no longer work.

<span id="Theme_Directory_Structure" class="mw-headline"> Theme Directory Structure </span>
-------------------------------------------------------------------------------------------

As of Omeka 1.3, public themes use the following files and file
structure:

-   **my\_theme/** (folder)
    -   **items/** (folder)
        -   *browse.php*
        -   *show.php*
        -   *tags.php*
    -   **exhibits/** (folder)
        -   *browse.php*
        -   *show.php*
        -   *summary.php*
        -   *item.php*
    -   **collections/** (folder)
        -   *browse.php*
        -   *show.php*
    -   **common/** (folder)
        -   *header.php*
        -   *footer.php*
    -   **css/** (folder)
        -   *screen.css*
    -   **images/** (folder)
    -   **javascripts/** (folder)
    -   *theme.ini*
    -   *theme.jpg*
    -   *index.php*
    -   *404.php*

### <span id="1.2.1_and_Earlier" class="mw-headline"> 1.2.1 and Earlier </span>

Themes in Omeka 1.2.1 and earlier require, at minimum, the following
structure:

-   /collections
    -   browse.php
    -   show.php
-   /common
    -   header.php
    -   footer.php
-   /css
    -   screen.css
-   index.php
-   /items
    -   browse.php
    -   show.php
    -   tags.php
-   theme.ini
-   theme.jpg

<span id="Template_Files" class="mw-headline"> Template Files </span>
---------------------------------------------------------------------

### <span id="1.3_and_Later" class="mw-headline"> 1.3 and Later </span>

As of version 1.3, Omeka includes templates for each public view for
themes in the core. This means public themes do not have to include all
the template files themselves; Instead, themes can omit files, and rely
instead on the core template files. If, however, theme developers wish
to override the core template files, they can simply add that template
file to their custom theme, and Omeka will use the theme file instead of
the one from the core.

Themes can also now optionally include extra views to customize pages
created by plugins. See [Theming Plugin
Pages](Theming_Plugin_Pages.html "Theming Plugin Pages") for more
information.

\

<span id="Theme.ini" class="mw-headline"> Theme.ini</span>
----------------------------------------------------------

The theme.ini is a required file that provides information about your
theme to Omeka. Filling this out should be the second step in creating a
theme so you can easily identify it in the list of available themes in
the administrative interface. Below is an example of the correct
formatting for the .ini file.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="ini source-ini">

``` {.de1}
[theme]
author = "Jeremy Boggs"
title = "Thanks, Roy"
description = "A tribute to Roy Rosenzweig."
license = "GPL"
website = "thanksroy.org"
```

</div>

</div>

Note that all values should be wrapped in quotation marks.

Upcoming versions of Omeka will switch to using omeka\_target\_version
instead of omeka\_tested\_up\_to, and will include a new support\_link.
These changes are part of the mechanism to let you add our themes to our
listing at omeka.org/add-ons/themes.

<span id="Common_Directory" class="mw-headline"> Common Directory </span>
-------------------------------------------------------------------------

The 'common' directory can contain any partial files you'd like to
include in other parts of your theme, such as header.php or footer.php.
While the header and footer files have special theme functions to
include them ([head](Functions/head.html "Functions/head") and
[foot](Functions/foot.html "Functions/foot"), respectively), you can
include any other file in the 'common' directory using the
[common](Functions/common.html "Functions/common") theme function.

### <span id="Header" class="mw-headline"> Header </span>

The header file, at 'common/header.php', is a global file that can be
called on any other page by using the function
[head](Theme_API/head.html "Theme API/head"). It should contain at a
minimum all of the markup you would place in the `<head>` tags of an
html page, such as doctype, stylesheets, javascripts, stylesheets,
etc.It is recommended you include
[plugin\_header](Theme_API/plugin_header.html "Theme API/plugin header")
in the `<head>` so users will be able to take advantage of omeka's
plugin extensibility. To fully take advantage of this file it is
recommended opening the `<body>` tag and placing any other elements you
would like to appear on all pages of your theme, such as title, logo,
and primary navigation. Navigation can be generated with
[public\_nav\_main](Theme_API/public_nav_main.html "Theme API/public nav main").
You could also include search functionality here by using
[simple\_search](Theme_API/simple_search.html "Theme API/simple search")
and/or
[link\_to\_advanced\_search](Theme_API/link_to_advanced_search.html "Theme API/link to advanced search").

### <span id="Footer" class="mw-headline"> Footer </span>

Filling out the footer.php file now will allow you to start with
webpages that validates from the start. Close any tags you opened in the
header, such as `<body>` or perhaps `<div id="content">`. It is again
recommended you include
[plugin\_footer](http://omeka.org/c/index.php?title=Theme_API/plugin_footer&action=edit&redlink=1 "Theme API/plugin footer (page does not exist)").
This file will be pulled in anywhere
[foot](Theme_API/foot.html "Theme API/foot") is called.

<span id="Building_the_Homepage" class="mw-headline"> Building the Homepage</span>
----------------------------------------------------------------------------------

The homepage for your theme is generated by the 'index.php' at the root
of your theme. If you have decided to use the header and footer files,
you should include [head](Theme_API/head.html "Theme API/head") at the
very top and [foot](Theme_API/foot.html "Theme API/foot") at the very
bottom of the page.

Here you can use functions such as
[display\_random\_featured\_item](Functions/display_random_featured_item.html "Functions/display random featured item")
or
[display\_random\_featured\_collection](Functions/display_random_featured_collection.html "Functions/display random featured collection")
or the [code snippet to display recently
added](Functions/recent_items.html "Functions/recent items") items to
pull content from your database.

<span id="The_Items_Directory" class="mw-headline"> The Items Directory </span>
-------------------------------------------------------------------------------

### <span id="items.2Fbrowse" class="mw-headline"> items/browse </span>

The 'items/browse' view uses the file 'items/browse.php'. This page
displays a list of all public items in the database. You have the option
to include navigation to view a list of items or a list of all item tags
by using the [nav](Theme_API/nav.html "Theme API/nav") function.

It is recommended you include
[pagination\_links](Theme_API/pagination_links.html "Theme API/pagination links")
somewhere on the browse page, to allow users to page through all of the
items in the list.

Again, see the page about looping items for more information on how
multiple items are displayed.

You can also use more advanced functions here to list items by
collection, type, specific tags.

It is also recommended you include
[plugin\_append\_to\_items\_browse\_each](http://omeka.org/c/index.php?title=Functions/plugin_append_to_items_browse_each&action=edit&redlink=1 "Functions/plugin append to items browse each (page does not exist)")
and
[plugin\_append\_to\_items\_browse](http://omeka.org/c/index.php?title=Functions/plugin_append_to_items_browse&action=edit&redlink=1 "Functions/plugin append to items browse (page does not exist)"),
so plugins that use these hooks can append content to the items/browse
page.

### <span id="items.2Fshow" class="mw-headline"> items/show </span>

The 'items/show' view uses the file 'items/show.php'. This page utilizes
the [item](Theme_API/item.html "Theme API/item"). Explain its use with
title as example to show use as function or with variable.

If you want to simply return all the element set metadata for an item
you should use
[show\_item\_metadata](Theme_API/show_item_metadata.html "Theme API/show item metadata").
If you want to have more control over which elements are returned on
this page refer to the [item](Theme_API/item.html "Theme API/item")
theme helper.

You can also include related files, collections, tags, and citations
using the following functions

-   [display\_files\_for\_item](Theme_API/display_files_for_item.html "Theme API/display files for item")
-   [link\_to\_collection\_for\_item](http://omeka.org/codex/Theme_API/link_to_collection_for_item "Theme API/link to collection for item")
-   [item\_tags\_as\_string](Theme_API/item_tags_as_string.html "Theme API/item tags as string")
-   [item\_citation](Theme_API/item_citation.html "Theme API/item citation")

We also recommended including
[plugin\_append\_to\_items\_show](http://omeka.org/c/index.php?title=Theme_API/plugin_append_to_items_show&action=edit&redlink=1 "Theme API/plugin append to items show (page does not exist)")
so plugins can append information to the items/show page.

### <span id="items.2Ftags" class="mw-headline"> items/tags </span>

The 'items/tags' view uses the file 'items/tags.php'. This page can be
used to display all of the tags in a cloud formation by using
[tag\_cloud](Theme_API/tag_cloud.html "Theme API/tag cloud").

<span id="Theme_Configuration" class="mw-headline"> Theme Configuration </span>
-------------------------------------------------------------------------------

As of Omeka 1.2, theme developers can now add configuration options to
their themes, which allows users to set theme options from the admin
panel. If a configuration form is available for a theme, a "Configure"
button will appear for the active public theme.

See [Theme
Configuration](Theme_Configuration.html "Theme Configuration") for
details on adding admin configuration to your theme.

<span id="Finishing_Up" class="mw-headline"> Finishing Up </span>
-----------------------------------------------------------------

Take a screenshot of your beautiful new theme! Resize it to 190px x
140px and save it as theme.jpg. Put this in the theme directory.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Theme\_Writing\_Best\_Practices](Theme_Writing_Best_Practices.html)"

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

    [Page](Theme_Writing_Best_Practices.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Theme_Writing_Best_Practices&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Theme_Writing_Best_Practices&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Theme_Writing_Best_Practices&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](Special:WhatLinksHere/Theme_Writing_Best_Practices.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Theme_Writing_Best_Practices.html)
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
