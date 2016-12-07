<div id="wrap">

[Skip Navigation](Multiple_Featured_Collections.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Multiple%20Featured%20Collections)

</div>

Recipes/Multiple Featured Collections
=====================================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

I'd like to have multiple featured collections displayed on the front
page.

<span id="Solution_1" class="mw-headline"> Solution 1 </span>
-------------------------------------------------------------

It looks at first like you could just call

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
display_random_featured_collection()
```

</div>

</div>

as many times as you need, but this has two problems. First, it will
output a header multiple times, too. Second, unless you have many many
featured collections, chances are pretty good that you will end up
showing duplicates.

Instead, then, we'll need to create our own function to do things in a
way that mimics that function. Here it is in its original form:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
function display_random_featured_collection()
{
    $featuredCollection = random_featured_collection();
    $html = '<h2>Featured Collection</h2>';
    if ($featuredCollection) {
        $html .= '<h3>' . link_to_collection($collectionTitle, array(), 'show', $featuredCollection) . '</h3>';
        if ($collectionDescription = collection('Description', array('snippet'=>150), $featuredCollection)) {
            $html .= '<p class="collection-description">' . $collectionDescription . '</p>';
        }
 
    } else {
        $html .= '<p>No featured collections are available.</p>';
    }
    return $html;
}
```

</div>

</div>

Notice that it starts by calling another function,
random\_featured\_collection(), that just gets a collection, but does
not return any html for display. We'll need to chase down how that
function works, too, because we really want multiple featured
collections, not just one.

random\_featured\_collection ultimately depends on some deeper-workings
of Omeka, in its features for querying the database. There is a class
called CollectionTable that does the job with this method:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
public function findRandomFeatured()
{    $select=$this->getSelect()->where("c.featured=1")->order("RAND()")->limit(1);        
return $this->fetchObject($select);
}
```

</div>

</div>

And so, we need to recreate what happens here in our new replacement for
display\_random\_featured\_collection().

It's pretty clear that the reason we only get one collection back is due
to that "limit(1)" part at the end. So, we need to recreate how Omeka
gets this data from the database, and make the little adjustment.

Whenever we need to get data from a specific table, the Omeka way is to
get a reference to the database itself, then to the table:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
    $collectionTable = get_db()->getTable('Collection');
```

</div>

</div>

Now we can follow the model of findRandomFeatured()

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
    $collectionTable = get_db()->getTable('Collection');
    $select = $collectionTable->getSelect()->where("c.featured = 1")->order("RAND()")->limit(3);
    $featuredCollections = $collectionTable->fetchObjects($select);
```

</div>

</div>

So, we've bypassed the usual function for getting a random featured
collections by going straight to the database tables.

From there, we just need to rewrite the rest of
display\_random\_featured() to loop through the collections and display
them instead of just showing the one. Here's the complete code for the
function:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
function my_theme_display_random_featured_collections()
{
    $collectionTable = get_db()->getTable('Collection');
    $select = $collectionTable->getSelect()->where("c.featured = 1")->order("RAND()")->limit(3);
    $featuredCollections = $collectionTable->fetchObjects($select);
 
    $html = '<h2>Sample Collections</h2>';
 
 
    if(count($featuredCollections) != 0) {
      foreach($featuredCollections as $featuredCollection) {
    if ($featuredCollection) {
        $html .= '<h3>' . link_to_collection($collectionTitle, array(), 'show', $featuredCollection) . '</h3>';
        if ($collectionDescription = collection('Description', array('snippet'=>150), $featuredCollection)) {
        $html .= '<p class="collection-description">' . $collectionDescription . '</p>';
        }
 
    }
      }
    } else {
      $html .= '<p>No featured collections are available.</p>';
    }
 
    return $html;
}
```

</div>

</div>

\

### <span id="Functions_Used" class="mw-headline"> Functions Used </span>

-   [display\_random\_featured\_collection()](../Functions/display_random_featured_collection.html "Functions/display random featured collection")
-   [get\_db()](http://omeka.org/c/index.php?title=Functions/get_db&action=edit&redlink=1 "Functions/get db (page does not exist)")

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Multiple\_Featured\_Collections](Multiple_Featured_Collections.html)"

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

    [Page](Multiple_Featured_Collections.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/Multiple_Featured_Collections&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Multiple_Featured_Collections&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Multiple_Featured_Collections&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Multiple_Featured_Collections.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Multiple_Featured_Collections.html)
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
