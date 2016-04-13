<div id="wrap">

[Skip Navigation](Release_Notes_for_2.0.3.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%202.0.3)

</div>

Release Notes for 2.0.3
=======================

<div id="primary">

Omeka 2.0.3 is the third maintenance release for the 2.0 series. It was
released on April 25, 2013.

<span id="Bugs_Fixed" class="mw-headline"> Bugs Fixed </span>
-------------------------------------------------------------

-   `metadata()` calls inside metadata filters broke future filters
    (*reported by Iwe Muiser*)
-   Input element text data could be lost if the HTML editor was on and
    a new element was added
    (*[\#509](https://github.com/omeka/Omeka/issues/509), reported by
    Lincoln Mullen*)
-   CSS issue with the Themes section of the admin theme in Chrome 26+
-   An Exception problem with the Navigation component
-   Timestamps in the database only used the hours of 0-12, not 13-23.
    (*reported by daniel.lind*)
-   Error pages didn't escape HTML content in the backtrace or message
    (*[\#512](https://github.com/omeka/Omeka/issues/512))*
-   Deleted collections left behind linkages to Items
    (*[\#507](https://github.com/omeka/Omeka/issues/507), reported by
    Lincoln Mullen*)
-   Searching for Items in nonexistent collections/types/etc. caused an
    error (*[\#527](https://github.com/omeka/Omeka/issues/527)*)
-   Tag hooks weren't being correctly thrown when saving Items
    (*[\#522](https://github.com/omeka/Omeka/issues/522)*)

<span id="Performance_Improvements" class="mw-headline"> Performance Improvements </span>
-----------------------------------------------------------------------------------------

-   A new, faster query is used for the Item-specific simple search
    (*[\#518](https://github.com/omeka/Omeka/issues/518))*

<span id="Localization" class="mw-headline"> Localization </span>
-----------------------------------------------------------------

-   A translation fix to the "Save Changes" button for plugin config
-   Updated translations for Catalan (Spain) (ca\_ES), Spanish (es),
    Croatian (hr), Italian (it), Japanese (ja), Flemish (nl\_BE),
    Brazilian Portuguese (pt\_BR), European Portuguese (pt\_PT).
-   New translation for Ukranian (uk).

<span id="Theme_and_Style_Improvements" class="mw-headline"> Theme and Style Improvements </span>
-------------------------------------------------------------------------------------------------

-   Updated versions of Thanks Roy, Seasons, and Berlin.
-   Added new "Night" style to Seasons.
-   Public-side pagination made consistent with admin-side

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_2.0.3](Release_Notes_for_2.0.3.html)"

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

    [Page](Release_Notes_for_2.0.3.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_2.0.3&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_2.0.3&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_2.0.3&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](Special:WhatLinksHere/Release_Notes_for_2.0.3.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_2.0.3.html)
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
