<div id="wrap">

[Skip Navigation](Default_Item_Thumbnail_Images.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Default%20Item%20Thumbnail%20Images)

</div>

Recipes/Default Item Thumbnail Images
=====================================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

I wanted to make a gallery of images for the browse page, but I had a
number of items without images and wanted a uniform look.

<span id="Solution" class="mw-headline"> Solution </span>
---------------------------------------------------------

I changed the item links to show a default image if there wasn't a
thumbnail for the item. For variety, I assigned thumbnails for different
items by item type as well.

### <span id="Functions_Used" class="mw-headline"> Functions Used </span>

-   [link\_to\_item()](../Functions/link_to_item.html "Functions/link to item")
-   [img()](../Functions/img.html "Functions/img")
-   [item\_has\_type()](../Functions/item_has_type.html "Functions/item has type")

By default the items browse page (items/browse.php) displays the item
thumbnail, title, description and tags.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php while (loop_items()): ?>
    <div class="item hentry">
        <div class="item-meta">
        <?php if (item_has_thumbnail()): ?>
            <div class="item-img">
                <?php echo link_to_item(item_square_thumbnail()); ?>              
            </div>
    <?php endif; ?>
 
            <h2><?php echo link_to_item(item('Dublin Core', 'Title'), array('class'=>'permalink')); ?></h2>
 
        <?php if ($text = item('Item Type Metadata', 'Text', array('snippet'=>250))): ?>
            <div class="item-description">
                <p><?php echo $text; ?></p>
            </div>
        <?php elseif ($description = item('Dublin Core', 'Description', array('snippet'=>250))): ?>
            <div class="item-description">
                <?php echo $description; ?>
            </div>
        <?php endif; ?>
 
        <?php if (item_has_tags()): ?>
            <div class="tags"><p><strong>Tags:</strong>
                <?php echo item_tags_as_string(); ?></p>
            </div>
        <?php endif; ?>
 
        <?php echo plugin_append_to_items_browse_each(); ?>
 
        </div><!-- end class="item-meta" -->
    </div><!-- end class="item hentry" -->            
<?php endwhile; ?>
```

</div>

</div>

I only want the thumbnail and title, so I removed everything else.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php while (loop_items()): ?>
    <div class="item hentry">
        <div class="item-meta">
        <?php if (item_has_thumbnail()): ?>
            <div class="item-img">
                <?php echo link_to_item(item_square_thumbnail()); ?>                      
            </div>
    <?php endif; ?>
 
            <h2><?php echo link_to_item(item('Dublin Core', 'Title'), array('class'=>'permalink')); ?></h2>
 
            <?php echo plugin_append_to_items_browse_each(); ?>
 
        </div><!-- end class="item-meta" -->
    </div><!-- end class="item hentry" -->            
<?php endwhile; ?>`
```

</div>

</div>

First I assigned a default image for any item without a thumbnail.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<div class="item-img">
<?php 
if (item_has_thumbnail()):
    echo link_to_item(item_square_thumbnail());
else:
    echo link_to_item('<img src="'.img('default_icon.jpg').'" />');
endif;
?>
</div>
```

</div>

</div>

This else statement changes the link text in the
[link\_to\_item()](../Functions/link_to_item.html "Functions/link to item")
function.

If the item does not have a thumbnail, the item link 'text' is the image
'default\_icon.jpg'. The [img()](../Functions/img.html "Functions/img")
function uses files uploaded to my themes images folder.
(MyOmekaInstall/themes/MyTheme/images)

The
[item\_square\_thumbnail()](../Functions/item_square_thumbnail.html "Functions/item square thumbnail")
function prints an img src tag for the thumbnail, but the
[img()](../Functions/img.html "Functions/img") function does not. So, I
had to made a string for the img src. If you were using this often, you
may want to make your own custom function for default images.

Next, I added defaults for documents, videos, and audio.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<div class="item-img">
<?php
if (item_has_thumbnail()):
    echo link_to_item(item_square_thumbnail());   
elseif (item_has_type('Document')):
    echo link_to_item('<img src="'.img('document_icon.jpg').'" />');
elseif (item_has_type('Moving Image')):
    echo link_to_item('<img src="'.img('video_icon.jpg').'" />');
elseif (item_has_type('Sound')):
    echo link_to_item('<img src="'.img('audio_icon.jpg').'" />');
else:
    echo link_to_item('<img src="'.img('default_icon.jpg').'" />');
endif;
?>
</div>
```

</div>

</div>

Warning: If you do not have the files uploaded or do not have the right
names for files when you use them in the img() function, you will
receive an error in Omeka.

Also,
[item\_has\_type()](../Functions/item_has_type.html "Functions/item has type")
uses items that are assigned an item type in the admin panel of Omeka,
it does not determine the item type by the uploaded file type.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Default\_Item\_Thumbnail\_Images](Default_Item_Thumbnail_Images.html)"

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

    [Page](Default_Item_Thumbnail_Images.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/Default_Item_Thumbnail_Images&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Default_Item_Thumbnail_Images&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Default_Item_Thumbnail_Images&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Default_Item_Thumbnail_Images.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Default_Item_Thumbnail_Images.html)
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
