<div id="wrap">

[Skip Navigation](nav.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/nav)

</div>

Functions/nav
=============

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>

</div>

<div id="primary">

The nav() helper function generates an unordered list of navigation
links on your theme. HTML list items will be given a class of "current"
for any links corresponding to the current page.

When creating navigation on your public theme, use the
[public\_nav\_main()](../Theme_API/public_nav.html "Theme API/public nav")
helper instead of nav. The difference between nav() and public\_nav() is
that plugins (including
[SimplePages](http://omeka.org/codex/Plugins/SimplePages "Plugins/SimplePages"))
are able to dynamically add or remove links from the navigation in
public\_nav().

<span id="Arguments:" class="mw-headline"> Arguments: </span>
-------------------------------------------------------------

-   \$links: array Key = Text of Navigation, Value = Link

<span id="Example" class="mw-headline"> Example </span>
-------------------------------------------------------

The following code creates navigation both the Items and Exhibits pages,
and uses the [uri()](../Theme_API/uri.html "Theme API/uri") function to
build dynamic links to pages within Omeka.:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<ul class="navigation"
<?php echo nav(
             array( 
               'Items' => uri('items'),
               'Exhibits' => uri('exhibits')
             )
           ); 
?>
</ul>
```

</div>

</div>

And the following HTML is produced:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="html4strict source-html4strict">

``` {.de1}
<ul class="navigation">
<li class="nav-items current">
  <a href="http://example.com/omeka/items">Items</a></li>
<li class="nav-exhibits">
  <a href="http://example.com/omeka/exhibits">Exhibits</a></li>
</ul>
```

</div>

</div>

<div class="printfooter">

Retrieved from "[http://omeka.org/codex/Functions/nav](nav.html)"

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

    [Page](nav.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/nav&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/nav&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/nav&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](../Special:WhatLinksHere/Functions/nav.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related changes](../Special:RecentChangesLinked/Functions/nav.html)
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
