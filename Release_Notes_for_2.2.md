<div id="wrap">

[Skip Navigation](Release_Notes_for_2.2.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%202.2)

</div>

Release Notes for 2.2
=====================

<div id="primary">

Omeka 2.2 was released on July 2, 2014.

<span id="New_Features" class="mw-headline"> New Features </span>
-----------------------------------------------------------------

### <span id="Shortcodes" class="mw-headline"> Shortcodes </span>

-   Omeka now supports
    [shortcodes](http://omeka.org/codex/Shortcodes "Shortcodes") for
    embedding content such as a list of recent or featured items, as
    well as plugin content, such as a map from the Geolocation plugin.
-   The new Simple Pages plugin bundled with Omeka supports shortcodes
    in the page text.

### <span id="Derivative_Images" class="mw-headline"> Derivative Images </span>

-   Configurable and extensible derivative image (thumbnail) creation
-   Blacklisting and whitelisting image creation by MIME type in
    config.ini
-   Support for using `ext/imagick` instead of command-line ImageMagick
-   The default ImageMagick derivative creator no longer separately
    tries to run `identify`; this can double thumbnail creation speed
    for some files

### <span id="Representative_Files_for_Records" class="mw-headline"> Representative Files for Records </span>

-   Any record type can return a "representative" file Omeka can use for
    displaying thumbnails
-   Collections and Exhibits select a representative image for
    themselves and so will show thumbnails on the front page, their
    browse pages, and in shortcodes
-   Items, Files, Collections, Exhibits, and any other records with
    representative images will show thumbnails on sitewide search
    results

### <span id="Appearance" class="mw-headline"> Appearance </span>

-   Admins can hide the header listing the element set ("Dublin Core")
    on item/collection/file pages through Appearance Settings
-   Additional fallback thumbnail icons for audio, video, and image
    types
-   Sorting links on the default public collections browse view
-   Common "single.php" themeable display for Items, Collections, and
    Exhibits used in recent and featured sections and shortcodes
-   Dev-editable button text for items-specific search

### <span id="Admin_Interface" class="mw-headline"> Admin Interface </span>

-   New interface for manually resending the user activation email
    message to a user.
-   The user edit page is split among three subpages and more closely
    follows the admin style
-   The Item-specific advanced search page more closely follows the
    admin style
-   The File edit page has tabs for each element set and filter-added
    section, like the Item and Collection add/edit pages
-   The dropdown for selecting a Collection for an item is sorted
    alphabetically by collection title
-   HTML edit boxes for metadata will automatically grow with the text
    input

### <span id="Security" class="mw-headline"> Security </span>

-   Admins can now specify more Allowed HTML Elements, such as `iframe`
-   Ability to enable or disable element filtering for the API

### <span id="Other" class="mw-headline"> Other </span>

-   Username restrictions greatly relaxed to allow email addresses as
    usernames
-   Theme configuration can now be divided into named sections
-   Accessibility improvements throughout the admin and public themes
-   jQuery and jQuery UI now automatically fall back to local copies if
    the CDN copy can't be loaded
-   All records can be sorted randomly
-   Search term input on "Narrow by Specific Fields" disables for "is
    empty" and "is not empty" types
-   Files can be internally filtered by original filename
    (*[\#616](https://github.com/omeka/Omeka/pull/616), thanks to Daniel
    Berthereau*)
-   Simple "OR" searches on records by providing an array of values
    (*[\#622](https://github.com/omeka/Omeka/pull/622), thanks to Daniel
    Berthereau*)

<span id="Bugs_Fixed" class="mw-headline"> Bugs Fixed </span>
-------------------------------------------------------------

-   MIME types could be incorrectly set for multiple files uploaded
    simultaneously
-   HTML in titles shown incorrectly on batch-edit
-   Invalid XML characters could break omeka-xml and omeka-json output
    (*[\#617](https://github.com/omeka/Omeka/pull/617), thanks to Rachel
    Donahue*)
-   Emails sent by Omeka did not support non-Latin characters
    (*[\#618](https://github.com/omeka/Omeka/pull/618), thanks to Marios
    Bekatoros*)
-   Element names were not localized on items/browse listing of filters
    (*[\#620](https://github.com/omeka/Omeka/issues/620), thanks to
    Matti Lassila*)
-   On the item-specific advanced search, "does not contain" did not
    include items that completely omitted the element
    (*[\#621](https://github.com/omeka/Omeka/pull/621), thanks to Daniel
    Berthereau*)

<span id="Localization" class="mw-headline"> Localization </span>
-----------------------------------------------------------------

-   todo

<span id="Add-ons" class="mw-headline"> Add-ons </span>
-------------------------------------------------------

### <span id="Bundled_Plugins" class="mw-headline"> Bundled Plugins </span>

-   Exhibit Builder 3.1
-   Simple Pages 3.0

### <span id="Bundled_Themes" class="mw-headline"> Bundled Themes </span>

-   Thanks, Roy 2.2
-   Seasons 2.2
-   Berlin 2.2

### <span id="Incompatibilities" class="mw-headline"> Incompatibilities </span>

A small number of plugins need to be upgraded to work with version 2.2:

-   [Derivative Images](../add-ons/plugins/derivative-images.1.html)
    must be upgraded to version 2.0
-   [Item Order](../add-ons/plugins/item-order.1.html) must be upgraded
    to version 2.0.1

<span id="For_Developers" class="mw-headline"> For Developers </span>
---------------------------------------------------------------------

For release information aimed at developers, see [What's new in Omeka
2.2](http://omeka.readthedocs.org/en/latest/whatsnew/2.2.html) in the
developer documentation.

### <span id="Library_Updates" class="mw-headline"> Library Updates </span>

-   Zend Framework 1.12.7
-   HTML Purifier 4.6.0
-   jQuery 1.11.1
-   jQuery UI 1.10.4
-   TinyMCE 3.5.10 (jQuery version)

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_2.2](Release_Notes_for_2.2.html)"

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

    [Page](Release_Notes_for_2.2.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_2.2&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_2.2&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_2.2&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_2.2.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_2.2.html)
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
