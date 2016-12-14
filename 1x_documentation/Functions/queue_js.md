<div id="wrap">

[Skip Navigation](queue_js.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/queue%20js)

</div>

Functions/queue js
==================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>

</div>

<div id="primary">

The queue\_js() helper function is used to add script files that will be
printed by [display\_js](display_js.html "Functions/display js"). This
is the preferred method for both theme and plugin writers to add
JavaScript to a page.

For stylesheets added with this function to be displayed, the
queue\_js() call must come before the display\_js() call. This means you
can generally call queue\_js() in the following places:

-   In common/header.php, before the call to
    [display\_js()](display_js.html "Functions/display js").
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
queue_js($file, $dir = 'javascripts');
?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   \$file (string|array) (required) The name of the JavaScript file
    to include. You should omit the ".js" extension from the filename.
    You can also specify an array of filenames, and each file will
    be included.
-   \$dir (string) (optional) (default: 'javascripts') The theme
    directory that will be searched for the JavaScript file. The default
    is the "javascripts" directory.

<span id="Return_Value" class="mw-headline"> Return Value </span>
-----------------------------------------------------------------

None.

<span id="Output" class="mw-headline"> Output </span>
-----------------------------------------------------

None.
[display\_js()](../Theme_API/display_js.html "Theme API/display js") is
the corresponding helper that outputs the tags; all Omeka pages will
normally call display\_js().

<span id="Example.28s.29" class="mw-headline"> Example(s) </span>
-----------------------------------------------------------------

### <span id="Including_a_Single_Script" class="mw-headline"> Including a Single Script </span>

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php queue_js('my-js'); ?>
```

</div>

</div>

This will cause a call to
[display\_js()](../Theme_API/display_js.html "Theme API/display js") to
include a tag like:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="xml source-xml">

``` {.de1}
<script type="text/javascript" src="http://example.com/omeka/themes/your-theme/javascripts/my-js.js"></script>
```

</div>

</div>

### <span id="Including_Multiple_Scripts" class="mw-headline"> Including Multiple Scripts </span>

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php queue_js(array('js1', 'js2', 'js3')); ?>
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
"[http://omeka.org/codex/Functions/queue\_js](queue_js.html)"

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

    [Page](queue_js.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/queue_js&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/queue_js&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/queue_js&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](../Special:WhatLinksHere/Functions/queue_js.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/queue_js.html)
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
