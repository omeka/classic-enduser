<div id="wrap">

[Skip
Navigation](Using_Search_Results_to_Create_Custom_Next_and_Previous_Links.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Using%20Search%20Results%20to%20Create%20Custom%20Next%20and%20Previous%20Links)

</div>

Recipes/Using Search Results to Create Custom Next and Previous Links
=====================================================================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

When you search for a term, you get a list of results on the item browse
page, and the term you searched is displayed in the search box. When you
view an individual item of this search, and then click next or previous
links, you do not get the next or previous item in the search. Instead
you get the next or previous item ID in the entire collection.

<span id="Solution" class="mw-headline"> Solution </span>
---------------------------------------------------------

I noticed if I added the search string from the url of the item browse
page to the item show page the search term appears in the search box.

So omeka/items/show/123 would be
omeka/items/show/123?search=search+term&submit\_search=Search. The
following modifications create next and previous links based on items in
the search.

### <span id="Functions_Used" class="mw-headline"> Functions Used </span>

-   [item\_uri()](../Functions/item_uri.html "Functions/item uri")
-   [get\_items()](../Functions/get_items.html "Functions/get items")
-   [set\_current\_item()](../Functions/set_current_item.html "Functions/set current item")
-   [get\_item\_by\_id()](../Functions/get_item_by_id.html "Functions/get item by id")

The first thing I did was modify the browse.php file to create links to
items that would have the search term. I used a conditional statement to
have these links only appear when a search has been run.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
if (item_has_thumbnail()):
    if($search=$_GET['search']): 
        $imagelink = item_uri().'?search='.$_GET['search'].'&submit_search=Search';
        echo '<div class="item-img"><a href="'.$imagelink.'">'.item_square_thumbnail(array('alt'=>item('Dublin Core', 'Title'))).'</a></div>'; 
    else: 
        echo '<div class="item-img">'.link_to_item(item_square_thumbnail(array('alt'=>item('Dublin Core', 'Title')))).'</div>';
    endif;
endif;
if($search=$_GET['search']):
    $searchlink = item_uri().'?search='.$_GET['search'].'&submit_search=Search';
    echo '<h2><a href="'.$searchlink.'">'.item('Dublin Core','Title').'</a></h2>'; 
else: 
    echo '<h2>'.link_to_item(item('Dublin Core', 'Title'), array('class'=>'permalink')).'</h2>'; 
endif;
?>
```

</div>

</div>

Next I created a custom function called custom\_next\_previous(), which
determines if the item belongs to a larger search group, finds its
position, and creates appropriate next and previous links. I've added
comments to the code to explain how it works.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
function custom_next_previous()
{
    //Starts a conditional statement that determines a search has been run
    if ($search = $_GET['search']) {
        // Sets the current item ID to the variable $current
        $current = item('id');
 
        // Get an array of all the items from the search, and all the IDs
        $list = get_items(array('search'=>$search),total_results());
        foreach ($list as &$value) {
            $itemIds[] = $value->id;
        }
 
        // Find where we currently are in the result set
        $key = array_search($current, $itemIds);
 
        // If we aren't at the beginning, print a Previous link
        if ($key > 0) {
            $previousItem = $list[$key - 1];
            $previousUrl = item_uri('show', $previousItem) . '?' . $_SERVER['QUERY_STRING'];
            echo '<li><a href="' . $previousUrl . '">Previous Item</a></li>';
        }
 
        // If we aren't at the end, print a Next link
        if ($key < count($list) - 1) {
            $nextItem = $list[$key + 1];
            $nextUrl = item_uri('show', $nextItem) . '?' . $_SERVER['QUERY_STRING'];
            echo '<li class="next"><a href="' . $nextUrl . '">Next Item</a></li>';
        }
    } else {
        // If a search was not run, then the normal next/previous navigation is displayed.
        echo '<li>'.link_to_previous_item('Previous Item').'</li>';
        echo '<li class="next">'.link_to_next_item('Next Item').'</li>';
    }
}
```

</div>

</div>

Finally, I replaced the following in the items/show.php file:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
 <ul class="item-pagination navigation">
    <li><?php echo link_to_previous_item('Previous Item'); ?></li>
    <li class="next">   <?php echo link_to_next_item('Next Item'); ?></li>
 </ul>
```

</div>

</div>

with a call to my custom\_next\_previous function:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<ul class="item-pagination navigation">
    <?php custom_next_previous(); ?>
</ul>
```

</div>

</div>

This modification works for simple searches.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Using\_Search\_Results\_to\_Create\_Custom\_Next\_and\_Previous\_Links](Using_Search_Results_to_Create_Custom_Next_and_Previous_Links.html)"

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

    [Page](Using_Search_Results_to_Create_Custom_Next_and_Previous_Links.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/Using_Search_Results_to_Create_Custom_Next_and_Previous_Links&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Using_Search_Results_to_Create_Custom_Next_and_Previous_Links&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Using_Search_Results_to_Create_Custom_Next_and_Previous_Links&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Using_Search_Results_to_Create_Custom_Next_and_Previous_Links.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Using_Search_Results_to_Create_Custom_Next_and_Previous_Links.html)
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
