<div id="wrap">

[Skip Navigation](link_to_collection_for_item.html#content)
<div id="header">

<div class="padding">

<span
id="logo">[![Omeka](../../ui/i/logo-horizontal-288px.gif)](../../index.html)</span>
<div id="search-form">

</div>

-   <div id="nav-showcase">

    </div>

    [Showcase](../../showcase/index.html)
-   <div id="nav-involved">

    </div>

    [Get Involved](../../get-involved/index.html)
-   <div id="nav-addons">

    </div>

    [Add-Ons](../../add-ons/index.html)
-   <div id="nav-forums">

    </div>

    [Forums](../../forums/index.html)
-   <div id="nav-documentation">

    </div>

    [Documentation](../index.html)
-   <div id="nav-download">

    </div>

    [Download](../../download/index.html)

</div>

</div>

<div id="content">

<div class="padding">

<div id="user-meta">

-   <div id="pt-login">

    </div>

    [Log
    In](https://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20API/link%20to%20collection%20for%20item)

</div>

Functions/link to collection for item
=====================================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.1.html "Functions")</span>(Redirected from
[Theme API/link to collection for
item](https://omeka.org/c/index.php?title=Theme_API/link_to_collection_for_item&redirect=no "Theme API/link to collection for item"))

</div>

<div id="primary">

The `link_to_collection_for_item` helper will generate a link to the
collection to which an item belongs. The title of the collection is used
as the text for the link.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php link_to_collection_for_item(
        $text = null, 
        $props = array(), 
      );
?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   text - (string) The string of text for the link. Default is null. If
    null, the title of the collection is used.
-   props - (array) An array of properties for the advanced search link.
    These are attributes and values for the &lt;a&gt; tag.

<span id="Examples" class="mw-headline"> Examples </span>
---------------------------------------------------------

### <span id="Change_the_text_of_the_link" class="mw-headline"> Change the text of the link </span>

You can use any string of text for the link to the item's collection by
specifying it as the first argument:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
echo link_to_collection_for_item('Item Collection'); 
?>
 
This will generate:
 
<source lang="html4strict">
<a href="http://example.com/collections/show/4">Item Collection</a>
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
echo link_to_collection_for_item(
        'Item Collection', 
        array(
            'id' => 'item-collection-link', 
        )
     ); 
?>
```

</div>

</div>

This will generate:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="html4strict source-html4strict">

``` {.de1}
<a href="http://example.com/collections/show/4" 
id="item-collection-link">Item Collection</a>
```

</div>

</div>

You can add any valid attribute to the link tag.

<div class="printfooter">

Retrieved from
"<https://omeka.org/codex/Functions/link_to_collection_for_item>"

</div>

<div id="catlinks" class="catlinks catlinks-allhidden">

</div>

</div>

<div id="secondary">

<div class="portlet">

Documentation
-------------

-   [Home](../index.html)
-   [Screencasts](../Screencasts.html)
-   [Themes](../Managing_Themes_2.0.html)
-   [Appearance](../Managing_Appearance_2.0.html)
-   [Plugins](../Plugins2.0.html)

</div>

<div class="portlet">

Page View
---------

-   <div id="nav-page">

    </div>

    [Page](https://omeka.org/codex/Functions/link_to_collection_for_item)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Functions/link_to_collection_for_item&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Functions/link_to_collection_for_item&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Functions/link_to_collection_for_item&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](https://omeka.org/codex/Special:WhatLinksHere/Functions/link_to_collection_for_item)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](https://omeka.org/codex/Special:RecentChangesLinked/Functions/link_to_collection_for_item)
-   <div id="t-specialpages">

    </div>

    [Special pages](../Special:SpecialPages.html)

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

-   [Project](../../about/index.html)
-   [Staff](../../about/staff/index.html)
-   [News](../../blog/index.html)
-   [License](http://www.gnu.org/copyleft/gpl.html)

</div>

<div class="section">

### Help

-   [User Forums](../../forums/index.html)
-   [Documentation](../index.html)
-   [Dev Listserv](http://groups.google.com/group/omeka-dev)
-   [Contact](../../contact/index.html)

</div>

<div class="section">

### Downloads

-   [Download Omeka](../../download/index.html)
-   [Plugins](../../addons/plugins.html)
-   [Themes](../../addons/themes.html)
-   [Packages](../../download/packages/index.html)

</div>

</div>

<div id="chnm-meta">

<span id="chnm-logo">[![Roy Rosenzweig Center for History and New
Media](../../ui/i/rrchnm-logo-regular.gif)](http://chnm.gmu.edu)</span>
Omeka is a project of the [Roy Rosenzweig Center for History and New
Media](http://chnm.gmu.edu), [George Mason
University](http://www.gmu.edu). Copyright © 2007–2016 CHNM.

</div>

</div>

</div>

</div>
