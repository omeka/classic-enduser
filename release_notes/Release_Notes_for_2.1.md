<div id="wrap">

[Skip Navigation](Release_Notes_for_2.1.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%202.1)

</div>

Release Notes for 2.1
=====================

<div id="primary">

Omeka 2.1 was released on August 27, 2013.

**Note:** Due to an update to Zend Framework's requirements, Omeka 2.1
officially requires PHP version 5.2.11 or higher.

<span id="New_Features" class="mw-headline"> New Features </span>
-----------------------------------------------------------------

-   REST API
    -   GET, PUT, POST, and DELETE methods implemented for items,
        collections, files, item types, elements, and element sets.
    -   GET method available for users and tags.
    -   DELETE method available for tags.

<span id="Enhancements" class="mw-headline"> Enhancements </span>
-----------------------------------------------------------------

-   Keyword search for users
    (*[\#59](https://github.com/omeka/Omeka/issues/59)*)
-   Direct links to plugin support\_link sites
    (*[\#258](https://github.com/omeka/Omeka/issues/258)*)
-   Direct links to files from files/show
    (*[\#542](https://github.com/omeka/Omeka/issues/542)*)
-   `record_url()` now accepts query string parameters
    (*[\#549](https://github.com/omeka/Omeka/issues/549)*)
-   Added methods for on-the-fly changes to storage adapters
    (*[\#550](https://github.com/omeka/Omeka/issues/550)*)
-   Show tags for non-Item records in tags browse
    (*[\#568](https://github.com/omeka/Omeka/issues/568)*)
-   New `get_record()` helper for getting single records
    (*[\#591](https://github.com/omeka/Omeka/pull/591), contributed by
    Jeremy Boggs*)
-   View object now automatically available for background processes
    (*[\#593](https://github.com/omeka/Omeka/issues/593)*)

<span id="Bugs_Fixed" class="mw-headline"> Bugs Fixed </span>
-------------------------------------------------------------

-   Plugin versions were stored as type 'text'
    (*[\#492](https://github.com/omeka/Omeka/issues/492)*)
-   Too many plugins could make the bottom of the admin navigation
    unreachable (*[\#519](https://github.com/omeka/Omeka/issues/519)*)
-   Styling on admin files/show was overly restrictive for some content
    (*[\#555](https://github.com/omeka/Omeka/issues/555)*)
-   "does not contain" items advanced search was acting like "contains"
    (*[\#588](https://github.com/omeka/Omeka/issues/588)*)
-   Items advanced search was incorrectly excluding some results

<span id="Plugin_API" class="mw-headline"> Plugin API </span>
-------------------------------------------------------------

-   New 'activate' and 'deactivate' plugin hooks
    (*[\#349](https://github.com/omeka/Omeka/issues/349)*)
-   New 'admin\_collections\_show\_sidebar' hook
    (*[\#520](https://github.com/omeka/Omeka/issues/520)*)

<span id="Localization" class="mw-headline"> Localization </span>
-----------------------------------------------------------------

-   Strings to translate updated
-   All languages updated

<span id="Updated_Libraries" class="mw-headline"> Updated Libraries </span>
---------------------------------------------------------------------------

-   Zend Framework 1.12.3
-   getID3 1.9.6
-   pheanstalk 2.1.0
-   HTMLPurifier 4.5.0
-   jQuery 1.10.1
-   jQuery UI 1.10.3

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_2.1](Release_Notes_for_2.1.html)"

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

    [Page](Release_Notes_for_2.1.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_2.1&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_2.1&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_2.1&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_2.1.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_2.1.html)
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
