<div id="wrap">

[Skip Navigation](Removing_Fields_from_Advanced_Search.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Removing%20Fields%20from%20Advanced%20Search)

</div>

Recipes/Removing Fields from Advanced Search
============================================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

The advanced search had a lot of fields that I didn't want to display. I
wanted to limit the options to make it more user friendly, so instead of
showing over 40 options in the drop down menu, I just wanted a few key
fields.

<span id="Solution" class="mw-headline"> Solution </span>
---------------------------------------------------------

I copied application/views/scripts/items/advanced-search.php to my theme
under the items folder. Then I added some javascript to beginning of
this file. I blacklisted a lot of elements in the advanced search as
detailed at
<http://groups.google.com/group/omeka-dev/browse_thread/thread/16ca2d476c532399/e5178def4f04c2a2?hl=en%29&lnk=gst&q=customize+advnaced+search#e5178def4f04c2a2>.
After noticing that the code in that link didn't work in IE9 and had
formatting issues in Chrome, I found that .remove() works better than
.hide(). Also I figured out how to block entire groups from showing
instead of having to blacklist each element individually. After posting
my code in the forums, John Flatness had some further refinements, and
this is the final result.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo js('jquery'); ?>
<script type="text/javascript" charset="utf-8">
jQuery(document).ready(function () {
    var blackListGroups = [
        "Item Type Metadata",
        "Contribution Form"
    ];
    var blackListElements = [
        "Contributor",
        "Coverage",
        "Format",
        "Identifier",
        "Language",
        "Relation",
        "Rights",
        "Source",
        "Type"
    ];
    jQuery.each(blackListGroups, function (index, value) {
        jQuery("#advanced-0-element_id optgroup[label='" + value + "']").remove();
    });
    jQuery.each(blackListElements, function (index, value) {
        jQuery("#advanced-0-element_id option[label='" + value + "']").remove();
    });
});
</script>
```

</div>

</div>

Basically it prevents Item Type Metadata, and Contribution For fields
from showing in the advanced search. It also blacklists individual
elements as well. This makes it fairly easy to remove elements from
displaying in the advanced search.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Removing\_Fields\_from\_Advanced\_Search](Removing_Fields_from_Advanced_Search.html)"

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

    [Page](Removing_Fields_from_Advanced_Search.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/Removing_Fields_from_Advanced_Search&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Removing_Fields_from_Advanced_Search&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Removing_Fields_from_Advanced_Search&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Removing_Fields_from_Advanced_Search.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Removing_Fields_from_Advanced_Search.html)
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
