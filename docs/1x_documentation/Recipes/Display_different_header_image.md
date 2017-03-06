<div id="wrap">

[Skip Navigation](Display_different_header_image.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Display%20different%20header%20image)

</div>

Recipes/Display different header image
======================================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

I want to display a different header image if the page is a SimplePages
page.

-   See also [Header Images and
    Themes](../../forums/topic/header-images-and-themes.html)

<span id="Solution_.231" class="mw-headline"> Solution \#1 </span>
------------------------------------------------------------------

In the theme's header.php file, usually in `theme/common/header.php`,
add the following code to change the image if the page is a SimplePage.
This example comes from "Seasons" theme.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<div id="header">
    <div class="center-div">
        <div id="search-container">
            <?php echo simple_search(); ?>
            <?php echo link_to_advanced_search(); ?>
        </div>
        <div id="site-title">
 
            <?php if ($bodyclass=='page simple-page simple-page-home'):?>
                  <img src="my_image.jpg"/>
            <?php else: ?>
                 <?php echo link_to_home_page(custom_display_logo()); ?>
            <?php endif ?> 
 
         </div>
     </div><!--center-div-->
</div>
```

</div>

</div>

In the site title div, the original code for the theme was:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<div id="site-title">
    <?php echo link_to_home_page(custom_display_logo()); ?>
</div>
```

</div>

</div>

The changes here check to see if we are looking at a simple page, and if
so shows just an image.

### <span id="Functions_Used" class="mw-headline"> Functions Used </span>

-   [link\_to\_home\_page()](../Functions/link_to_home_page.html "Functions/link to home page")

<span id="Solution_.232" class="mw-headline"> Solution \#2 </span>
------------------------------------------------------------------

Just put the following into your SimplePage

    <style type="text/css">
    #header {background: transparent url(/omeka/archive/files/yourimage.jpg);}
    </style>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Display\_different\_header\_image](Display_different_header_image.html)"

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

    [Page](Display_different_header_image.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](../Talk:Recipes/Display_different_header_image.html)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Display_different_header_image&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Display_different_header_image&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Display_different_header_image.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Display_different_header_image.html)
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
