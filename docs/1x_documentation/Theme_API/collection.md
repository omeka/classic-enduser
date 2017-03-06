<div id="wrap">

[Skip Navigation](collection.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20API/collection)

</div>

Functions/collection
====================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>(Redirected from [Theme
API/collection](http://omeka.org/c/index.php?title=Theme_API/collection&redirect=no "Theme API/collection"))

</div>

<div id="primary">

<span id="Description" class="mw-headline"> Description </span>
---------------------------------------------------------------

The `collection()` helper will return the value of a specific field for
a collection object.

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo collection($fieldName, $options = array()); ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   **\$fieldName** (string) - The name of the field you'd like
    to return. Available fields for collection:
    -   Name - Returns the collection name.
    -   Description - Returns the description of the collection.
    -   ID - Returns the ID of the collection.
    -   Public (boolean) - Returns true if a collection is flagged
        as public.
    -   Featured (boolean) - Returns true if a collection is flagged
        as featured.
    -   Date Added - Returns the date the collection was added to Omeka.
    -   Date Modified - Returns the date the collection was modified.
    -   Collectors - Returns an array of collectors associated with
        a collection.
-   **\$options** (array) - One option is available:
    -   snippet - (integer). Setting `snippet` to a particular number
        will truncate the return text to that number of characters.

<span id="Examples" class="mw-headline"> Examples </span>
---------------------------------------------------------

### <span id="Show_the_Collection_Name" class="mw-headline"> Show the Collection Name </span>

Set to "true" by default, the show\_empty\_elements option allows you to
limit the fields displayed to all fields or to non-empty fields for an
item. Setting this to "false" will only display fields that have data.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
 
echo collection('Name'); 
 
?>
```

</div>

</div>

### <span id="Show_the_Description_using_Snippet" class="mw-headline"> Show the Description using Snippet </span>

The following example returns a collection's Description field, using
the snippet option to return only the first 200 characters of the
field's value:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
 
echo collection('Description', array('snippet' => 200)); 
 
?>
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/collection](../Functions/collection.html)"

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

    [Page](../Functions/collection.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/collection&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/collection&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/collection&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Functions/collection.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/collection.html)
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
