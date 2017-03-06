<div id="wrap">

[Skip Navigation](YouTube_Video_For_Item.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/YouTube%20Video%20For%20Item)

</div>

Recipes/YouTube Video For Item
==============================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

How to create and display items that use/embed YouTube videos.

<span id="Solution" class="mw-headline"> Solution </span>
---------------------------------------------------------

The key is to include the YouTube video's unique identifier when adding
metadata to an item. The YouTube identifier is part of a video's url.
For example:

-   YouTube video url: <http://www.youtube.com/watch?v=R8XAlSp838Y>
-   YouTube identifier: **R8XAlSp838Y**

The YouTube identifier is necessary for creating video embed code,
and/or obtaining YouTube-provided thumbnail image URLs. For the purpose
of this recipe, the YouTube identifier will reside in an item's Dublin
Core "Identifier" field.

The general strategy is to first use the item() function to retrieve the
YouTube identifier, and then use the identifier to create the embed code
or thumbnail image path URL for display.

\

### <span id="Functions_Used" class="mw-headline"> Functions Used </span>

-   [item()](../Functions/item.html "Functions/item")
-   [link\_to\_item()](../Functions/link_to_item.html "Functions/link to item")
-   [loop\_items()](../Functions/loop_items.html "Functions/loop items")

\
 Here's an example of how to display YouTube video within a page, such
as the item view page (applications/views/scripts/items/show.php)

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php /* First get the YouTube identifier from the item metadata: */ ?>
<?php $youtube_id= item('Dublin Core', 'Identifier');?>
 
<!--Now create the embed code at the point you want to display the video -->
<iframe width="784" height="588" src="http://www.youtube.com/embed/<?php echo $youtube_id;?>" frameborder="0" allowfullscreen></iframe>
```

</div>

</div>

To see what options are available to construct the YouTube embed code,
check out the
[documentation](https://developers.google.com/youtube/player_parameters).

\
 To display standard [YouTube thumbnail
images](http://stackoverflow.com/questions/2068344/how-to-get-thumbnail-of-youtube-video-link-using-youtube-api),
a similar technique is used. Here is some code that could be used on the
browse items page (applications/views/scripts/items/browse.php):

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
    <?php /*loop through items:  */ ?>
    <?php while (loop_items()): ?>
 
        <?php /* retrieve the YouTube identifier from the metadata  */?>
        <?php $youtube_id= item('Dublin Core', 'Identifier'); ?>
 
        <?php /* create the YouTube standard URL element  */?>
        <?php  $youtube_thumb="<img src='http://img.youtube.com/vi/$youtube_id/hqdefault.jpg'>"; ?>
 
        <?php /* use "link_to_item" to display the clickable thumbnail, linked to its item view page  */ ?>  
        <?php echo link_to_item($youtube_thumb); ?>
 
         <?php /* include the item's title */ ?>
         <h2><?php echo link_to_item(item('Dublin Core', 'Title'), array('class'=>'permalink')); ?></h2>
 
    <?php endwhile; ?>
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/YouTube\_Video\_For\_Item](YouTube_Video_For_Item.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Category](http://omeka.org/codex/Special:Categories "Special:Categories"):
<span
dir="ltr">[Recipes](http://omeka.org/c/index.php?title=Category:Recipes&action=edit&redlink=1 "Category:Recipes (page does not exist)")</span>

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

    [Page](YouTube_Video_For_Item.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/YouTube_Video_For_Item&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/YouTube_Video_For_Item&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/YouTube_Video_For_Item&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/YouTube_Video_For_Item.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/YouTube_Video_For_Item.html)
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
