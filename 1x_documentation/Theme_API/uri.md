<div id="wrap">

[Skip Navigation](uri.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20API/uri)

</div>

Functions/uri
=============

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>(Redirected from [Theme
API/uri](http://omeka.org/c/index.php?title=Theme_API/uri&redirect=no "Theme API/uri"))

</div>

<div id="primary">

Returns a URL to a page in an Omeka site. This function can be used to
create links between different pages on the site.

Plugin and theme writers should always use this helper when linking
between pages. Hand-written or "bare" URLs are generally only valid for
a particular Omeka installation. This helper generates relative URLs
that are valid regardless of where an Omeka installation is located on a
server.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php uri($options, $route, $queryParams, $reset, $encode); ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   \$options (*string* or *array*)(optional, default: empty array)
    -   If a string is passed it is treated as an Omeka-relative link.
        So, passing 'items' would create a link to the items page.
    -   (Advanced) If an array is passed (or no argument given), it is
        treated as options to be passed to Omeka's routing system.
-   \$route (*string*)(optional, default: null) The route to use if an
    array is passed in the first argument.
-   \$queryParams (*array*)(optional, default: empty array) A set of
    query string parameters to append to the URL
-   \$reset (*boolean*)(optional, default: false) Whether Omeka should
    discard the current route when generating the URL.
-   \$encode (*boolean*)(optional, default: true) Whether the URL should
    be URL-encoded

<span id="Return_Value" class="mw-headline"> Return Value </span>
-----------------------------------------------------------------

(*string*) URL.

<span id="Example.28s.29" class="mw-headline"> Example(s) </span>
-----------------------------------------------------------------

There are many possible arguments above, but the general usage of this
helper is simple.

To print a URL pointing to Omeka's items page:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo uri('items'); ?>
```

</div>

</div>

<span id="Source_File.2FVersion" class="mw-headline"> Source File/Version </span>
---------------------------------------------------------------------------------

-   application/helpers/UrlFunctions.php since Omeka 1.0

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/uri](../Functions/uri.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Category](http://omeka.org/codex/Special:Categories "Special:Categories"):
<span
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

    [Page](../Functions/uri.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/uri&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/uri&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/uri&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](../Special:WhatLinksHere/Functions/uri.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related changes](../Special:RecentChangesLinked/Functions/uri.html)
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
