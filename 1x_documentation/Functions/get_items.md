<div id="wrap">

[Skip Navigation](get_items.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/get%20items)

</div>

Functions/get items
===================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>

</div>

<div id="primary">

The `get_items()` helper allows you to retrieve an array of items
matching several arguments. You can then use this array in
[set\_items\_for\_loop](../Theme_API/set_items_for_loop.html "Theme API/set items for loop")
to create a custom loop of items.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
 
get_items(
    $params = array(), 
    $limit
);
 
?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   params - An array of parameters. Available parameters include:
    -   collection - Collection ID
    -   featured - true or false
    -   range - A range of item IDs
    -   recent - true or false
    -   tags - A string of comma-separated tags
    -   type - Type ID
    -   user - User ID
    -   sort\_field (see [Sorting
        Results](../Sorting_Results.html "Sorting Results"))
    -   sort\_dir (see [Sorting
        Results](../Sorting_Results.html "Sorting Results"))

<!-- -->

-   limit - The maximum number of items you want to return. The default
    value is '10'.

<span id="Examples" class="mw-headline"> Examples </span>
---------------------------------------------------------

### <span id="Recent_Items" class="mw-headline"> Recent Items </span>

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
$items = get_items(array('recent' => true));
set_items_for_loop($items);
while(loop_items()):
?>
<h2><?php echo item('Dublin Core', 'Title'); ?></h2>
<p><?php echo item('Dublin Core', 'Description'); ?></p>
<?php endwhile; ?>
```

</div>

</div>

You can also use the
[recent\_items](../Theme_API/recent_items.html "Theme API/recent items")
helper.

### <span id="Three_Featured_Items" class="mw-headline"> Three Featured Items </span>

The following uses `get_items` helper to create a loop of the last 3
items marked "featured".

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
$items = get_items(array('featured' => true));
set_items_for_loop($items);
while(loop_items()):
?>
 
<h2><?php echo item('Dublin Core', 'Title'); ?></h2>
<p><?php echo item('Dublin Core', 'Description'); ?></p>
<?php endwhile; ?>
```

</div>

</div>

### <span id="Last_20_items_tagged_.22foo.22_and_.22bar.22" class="mw-headline"> Last 20 items tagged "foo" and "bar" </span>

The following uses `get_items` helper to create a loop of the last 20
items tagged "foo" and "bar".

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
$items = get_items(array('tags' => 'foo,bar'), 20);
set_items_for_loop($items);
while(loop_items()):
?>
 
<h2><?php echo item('Dublin Core', 'Title'); ?></h2>
<p><?php echo item('Dublin Core', 'Description'); ?></p>
 
<?php endwhile; ?>
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/get\_items](get_items.html)"

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

    [Page](get_items.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/get_items&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/get_items&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/get_items&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](../Special:WhatLinksHere/Functions/get_items.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/get_items.html)
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
