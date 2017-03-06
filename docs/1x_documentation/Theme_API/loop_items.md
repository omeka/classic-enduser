<div id="wrap">

[Skip Navigation](loop_items.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20API/loop%20items)

</div>

Functions/loop items
====================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>(Redirected from [Theme
API/loop
items](http://omeka.org/c/index.php?title=Theme_API/loop_items&redirect=no "Theme API/loop items"))

</div>

<div id="primary">

`loop_items()` loops through an array of items, enabling a theme writer
to display metadata for each item in the loop.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php loop_items(); ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

None

<span id="Examples" class="mw-headline"> Examples </span>
---------------------------------------------------------

### <span id="Default_code_on_items.2Fbrowse.php" class="mw-headline"> Default code on items/browse.php </span>

The following example can be used on the items/browse.php page in the
default theme. An array of items is already available for that view, so
this example simply loops through that array of items, and displays the
title of each item with a link.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php while (loop_items()): ?>
 
    <h3><?php echo link_to_item(item('Dublin Core', 'Title'), array('class'=>'permalink')); ?></h3>
 
<?php endwhile; ?>
```

</div>

</div>

### <span id="Looping_Items_Elsewhere" class="mw-headline"> Looping Items Elsewhere </span>

If you wish to loop through items in template files other than
items/browse.php, you'll need to use the set\_items\_for\_loop helper to
set an array of items first. The following example is on the index.php
file of the default theme. The `loop_items` helper uses the array of
items created in the `set_items_for_loop` helper:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php set_items_for_loop(recent_items(10)); ?>
<?php if (has_items_for_loop()): ?>
    <ul class="items-list">
    <?php while (loop_items()): ?>
        <li class="item">
            <h3><?php echo link_to_item(); ?></h3>
            <?php if($desc = item('Dublin Core', 'Description', array('snippet'=>150))): ?>
            <div class="item-description"><?php echo $desc; ?></div>
            <?php endif; ?>       
        </li>     
    <?php endwhile; ?>
    </ul>
<?php else: ?>
    <p>No recent items available.</p>
<?php endif; ?>
```

</div>

</div>

### <span id="Browsing_specific_item_types_with_specific_metadata" class="mw-headline"> Browsing specific item types with specific metadata </span>

If you would like to create a browse view that calls a specific item
type containing specific metadata. For example, create a browse page
with only Still Images with the Original Format field with the text,
Map:

&lt;?php if (item\_has\_type('Still Image') && item('Item Type
Metadata', 'Original Format')== 'Map'): ?&gt;

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/loop\_items](../Functions/loop_items.html)"

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

    [Page](../Functions/loop_items.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/loop_items&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/loop_items&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/loop_items&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Functions/loop_items.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/loop_items.html)
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
