<div id="wrap">

[Skip Navigation](Release_Notes_for_1.5.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%201.5)

</div>

Release Notes for 1.5
=====================

<div id="primary">

Omeka 1.5 was released on February 7, 2012.

<span id="New_Features" class="mw-headline"> New Features </span>
-----------------------------------------------------------------

-   **Internationalization:** Users can now [choose a
    language](http://omeka.org/codex/Configuring_Language "Configuring Language")
    and locale to display the interface in. This affects the displayed
    text and formatting of other data like system-generated dates.
-   **Media Extension Awareness:** File extensions are now used as a
    fallback to determine how files should be displayed if the MIME type
    is incorrect or not detected.
-   **File Ordering:** Users can now reorder files within an item
    without re-uploading.

<span id="Bug_Fixes" class="mw-headline"> Bug Fixes </span>
-----------------------------------------------------------

-   Files form doesn't automatically print extra element sets
    ([\#34](https://github.com/omeka/Omeka/issues/34))
-   Item Type controller shows a "has encountered an error" page instead
    of a flash error ([\#70](https://github.com/omeka/Omeka/issues/70))
-   "Uninstall" button is enabled for plugins that need to be upgraded
    ([\#82](https://github.com/omeka/Omeka/issues/82))
-   "Add User" form lets you pick Active/Inactive
    ([\#89](https://github.com/omeka/Omeka/issues/89))
-   Retry when HTTP errors occur for S3
    ([\#94](https://github.com/omeka/Omeka/issues/94))
-   Certain fields for collections should allow null
    ([\#95](https://github.com/omeka/Omeka/issues/95))
-   Incorrect URL building in collections/index/page/n
    ([\#96](https://github.com/omeka/Omeka/issues/96))
-   has\_permission always returns false if you're not logged in
    ([\#99](https://github.com/omeka/Omeka/issues/99))
-   New item types with duplicate names override the original
    description ([\#125](https://github.com/omeka/Omeka/issues/125))

<span id="Changes" class="mw-headline"> Changes </span>
-------------------------------------------------------

-   The plugins page no longer warns about plugins that haven't been
    tested up to the current Omeka version.
-   Early errors that occur when starting Omeka are now logged to the
    PHP log.

<span id="For_Developers" class="mw-headline"> For Developers </span>
---------------------------------------------------------------------

-   The new Omeka\_Plugin\_Abstract class gives developers an optional
    framework to simplify class-based plugins.
-   Plugin-added element sets can apply to specific record types.

### <span id="Library_Upgrades" class="mw-headline"> Library Upgrades </span>

-   Zend Framework 1.11.11
-   jQuery 1.7.1
-   jQuery UI 1.8.16
-   TinyMCE 3.4.7-jQuery

### <span id="New_Functions" class="mw-headline"> New Functions </span>

-   [\_\_()](http://omeka.org/c/index.php?title=Functions/&action=edit&redlink=1 "Functions/ (page does not exist)")
    (Translation function)
-   [add\_translation\_source()](http://omeka.org/c/index.php?title=Functions/add_translation_source&action=edit&redlink=1 "Functions/add translation source (page does not exist)")
-   [get\_html\_lang()](http://omeka.org/c/index.php?title=Functions/get_html_lang&action=edit&redlink=1 "Functions/get html lang (page does not exist)")
-   [format\_date()](http://omeka.org/c/index.php?title=Functions/format_date&action=edit&redlink=1 "Functions/format date (page does not exist)")
-   [queue\_js\_string()](Functions/queue_js_string.html "Functions/queue js string")
-   [queue\_css\_string()](Functions/queue_css_string.html "Functions/queue css string")

### <span id="New_Hooks" class="mw-headline"> New Hooks </span>

-   [admin\_append\_to\_files\_show](http://omeka.org/c/index.php?title=Hooks/admin_append_to_files_show&action=edit&redlink=1 "Hooks/admin append to files show (page does not exist)")

### <span id="New_Filters" class="mw-headline"> New Filters </span>

-   [display\_file](http://omeka.org/c/index.php?title=Filters/display_file&action=edit&redlink=1 "Filters/display file (page does not exist)")

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_1.5](Release_Notes_for_1.5.html)"

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

    [Page](Release_Notes_for_1.5.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_1.5&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_1.5&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_1.5&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_1.5.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_1.5.html)
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
