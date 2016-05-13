Release Notes for 2.3.1
=======================


Omeka 2.3.1 is the first maintenance release for version 2.3. It was released on August 27, 2015.

<span id="Enhancements" class="mw-headline"> Enhancements </span>
-----------------------------------------------------------------

-   It is now possible to view tags assigned to zero records in the
    admin interface for tags
-   The item shortcodes now allow filtering by item type
    ([\#668](https://github.com/omeka/Omeka/issues/668)).
-   Invalid strings are now handled more gracefully when using PHP 5.4
    or newer
-   The full set of available filters for Items are now available for
    use in the API
-   The ExternalImageMagick and Imagick file derivative strategies now
    have a `autoOrient` option to automatically fix the orientation of
    images that have an embedded orientation flag.

<span id="Bugs_Fixed" class="mw-headline"> Bugs Fixed </span>
-------------------------------------------------------------

-   An error occurred when adding tags differing only in trailing spaces
-   Sessions containing invalid UTF-8 text data could be dropped or
    truncated
-   Invalid element text records could cause nonsensical API output
-   Element texts could be duplicated if a record was saved more than
    once in a single request
-   The linkToMetadata option for file\_markup could cause a PHP notice
-   The Imagick derivative strategy handled images with layers and
    transparency improperly
-   The Mixin\_ElementText::getAllElementTextsByElement function
    introduced in 2.3 did not work correctly
    ([\#662](https://github.com/omeka/Omeka/pull/662,), fix contributed
    by Daniel Berthereau)
-   There was a typo in the admin interface
    ([\#664](https://github.com/omeka/Omeka/pull/664), fix contributed
    by Zach Ploskey)

<span id="Changes" class="mw-headline"> Changes </span>
-------------------------------------------------------

-   PHP's error reporting level is now set the same regardless of the
    "environment" setting

<span id="Localization" class="mw-headline"> Localization </span>
-----------------------------------------------------------------

-   New translation for Latvian (lv\_LV)
-   Updates for Czech (cs), Estonian (et), Italian (it), Dutch (nl\_NL),
    Polish (pl), Swedish (sv\_SE), and Turkish (tr\_TR).

<span id="Bundled_Add-ons" class="mw-headline"> Bundled Add-ons </span>
-----------------------------------------------------------------------

### <span id="Themes" class="mw-headline"> Themes </span>

-   Thanks, Roy 2.3.1 (fixed a problem with site logos not showing
    correctly on item pages)

### <span id="Plugins" class="mw-headline"> Plugins </span>

-   Exhibit Builder 3.2.1 (fixed a problem that sometimes prevented
    exhibits from being deleted, updated translations)
-   Simple Pages 3.0.6 (updated translations)

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_2.3.1](Release_Notes_for_2.3.1.html)"

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

    [Page](Release_Notes_for_2.3.1.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_2.3.1&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_2.3.1&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_2.3.1&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](Special:WhatLinksHere/Release_Notes_for_2.3.1.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_2.3.1.html)
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
