<div id="wrap">

[Skip Navigation](Linking_to_Related_Items.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Linking%20to%20Related%20Items)

</div>

Recipes/Linking to Related Items
================================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

I wanted to create a way to link individual items to a larger group of
related items. For example, we have yearbook pictures from the early
1900s on our site as individual items. We wanted to add a link to the
item show page that would bring the user to all of the related images
from that specific year.

<span id="Solution" class="mw-headline"> Solution </span>
---------------------------------------------------------

Initially, I thought of taking part of the titles, and creating search
links from the title. Also I tried using the dates as a search limiter.
However, those methods often produced inconsistent results, with more
images than I wanted. The thought of manually grouping items that are
related also didn't seem feasible.

Eventually, I decided that using the identifier field as my search
limiter was my best option. We had generally uploaded items in batches
with the csv import, and items that shared part of their identifier were
often closely related. So 1915 medical yearbook images had the
identifiers of 1915M\_01, 1915M\_02, etc. Basically, I needed to get rid
of the part of the identifier that was specific to the item, usually the
last two or three numbers, so that my search term was just the base of
the identifier. I want 1915M\_ instead of 1915M\_01. The identifier
1915M\_01 would return just that one item if used as a search term.

However, I also noticed that we don't have standard identifiers, some
looked like 06-15-01 and others looked like 1916D\_01. So my code had to
take that into account.

The following code is placed in my custom.php file. It looks at the
item's identifier for a "-" or "\_". Then it finds the last instance of
that character, and returns the string before the character. So
06-1940-03 becomes 06-1940-. Then it fills in the search link with that
info. We decided to place this link at the end of the description field,
but it could easily go elsewhere.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
add_filter(array('Display', 'Item', 'Dublin Core', 'Description'), 'mytheme_display_description');
 
function mytheme_display_description($description, $item, $elementTextRecord)
{
$text = '';
$text.=$description;
$itemurl=uri(); // This gets the current page's url
if (stristr($itemurl,'show')){ //This prevents the link from showing on the browse pages
$myid=item('Dublin Core', 'Identifier');
if (stristr($myid,'-')){
$myid= substr($myid,0,strrpos($myid,'-')+strlen('-'));}//Finds last "-" and returns string preceding it. Removes individual aspect of item's identifier.
if (stristr($myid,'_')){
$myid= substr($myid,0,strrpos($myid,'_')+strlen('_'));}
$link = uri("items/browse?search=&advanced[0][element_id]=43&advanced[0][type]=contains&advanced[0][terms]=" . $myid . "&submit_search=Search");//On our site element_id=43 corresponds to the identifier element, but it might be different on other sites.
$text.='&nbsp<a class="browse-link" href="' . $link . '" title="Browse Related Items">Browse related items</a>';}
return $text;
 
}
```

</div>

</div>

I found how to return the part of a string preceding the last instance
of a character at
<http://www.php.net/manual/en/function.strrchr.php#60075>. There might
be an easier way, but it works.

### <span id="Functions_Used" class="mw-headline"> Functions Used </span>

-   [Element\_Display\_Filter](../Filters/Element_Display_Filter.html "Filters/Element Display Filter")
-   [uri()](../Functions/uri.html "Functions/uri")
-   [item()](../Functions/item.html "Functions/item")

<http://www.php.net/manual/en/function.stristr.php>\
 <http://www.php.net/manual/en/function.substr.php>\
 <http://www.php.net/manual/en/function.strpos.php>\
 <http://www.php.net/manual/en/function.strlen.php>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Linking\_to\_Related\_Items](Linking_to_Related_Items.html)"

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

    [Page](Linking_to_Related_Items.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/Linking_to_Related_Items&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Linking_to_Related_Items&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Linking_to_Related_Items&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Linking_to_Related_Items.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Linking_to_Related_Items.html)
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
