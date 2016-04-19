<div id="wrap">

[Skip Navigation](Release_Notes_for_2.3.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%202.3)

</div>

Release Notes for 2.3
=====================

<div id="primary">

Omeka 2.3 was released on March 19, 2015.

<span id="Enhancements" class="mw-headline"> Enhancements </span>
-----------------------------------------------------------------

-   Accessibility improvements (added ARIA roles and landmarks, improved
    labels, navigation skip links)
-   New file derivative strategy using PHP's GD extension
-   Built-in support for setting default sort orders for browse pages
-   Element dropdowns on item advanced search respect the
    admin-configured element sorting order
    ([\#643](https://github.com/omeka/Omeka/issues/643))
-   The admin-configured page limits for browse pages are used for more
    controllers, including plugins
-   The listing of items on collection pages now follows the admin page
    limits ([\#601](https://github.com/omeka/Omeka/issues/601))
-   Support for the new access control directives used by Apache 2.4
    ([\#631](https://github.com/omeka/Omeka/issues/631))
-   URLs within the default citation output now include a span wrapper
    to allow specific styling
-   New interface for resetting customized navigation to default
    settings
-   Improved error output for exceptions
-   Detailed error messages are now always shown for exceptions during
    upgrade
-   Support for newer versions (4.2+) of PHPUnit
-   The API now accepts `sort_field` and `sort_dir` GET parameters for
    sorting results
-   Omeka will hide the "Path to ImageMagick" setting when an
    alternative derivative strategy is in use
-   The System Information panel now uses internal "folder" names for
    both themes and plugins
-   Improved translation coverage
    ([\#655](https://github.com/omeka/Omeka/pull/655),
    [\#659](https://github.com/omeka/Omeka/issues/659))

<span id="Bugs_Fixed" class="mw-headline"> Bugs Fixed </span>
-------------------------------------------------------------

-   Tags were incorrectly treated as case-sensitive in some places
-   Assigning tags to records caused an SQL error for some newer MySQL
    servers
-   The item advanced search "does not contain" worked incorrectly with
    elements having multiple texts
-   API authentication did not work properly on installations with no
    database prefix
-   `browse_sort_links` for "bare" links handled attributes incorrectly
    ([\#648](https://github.com/omeka/Omeka/issues/648))
-   Setting a custom homepage including a query string would silently
    set that query on all pages
-   Upgrades could fail on some "strict mode" MySQL configurations
-   Upgrades directly from old 1.x versions could fail when migrating
    collections
-   Theme overrides of plugin views did not apply when on a different
    plugin's page ([\#635](https://github.com/omeka/Omeka/issues/635))
-   The display of item search filters did not always recognize when
    users filtered by tag
-   Automatic `alt` attributes for file display were over-escaped
-   Admin-side page titles on hover were over-escaped
-   Long titles for records indexed for the sitewide search could be
    silently truncated or cause an error
-   The sitewide search form did not respect the documented
    `submit_value` option
-   Errors on individual items could cause the "Index Records" job to
    fail
-   Item Types did not properly clean up after themselves after they
    were deleted

<span id="Localization" class="mw-headline"> Localization </span>
-----------------------------------------------------------------

-   The Norwegian (no) translation has been moved to Norwegian
    Bokmål (nb).
-   New translations for Bulgarian (bg\_BG), Korean (ko\_KR).
-   Updates to many existing translations

<span id="External_Libraries" class="mw-headline"> External Libraries </span>
-----------------------------------------------------------------------------

Omeka 2.3 updates to the following versions of its external
dependencies:

-   Zend Framework 1.12.11
-   jQuery 1.11.2
-   jQuery UI 1.11.2
-   TinyMCE 3.5.11

<span id="Bundled_Add-ons" class="mw-headline"> Bundled Add-ons </span>
-----------------------------------------------------------------------

### <span id="Plugins" class="mw-headline"> Plugins </span>

-   Exhibit Builder 3.2
-   Simple Pages 3.0.5

### <span id="Themes" class="mw-headline"> Themes </span>

-   Thanks, Roy 2.3
-   Seasons 2.3
-   Berlin 2.3

<span id="For_Developers" class="mw-headline"> For Developers </span>
---------------------------------------------------------------------

For change information geared toward developers, see [What's New in
Omeka 2.3](http://omeka.readthedocs.org/en/latest/whatsnew/2.3.html) on
Omeka's Read the Docs site.

<span id="Acknowledgements" class="mw-headline"> Acknowledgements </span>
-------------------------------------------------------------------------

The following members of the Omeka community contributed code, fixes,
and improvements to Omeka 2.3:

-   Erin Bell ([PR \#636](https://github.com/omeka/Omeka/pull/636))
-   Daniel Berthereau ([PR
    \#640](https://github.com/omeka/Omeka/pull/640), [PR
    \#647](https://github.com/omeka/Omeka/pull/647), [PR
    \#650](https://github.com/omeka/Omeka/pull/650), [PR
    \#652](https://github.com/omeka/Omeka/pull/652), [PR
    \#653](https://github.com/omeka/Omeka/pull/653))
-   Adam Doan ([PR \#629](https://github.com/omeka/Omeka/pull/629))
-   Wayne Graham ([PR \#630](https://github.com/omeka/Omeka/pull/630))
-   Anna Michelle ([PR \#651](https://github.com/omeka/Omeka/pull/651))
-   Michał Seweryniak ([PR
    \#655](https://github.com/omeka/Omeka/pull/655))

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_2.3](Release_Notes_for_2.3.html)"

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

    [Page](Release_Notes_for_2.3.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_2.3&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_2.3&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_2.3&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_2.3.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_2.3.html)
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
