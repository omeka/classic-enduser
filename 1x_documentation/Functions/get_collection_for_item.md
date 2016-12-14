<div id="wrap">

[Skip Navigation](get_collection_for_item.html#content)
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
    In](https://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/get%20collection%20for%20item)

</div>

Functions/get collection for item
=================================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.1.html "Functions")</span>

</div>

<div id="primary">

<div
style="background:gold; border:1px solid goldenrod; padding: 1em 1em 0 1em; margin-bottom: 1em;">

<span id="This_page_is_outdated" class="mw-headline">This page is outdated</span> {#this-page-is-outdated style="color:#404040; border-bottom: none"}
---------------------------------------------------------------------------------

The information on this page concerns an old or obsolete version of
Omeka. If you are using a more recent version, instead see
[get\_collection\_for\_item on Omeka's Read the
Docs](http://omeka.readthedocs.org/en/latest/Reference/libraries/globals/get_collection_for_item.html).

</div>

<span id="Description" class="mw-headline"> Description </span>
---------------------------------------------------------------

The `get_collection_for_item()` returns the Collection object for a
specified item, and retrieves the current item object by default. This
is meant to be a simple facade for access to the Collection record, and
is used by
[link\_to\_collection\_for\_item()](../Theme_API/link_to_collection_for_item.html "Theme API/link to collection for item")
to generate a link to the current item's collection.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo get_collection_for_item($item=null); ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   **\$item** (object) or null (default). If null, the current item in
    the loop is used.

<span id="Examples" class="mw-headline"> Examples </span>
---------------------------------------------------------

### <span id="Printing_the_Name_of_a_Collection" class="mw-headline"> Printing the Name of a Collection </span>

The following example works on an items/show/ page. Retrieving the
item's collection, the name of the collection is printed on the screen.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
 
   $Collection = get_collection_for_item();
   echo $Collection->name;
 
?>
```

</div>

</div>

The name of the collection is available via the Collection database
model. Similar code could be used to display both the name of a
collection, and its description on an items/show/ page.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
 
   if ($Collection = get_collection_for_item()) {
      echo '<h1>' . $Collection->name . '</h1>';
      echo '<p>' . $Collection->description . '</p>';
   } else {
      echo '<p>This item is not in a collection.</p>';
   } 
 
?>
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[https://omeka.org/codex/Functions/get\_collection\_for\_item](get_collection_for_item.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Category](../Special:Categories.html "Special:Categories"): <span
dir="ltr">[Obsolete
pages](https://omeka.org/c/index.php?title=Category:Obsolete_pages&action=edit&redlink=1 "Category:Obsolete pages (page does not exist)")</span>

</div>

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

    [Page](get_collection_for_item.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Functions/get_collection_for_item&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Functions/get_collection_for_item&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Functions/get_collection_for_item&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Functions/get_collection_for_item.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/get_collection_for_item.html)
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
