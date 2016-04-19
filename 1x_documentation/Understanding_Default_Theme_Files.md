<div id="wrap">

[Skip Navigation](Understanding_Default_Theme_Files.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Understanding%20Default%20Theme%20Files)

</div>

Understanding Default Theme Files
=================================

<div id="primary">

Many projects call for some amount of seasoning your public display to
taste. Maybe you need to display an additional piece of metadata on the
item browse pages, or you want to make a minor rearrangement to the
content.

The natural first step is to start looking in your theme's files, where
you might see a folder and directory structure like:

    {your-theme}
    -items
    --show.php

This corresponds to what you will see at /items/show/{item-id}.

Straightforward enough. But it comes as a surprise, then, that there
seems to be no file that corresponds to /items/browse. One would have
expected to see it at

    {your-theme}
    -items
    --browse.php

but it isn't there.

That is because if Omeka does not see the expected file, it falls back
to default theme files. These can be found at

    {omeka-root}
    -application
    --views
    ---scripts

There, you will see subdirectories for items, collections, and more.
Comparing the fallback code with the code in many of the themes for
Omeka, you will see that we rely on the fallback mechanism extensively.

The upshot is that if you want to make an adjustment to a part of
Omeka's public display, but it seems that the file you need is not
present, you might need prevent the fallback behavior from happening.

To do that, you need only copy the fallback file from
/application/views/scripts into the corresponding directory in your
theme. For example, if you want to customize the display for the browse
collections page, you would create the collections directory in your
theme if it does not exist, the copy
/application/views/scripts/collections/browse.php into that directory,
and start editing away!

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Understanding\_Default\_Theme\_Files](Understanding_Default_Theme_Files.html)"

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

    [Page](Understanding_Default_Theme_Files.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Understanding_Default_Theme_Files&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Understanding_Default_Theme_Files&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Understanding_Default_Theme_Files&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](Special:WhatLinksHere/Understanding_Default_Theme_Files.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Understanding_Default_Theme_Files.html)
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
