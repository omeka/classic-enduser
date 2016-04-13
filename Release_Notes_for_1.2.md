<div id="wrap">

[Skip Navigation](Release_Notes_for_1.2.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%201.2)

</div>

Release Notes for 1.2
=====================

<div id="primary">

Omeka 1.2 was released on April 8, 2010.

<span id="Core_Changes" class="mw-headline"> Core Changes </span>
-----------------------------------------------------------------

-   Adds theme configuration capabilities on a per-theme basis. Theme
    writers can now add configuration options to their themes, which can
    be changed by Omeka users from admin.
    -   Such configurations include switching CSS-style sheets and
        adding a logo to the theme's header.
-   Adds two new configurable themes to the pre-packaged group of
    themes: Seasons and Rhythm.
    -   Rhythm offers three style sheets for different color palettes.
        Seasons offers four style sheets and option for uploading a
        logo file.
-   Adds security setting to enable/disable checking a file MIME type by
    looking at the file header.
-   Updates the omeka-xml output to use version 3 of the schema.
-   Adds a commented-out RewriteBase rule to various .htaccess files
    in Omeka.

<span id="Admin_Theme_Changes" class="mw-headline"> Admin Theme Changes </span>
-------------------------------------------------------------------------------

-   Adds button for configuring themes, if they have a
    configuration form.
-   Add styles to resize img and object elements to prevent overflowing
    in admin; Updates files/show.php and items/show.php to use the
    fullsize image when available.
-   Updates the Item Type edit form, to make adding elements to an Item
    Type more user friendly.
-   Fixes bug where form errors were not displaying correctly.
-   Adds cautionary text in confirm boxes for delete item, delete
    element set, delete item type, delete collection, delete user, and
    remove element from item type.

<span id="API_Changes" class="mw-headline"> API Changes </span>
---------------------------------------------------------------

-   Adds
    [get\_theme\_option](Theme_API/get_theme_option.html "Theme API/get theme option")
    helper to retrieve current theme options set in the admin.
-   Updates image helpers for images so that they use the 'alt' option
    first, then the description in the file metadata, then the title in
    the file metadata, and finally, if these are unavailable, the
    item title.
-   Fixes get\_collections() helper to allow returning collections that
    are both public and featured.
-   Deprecates form helpers in favor of Zend Form methods. The following
    helpers can still be used, but will be removed in a future release:
    -   label()
    -   textarea()
    -   input()
    -   select()

<span id="Miscellaneous" class="mw-headline"> Miscellaneous </span>
-------------------------------------------------------------------

-   Update Zend to version 1.9.7.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_1.2](Release_Notes_for_1.2.html)"

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

    [Page](Release_Notes_for_1.2.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_1.2&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_1.2&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_1.2&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_1.2.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_1.2.html)
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
