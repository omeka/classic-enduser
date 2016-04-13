<div id="wrap">

[Skip Navigation](Release_Notes_for_1.4.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%201.4)

</div>

Release Notes for 1.4
=====================

<div id="primary">

Omeka 1.4 was released on June 22, 2011.

<span id="General" class="mw-headline"> General </span>
-------------------------------------------------------

-   Batch editing for items
-   Improved update and installation scripts
-   Improved error handling and logging
-   Improved upload file handling
-   Allows configuration of tag delimiter
-   Improvements to database date and time formatting
-   Improvements to advanced search
    -   New "is exactly" advanced search type
    -   Fixed "is null" and "does not contain" search types
-   Atom feed output
    -   Next, previous, last, and first links
-   Improved user and access control handling
-   Miscellaneous tweaks and bedazzlings

<span id="Library_Updates" class="mw-headline"> Library Updates </span>
-----------------------------------------------------------------------

-   Updated Zend Framework to 1.11.6
-   Updated jQuery to 1.6.1
-   Updated jQuery UI to 1.8.13
-   Updated TinyMCE to 3.4.2-jQuery

<span id="Security" class="mw-headline"> Security </span>
---------------------------------------------------------

-   Cross Site Scripting and AJAX vulnerabilities addressed
-   CSRF protection for delete actions

<span id="UI.2FUX" class="mw-headline"> UI/UX </span>
-----------------------------------------------------

-   Improvements to admin theme
-   Many improvements and fixes to media helpers, esp. for display of
    AVI, WMV, WMA
-   Improvements to theme configuration
    -   TinyMCE integration
    -   Image preview
-   Improved item citation style
-   Modal AJAX for delete/confirm

<span id="For_Developers" class="mw-headline"> For Developers </span>
---------------------------------------------------------------------

-   Omeka\_Job component for background jobs (e.g., importing)
-   Omeka\_Storage Layer
    -   Amazon S3 storage
-   New functions
    -   [plugin\_is\_active](http://omeka.org/c/index.php?title=Functions/plugin_is_active&action=edit&redlink=1 "Functions/plugin is active (page does not exist)")
    -   [link\_to\_items\_atom](http://omeka.org/c/index.php?title=Functions/link_to_items_atom&action=edit&redlink=1 "Functions/link to items atom (page does not exist)")
    -   [clear\_filters](http://omeka.org/c/index.php?title=Functions/clear_filters&action=edit&redlink=1 "Functions/clear filters (page does not exist)")
    -   [body\_tag](http://omeka.org/c/index.php?title=Functions/body_tag&action=edit&redlink=1 "Functions/body tag (page does not exist)")
    -   [auto\_discovery\_link\_tags](http://omeka.org/c/index.php?title=Functions/auto_discovery_link_tags&action=edit&redlink=1 "Functions/auto discovery link tags (page does not exist)")
    -   [\_log](http://omeka.org/c/index.php?title=Functions/_log&action=edit&redlink=1 "Functions/ log (page does not exist)")
    -   [random\_featured\_items](http://omeka.org/c/index.php?title=Functions/random_featured_items&action=edit&redlink=1 "Functions/random featured items (page does not exist)")
    -   [plugin\_body](http://omeka.org/c/index.php?title=Functions/plugin_body&action=edit&redlink=1 "Functions/plugin body (page does not exist)")
    -   [plugin\_page\_header](http://omeka.org/c/index.php?title=Functions/plugin_page_header&action=edit&redlink=1 "Functions/plugin page header (page does not exist)")
    -   [plugin\_page\_content](http://omeka.org/c/index.php?title=Functions/plugin_page_content&action=edit&redlink=1 "Functions/plugin page content (page does not exist)")
    -   [url\_to\_link](http://omeka.org/c/index.php?title=Functions/url_to_link&action=edit&redlink=1 "Functions/url to link (page does not exist)")
-   New filters
    -   [item\_citation
        filter](Filters/item_citation.html "Filters/item citation")
-   New global functions
-   Deprecated functions
    -   [auto\_discovery\_link\_tag](Functions/auto_discovery_link_tag.html "Functions/auto discovery link tag")

<span id="Tests" class="mw-headline"> Tests </span>
---------------------------------------------------

-   Tests now require PHPUnit 3.5 or newer
-   Fakemail no longer required for testing
-   Added test suites:
    -   All

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_1.4](Release_Notes_for_1.4.html)"

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

    [Page](Release_Notes_for_1.4.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_1.4&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_1.4&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_1.4&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_1.4.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_1.4.html)
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
