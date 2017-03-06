<div id="wrap">

[Skip Navigation](display_css.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20API/display%20css)

</div>

Functions/display css
=====================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>(Redirected from [Theme
API/display
css](http://omeka.org/c/index.php?title=Theme_API/display_css&redirect=no "Theme API/display css"))

</div>

<div id="primary">

The display\_css() helper function prints HTML `link` tags to the page
for each stylesheet added with
[queue\_css()](queue_css.html "Theme API/queue css"). It is commonly
used in a theme's common/header.php file to print the `link` tags inside
the page `head`.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php display_css(); ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

display\_css() takes no arguments.

<span id="Return_Value" class="mw-headline"> Return Value </span>
-----------------------------------------------------------------

None. display\_css() prints the tags immediately, it does not return
them as a string.

<span id="Example.28s.29" class="mw-headline"> Example(s) </span>
-----------------------------------------------------------------

### <span id="Standard_Usage" class="mw-headline"> Standard Usage </span>

In a theme's common/header.php:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php display_css(); ?>
```

</div>

</div>

This will print a tag for any script added with
[queue\_css()](queue_css.html "Theme API/queue css"). In a theme, the
call to display\_css() should come after the call to
[plugin\_header()](plugin_header.html "Theme API/plugin header") so
plugins have a chance to add their own CSS.

<span id="Source_File_.2F_Version" class="mw-headline"> Source File / Version </span>
-------------------------------------------------------------------------------------

-   application/helpers/AssetFunctions.php in Omeka 1.3.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/display\_css](../Functions/display_css.html)"

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

    [Page](../Functions/display_css.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/display_css&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/display_css&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/display_css&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Functions/display_css.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/display_css.html)
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
