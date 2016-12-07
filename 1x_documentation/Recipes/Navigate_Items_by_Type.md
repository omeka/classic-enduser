<div id="wrap">

[Skip Navigation](Navigate_Items_by_Type.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Navigate%20Items%20by%20Type)

</div>

Recipes/Navigate Items by Type
==============================

<div id="primary">

<span id="Problem" class="mw-headline">Problem</span>
-----------------------------------------------------

I want to organize my site by item type, so I need users to easily be
able to navigate between different item types without having to go
through the advanced search page.

<span id="Solution" class="mw-headline">Solution</span>
-------------------------------------------------------

### <span id="Functions_Used" class="mw-headline">Functions Used</span>

-   [nav()](../Functions/nav.html "Functions/nav")

We need to create a function that will get the right URLs when given the
names of the item types we want to browse by. This way, we don't need to
manually figure out the correct link for each item type.

This function should go in the theme's **custom.php** file. Some themes
already have a **custom.php** file, and some do not. If the theme you
are using does not have a **custom.php** file, create it yourself in the
root of the theme directory.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
/**
 * Get an array of item_browse URLs, suitable for use with nav().
 *
 * @param array $itemTypes Array of item type names.
 * @param array $browseParams (optional) Additional browse parameters,
 *  will be used in every URL.
 * @return array
 */
function mytheme_items_browse_by_types($itemTypes, $browseParams = array())
{
    $urls = array();
    $table = get_db()->getTable('ItemType');
    foreach ($itemTypes as $typeName) {
        $itemType = $table->findByName($typeName);
        $urls[$typeName] = uri('items/browse', array('type' => $itemType->id) + $browseParams);
        release_object($itemType);
    }
 
    return $urls;
}
```

</div>

</div>

Now, you can use this function wherever you want users to be able to
navigate by item type. An easy way to do this is to use the
[nav()](../Functions/nav.html "Functions/nav") helper, which will output
the HTML for a list of links.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$types = array('Document', 'Still Image');
echo nav(mytheme_items_browse_by_types($types));
```

</div>

</div>

The second parameter allows you to add browse parameters to every URL.
You could use that parameter to create the navigation shown in the
["Browse Within a Collection"
recipe](Browse_Within_A_Collection.html "Recipes/Browse Within A Collection")
without having to look up the correct ID for each type yourself.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$types = array('Document', 'Still Image');
echo nav(mytheme_items_browse_by_types($types, array('collection' => collection('id')));
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Navigate\_Items\_by\_Type](Navigate_Items_by_Type.html)"

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

    [Page](Navigate_Items_by_Type.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/Navigate_Items_by_Type&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Navigate_Items_by_Type&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Navigate_Items_by_Type&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Navigate_Items_by_Type.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Navigate_Items_by_Type.html)
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
