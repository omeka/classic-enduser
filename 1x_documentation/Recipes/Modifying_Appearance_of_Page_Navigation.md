<div id="wrap">

[Skip Navigation](Modifying_Appearance_of_Page_Navigation.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Modifying%20Appearance%20of%20Page%20Navigation)

</div>

Recipes/Modifying Appearance of Page Navigation
===============================================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

I wanted to change the browse results page navigation from "First Next
22 23 24 25 26 Previous Last" to something like: "&lt;&lt; 1 ...... 22
23 24 25 26 ...... 163 &gt;&gt;"

<span id="Solution" class="mw-headline"> Solution </span>
---------------------------------------------------------

In order to change the look for these links I copied the
pagination-control.php file from application/views/scripts/common/ to my
theme's common directory. Then I made the following changes to this
file:

-   The First and Last links, now display the number for the first and
    last pages of results&lt;/li
-   Previous/Next are now &lt;&lt;/&gt;&gt;
-   Added ellipses to add some spacing to the links

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
    <!--If page count is greater than 1 and greater than 5-->
    <?php if ($this->pageCount > 1 && $this->pageCount > 5): ?>
    <ul class="pagination_list">
    <?php if (isset($this->previous)): ?>
    <!-- Previous page link -->
    <li class="pagination_previous">
    <!-- Removed the word Previous and replaced it with << -->
    <a href="<?php echo html_escape($this->url(array('page' => $this->previous), null, $_GET)); ?>"><<</a>
    </li>
 
    <?php endif; ?>   
 
    <!-- if the current page is not one of the first three records -->
    <!-- Prevents duplicate links for first three pages like << 1......1 2 3 4 5 .......50>>. This now looks like << 1 2 3 4 5.......50 >> for first three records.-->
    <?php if ($this->current >3): ?>
    <!-- First page link -->
    <li class="pagination_first">
    <a href="<?php echo html_escape($this->url(array('page' => $this->first), null, $_GET)); ?>"><?php echo ($this->first); ?></a>
    </li>
    <li>......</li>
    <?php endif; ?>
 
 
    <!-- Numbered page links -->
    <?php foreach ($this->pagesInRange as $page): ?>
    <?php if ($page != $this->current): ?>
    <li class="pagination_range"><a href="<?php echo html_escape($this->url(array('page' => $page), null, $_GET)); ?>"><?php echo $page; ?></a></li>
    <?php else: ?>
    <li class="pagination_current"><?php echo $page; ?></li>
    <?php endif; ?>
    <?php endforeach; ?>
 
    <!-- if the current page is not one of the last 3 pages -->
    <!-- Prevents duplicate links for the last three pages like << 1......46 47 48 49 50 .......50>>. This now looks like << 1......46 47 48 49 50 >> for last three pages-->
    <?php if ($this->current < ($this->last)-2): ?>
    <li>......</li>
    <!-- Last page link -->
    <li class="pagination_last">
    <a href="<?php echo html_escape($this->url(array('page' => $this->last), null, $_GET)); ?>"><?php echo ($this->last); ?></a>
    </li>
    <?php endif; ?>
 
    <!-- Removed the word Next and replaced it with >> -->
    <?php if (isset($this->next)): ?>
    <!-- Next page link -->
    <li class="pagination_next">
    <a href="<?php echo html_escape($this->url(array('page' => $this->next), null, $_GET)); ?>">>></a>
    </li>
    <?php endif; ?>
 
</ul>
<?php endif; ?>
<!-- if there are 5 or fewer pages, do not include the elipses, and do not include extra links to first and last pages --->
<?php if ($this->pageCount > 1 && $this->pageCount <= 5): ?>
<ul class="pagination_list">
 
    <?php if (isset($this->previous)): ?>
    <!-- Previous page link -->
    <li class="pagination_previous">
    <a href="<?php echo html_escape($this->url(array('page' => $this->previous), null, $_GET)); ?>"><<</a>
    </li>
    <?php endif; ?>
 
    <!-- Numbered page links -->
    <?php foreach ($this->pagesInRange as $page): ?>
    <?php if ($page != $this->current): ?>
    <li class="pagination_range"><a href="<?php echo html_escape($this->url(array('page' => $page), null, $_GET)); ?>"><?php echo $page; ?></a></li>
    <?php else: ?>
    <li class="pagination_current"><?php echo $page; ?></li>
    <?php endif; ?>
    <?php endforeach; ?>
 
    <?php if (isset($this->next)): ?>
    <!-- Next page link -->
    <li class="pagination_next">
    <a href="<?php echo html_escape($this->url(array('page' => $this->next), null, $_GET)); ?>">>></a>
    </li>
    <?php endif; ?>
 
    </ul>
<?php endif; ?>
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Modifying\_Appearance\_of\_Page\_Navigation](Modifying_Appearance_of_Page_Navigation.html)"

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

    [Page](Modifying_Appearance_of_Page_Navigation.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/Modifying_Appearance_of_Page_Navigation&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Modifying_Appearance_of_Page_Navigation&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Modifying_Appearance_of_Page_Navigation&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Modifying_Appearance_of_Page_Navigation.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Modifying_Appearance_of_Page_Navigation.html)
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
