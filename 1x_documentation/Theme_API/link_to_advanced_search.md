<div id="wrap">

[Skip Navigation](link_to_advanced_search.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20API/link%20to%20advanced%20search)

</div>

Functions/link to advanced search
=================================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>(Redirected from [Theme
API/link to advanced
search](http://omeka.org/c/index.php?title=Theme_API/link_to_advanced_search&redirect=no "Theme API/link to advanced search"))

</div>

<div id="primary">

The `link_to_advanced_search` function will create a link to your
advanced search page.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php link_to_advanced_search(
        $text = 'Advanced Search', 
        $props = array(), 
        $uri=null
      );
?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   text - (string) The string of text for the link. Default is
    'Advanced Search'.
-   props - (array) An array of properties for the advanced search link.
    These are attributes and values for the `<a>` tag.
-   uri - The uri for your advanced search page. If null, the default
    advanced search uri (advanced-search) is used.

<span id="Examples" class="mw-headline"> Examples </span>
---------------------------------------------------------

### <span id="Changing_the_text_of_the_link" class="mw-headline"> Changing the text of the link </span>

By default, the link to your advanced search page will say 'Advanced
Search'. If you would like to change that, simply pass the new text as
the first argument to the function:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo link_to_advanced_search('More Search Options'); ?>
```

</div>

</div>

This will generate:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="html4strict source-html4strict">

``` {.de1}
<a href="http://example.com/advanced-search/">More Search Options</a>
```

</div>

</div>

### <span id="Adding_Attributes_to_the_Link" class="mw-headline"> Adding Attributes to the Link </span>

You can add attributes to the link, such as `id` or `class`, by passing
those attributes to the `props` argument in an array:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
echo link_to_advanced_search(
        'Advanced Search', 
        array(
            'id' => 'advanced-search-link', 
            'class' => 'link')
            ); 
?>
```

</div>

</div>

This will generate:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="html4strict source-html4strict">

``` {.de1}
<a href="http://example.com/advanced-search/" 
id="advanced-search-link" class="link">Advanced Search</a>
```

</div>

</div>

You can add any valid attribute to the link tag.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/link\_to\_advanced\_search](../Functions/link_to_advanced_search.html)"

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

    [Page](../Functions/link_to_advanced_search.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/link_to_advanced_search&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/link_to_advanced_search&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/link_to_advanced_search&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Functions/link_to_advanced_search.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/link_to_advanced_search.html)
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
