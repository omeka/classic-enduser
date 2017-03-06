<div id="wrap">

[Skip Navigation](public_nav.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/public%20nav)

</div>

Functions/public nav
====================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>

</div>

<div id="primary">

Provides an unordered list of links for site navigation.

To get the navigation element that plugins will add to by default, use
[public\_nav\_main](../Theme_API/public_nav_main.html "Theme API/public nav main").

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php public_nav($navArray, $navType) ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   *array* \$navArray: An array of link labels pointing to link URLs.
    Best practice for creating links to other parts of an Omeka site is
    to use the [uri() helper](../Theme_API/uri.html "Theme API/uri").
-   *string* \$navType: (optional) A name specifying what "type" of
    navigation is being created. Omitting this argument causes plugins
    to be unable to add to the navigation.

<span id="Example" class="mw-headline"> Example </span>
-------------------------------------------------------

The following example code will print only exactly the links that are
passed in the \$navArray. Plugins will not add any additional links.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<ul>
<?php 
echo public_nav(
    array(
        'Browse Items' => uri('items'), 
        'Browse Collections' => uri('collections')
    )
);
?>
</ul>
```

</div>

</div>

This example will generate the following HTML:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<ul>
<li><a href="http://example.com/items">Browse Items</a></li>
<li><a href="http://example.com/collections">Browse Collections</a></li>
</ul>
```

</div>

</div>

On the other hand, public\_nav can also be used to create a new
navigation "type" that plugins can optionally attach to.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
echo public_nav(
    array(
        'Browse Items' => uri('items'), 
        'Browse Collections' => uri('collections')
    ), 'mynav'
);
?>
```

</div>

</div>

In the above case, plugins will be able to use a filter called
'public\_navigation\_mynav' to add to this element without affecting the
main or any other navigation.

<span id="CSS_Styles" class="mw-headline"> CSS Styles </span>
-------------------------------------------------------------

The default CSS style div class tag is .navigation.

<span id="Source_File.2FVersion" class="mw-headline"> Source File/Version </span>
---------------------------------------------------------------------------------

-   application/helpers/LinkFunctions.php since Omeka 1.0

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/public\_nav](public_nav.html)"

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

    [Page](public_nav.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/public_nav&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/public_nav&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/public_nav&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](http://omeka.org/codex/Special:WhatLinksHere/Functions/public_nav)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](http://omeka.org/codex/Special:RecentChangesLinked/Functions/public_nav)
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
