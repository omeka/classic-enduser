<div id="wrap">

[Skip Navigation](js.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/js)

</div>

Functions/js
============

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>

</div>

<div id="primary">

The js() helper function retrieves JavaScript files located within the
*/javascripts/* folder of a theme. By using js(), the relative path to
the file is dynamically generated for each page.

**Note:** Starting with Omeka 1.3, the
[queue\_js](../Theme_API/queue_js.html "Theme API/queue js") helper is
preferred to this one for most use cases. Normally, you should only
continue to use this helper when you want to output an inline script in
the body of the page.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php  
    js($file,
        $dir = 'javascripts',
        $scriptaculousLibraries = array('effects', 'dragdrop'));
?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

 *string* `$file` {{\#if
:   | (optional)}}
:   The name of the JavaScript file to be included, without the
    *.js* extension.
:   {{\#if: | Default: `{{{default}}}`}}

 *string* `$dir` {{\#if
:   'javascripts' | (optional)}}
:   The theme directory where the JavaScript file is located.
:   {{\#if: 'javascripts' | Default: `'javascripts'`}}

 *array* `$scriptaculousLibraries` {{\#if
:   array('effects', 'dragdrop') | (optional)}}
:   An array of Scriptaculous libraries to be included, by file name.
    This variable has effect only if 'default' is passed for the
    `$file` parameter.
:   {{\#if: array('effects', 'dragdrop') | Default:
    `array('effects', 'dragdrop')`}}

<span id="Return_Values" class="mw-headline"> Return Values </span>
-------------------------------------------------------------------

-   (string) A &lt;script&gt; tag that includes the JavaScript file

<span id="Example.28s.29" class="mw-headline"> Example(s) </span>
-----------------------------------------------------------------

### <span id="Include_a_JavaScript_file" class="mw-headline"> Include a JavaScript file </span>

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo js('foo'); ?>
```

</div>

</div>

The above code includes the JavaScript file *foo.js* in the
*themes/\[YOUR THEME\]/javascripts* directory by returning the following
HTML

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<script type="text/javascript" 
src="http://www.yourdomain.com/themes/YourTheme/javascripts/foo.js" 
charset="utf-8"></script>
```

</div>

</div>

### <span id="Include_the_default_JavaScript_file" class="mw-headline"> Include the default JavaScript file </span>

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo js('default'); ?>
```

</div>

</div>

The above code includes JavaScript file *default.js* within the
*javascripts* directory. Because it is including the default JavaScript
file, the function loads the effects and drag and drop Scriptalicious
libraries.

<span id="Source_File_.2F_Version" class="mw-headline"> Source File / Version </span>
-------------------------------------------------------------------------------------

-   application/helpers/FileFunctions.php in Omeka 1.0.

<div class="printfooter">

Retrieved from "[http://omeka.org/codex/Functions/js](js.html)"

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

    [Page](js.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/js&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/js&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/js&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](../Special:WhatLinksHere/Functions/js.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related changes](../Special:RecentChangesLinked/Functions/js.html)
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
