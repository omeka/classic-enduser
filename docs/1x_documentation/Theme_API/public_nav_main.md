<div id="wrap">

[Skip Navigation](public_nav_main.html#content)
<div id="header">

<div class="padding">

<span
id="logo">[![Omeka](http://omeka.org/ui/i/logo-horizontal-288px.gif)](../../index.html)</span>
<div id="search-form">

</div>

-   <div id="nav-showcase">

    </div>

    [Showcase](../../showcase.1.html)
-   <div id="nav-involved">

    </div>

    [Get Involved](../../index.html%3Fp=124.html)
-   <div id="nav-addons">

    </div>

    [Add-Ons](../../add-ons.1.html)
-   <div id="nav-forums">

    </div>

    [Forums](../../forums/topic/mysqli-stmt.bind-result.html)
-   <div id="nav-documentation">

    </div>

    [Documentation](http://omeka.org/codex/)
-   <div id="nav-download">

    </div>

    [Download](../../download.1.html)

</div>

</div>

<div id="content">

<div class="padding">

<div id="user-meta">

-   <div id="pt-login">

    </div>

    [Log
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20API/public%20nav%20main)

</div>

Functions/public nav main
=========================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>(Redirected from [Theme
API/public nav
main](http://omeka.org/c/index.php?title=Theme_API/public_nav_main&redirect=no "Theme API/public nav main"))

</div>

<div id="primary">

<div
style="background:gold; border:1px solid goldenrod; padding: 1em 1em 0 1em; margin-bottom: 1em;">

<span id="This_page_is_outdated" class="mw-headline">This page is outdated</span> {#this-page-is-outdated style="color:#404040; border-bottom: none"}
---------------------------------------------------------------------------------

The information on this page concerns an old or obsolete version of
Omeka. If you are using a more recent version, instead see
[public\_nav\_main on Omeka's Read the Docs
site](http://omeka.readthedocs.org/en/latest/Reference/libraries/globals/public_nav_main.html).

</div>

Provides an unordered list of the site's main navigational sections.

Plugins may add elements to the navigation through the
[public\_navigation\_main
filter](../Filters/public_navigation_main.html "Filters/public navigation main").

To avoid this, or to create another named navigation element that
plugins can attach to, use the [public\_nav()
function](../Functions/public_nav.html "Functions/public nav").

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php public_nav_main($navArray) ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   *array* \$navArray: An array of link labels pointing to link URLs.
    Best practice for creating links to other parts of an Omeka site is
    to use the [uri() helper](uri.html "Theme API/uri").

<span id="Example" class="mw-headline"> Example </span>
-------------------------------------------------------

For an example, see the following file in the default theme:

-   theme/default/common/header.php

This function is generally used along with a php echo command. In the
above file, it is called with arguments pointing to the uri's for the
list of items and collections.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
echo public_nav_main(
    array(
        'Browse Items' => uri('items'), 
        'Browse Collections' => uri('collections')
    )
);
?>
```

</div>

</div>

<span id="CSS_Styles" class="mw-headline"> CSS Styles </span>
-------------------------------------------------------------

The default CSS style div class tag is .navigation.

<span id="Source_File.2FVersion" class="mw-headline"> Source File/Version </span>
---------------------------------------------------------------------------------

-   application/helpers/LinkFunctions.php since Omeka 1.0

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/public\_nav\_main](../Functions/public_nav_main.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Categories](http://omeka.org/codex/Special:Categories "Special:Categories"):
<span dir="ltr">[Obsolete
pages](http://omeka.org/c/index.php?title=Category:Obsolete_pages&action=edit&redlink=1 "Category:Obsolete pages (page does not exist)")</span>
| <span
dir="ltr">[Functions](../Category:Functions.html "Category:Functions")</span>

</div>

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

    [Page](../Functions/public_nav_main.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/public_nav_main&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/public_nav_main&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/public_nav_main&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Functions/public_nav_main.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/public_nav_main.html)
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

-   [Project](../../index.html%3Fp=2.html)
-   [Staff](../../index.html%3Fp=3.html)
-   [News](../../blog.1.html)
-   [License](http://www.gnu.org/copyleft/gpl.html)

</div>

<div class="section">

### Help

-   [User Forums](../../forums/topic/mysqli-stmt.bind-result.html)
-   [Documentation](http://omeka.org/codex/)
-   [Dev Listserv](http://groups.google.com/group/omeka-dev)
-   [Contact](http://omeka.org/contact/)

</div>

<div class="section">

### Downloads

-   [Download Omeka](../../download.1.html)
-   [Plugins](../../plugins.html)
-   [Themes](../../download/themes/index.html)
-   [Packages](../../index.html%3Fp=222.html)

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
