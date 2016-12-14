<div id="wrap">

[Skip Navigation](queue_css.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/queue%20css)

</div>

Functions/queue css
===================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>

</div>

<div id="primary">

The queue\_css() helper function is used to add stylesheets that will be
printed by [display\_css](display_css.html "Functions/display css").
This is the preferred method for both theme and plugin writers to add
CSS to a page.

For stylesheets added with this function to be displayed, the
queue\_css() call must come before the display\_css() call. This means
you can generally call queue\_css() in the following places:

-   In common/header.php, before the call to
    [display\_css()](display_css.html "Functions/display css").
-   In a particular view script, before the call to
    [head()](head.html "Functions/head").
-   For plugin writers, in the
    [public\_theme\_header](../Hooks/public_theme_header.html "Hooks/public theme header")
    or
    [admin\_theme\_header](../Hooks/admin_theme_header.html "Hooks/admin theme header") hooks.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
queue_css($file, 
          $media = 'all',
          $conditional = false,
          $dir = 'css');
?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   \$file (string|array) (required) The name of the CSS file
    to include. You should omit the ".css" extension from the filename.
    You can also specify an array of filenames, and each file will
    be included.
-   \$media (string) (optional) (default: 'all') The media type the
    stylesheet should apply to. This is output as the "media" attribute
    of the `link` tag.
-   \$conditional (string) (optional) (default: false) An IE-style
    [conditional
    comment](http://en.wikipedia.org/wiki/Conditional_comment "wikipedia:Conditional comment").
    This is generally used to include IE-only styles. The default is to
    include no conditional.
-   \$dir (string) (optional) (default: 'css') The theme directory that
    will be searched for the CSS file. The default is the
    "css" directory.

<span id="Return_Value" class="mw-headline"> Return Value </span>
-----------------------------------------------------------------

None.

<span id="Output" class="mw-headline"> Output </span>
-----------------------------------------------------

None.
[display\_css()](../Theme_API/display_css.html "Theme API/display css")
is the corresponding helper that outputs the tags; all Omeka pages will
normally call display\_css().

<span id="Example.28s.29" class="mw-headline"> Example(s) </span>
-----------------------------------------------------------------

### <span id="Including_a_Single_Stylesheet" class="mw-headline"> Including a Single Stylesheet </span>

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php queue_css('styles'); ?>
```

</div>

</div>

This will cause a call to
[display\_css()](../Theme_API/display_css.html "Theme API/display css")
to include a tag like:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="xml source-xml">

``` {.de1}
<link href="http://your-path/css/styles.css" media="all" rel="stylesheet" type="text/css">
```

</div>

</div>

### <span id="Including_Multiple_Stylesheets" class="mw-headline"> Including Multiple Stylesheets </span>

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php queue_css(array('style1', 'style2', 'style3')); ?>
```

</div>

</div>

This is equivalent to calling the above example three times, once for
each stylesheet.

<span id="Source_File_.2F_Version" class="mw-headline"> Source File / Version </span>
-------------------------------------------------------------------------------------

-   application/helpers/AssetFunctions.php in Omeka 1.3.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/queue\_css](queue_css.html)"

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

    [Page](queue_css.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/queue_css&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/queue_css&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/queue_css&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](../Special:WhatLinksHere/Functions/queue_css.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/queue_css.html)
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
