<div id="wrap">

[Skip Navigation](show_item_metadata.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/show%20item%20metadata)

</div>

Functions/show item metadata
============================

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>

</div>

<div id="primary">

<div
style="background:gold; border:1px solid goldenrod; padding: 1em 1em 0 1em; margin-bottom: 1em;">

<span id="This_page_is_outdated" class="mw-headline">This page is outdated</span> {#this-page-is-outdated style="color:#404040; border-bottom: none"}
---------------------------------------------------------------------------------

The information on this page concerns an old or obsolete version of
Omeka. If you are using a more recent version, instead see [`metadata`
on Read the
Docs](http://omeka.readthedocs.org/en/latest/Reference/libraries/globals/metadata.html).

</div>

<span id="Description" class="mw-headline"> Description </span>
---------------------------------------------------------------

The `show_item_metadata()` helper inserts all the metadata field
available for an item in an Omeka archive. It is primary used in the
`show.php` file in a public theme.

`show_item_metadata` has several options available:

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo show_item_metadata($options = array(), $item = null); ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

-   **\$options** (array) - Three options are available:
    -   show\_empty\_elements - (bool|string). Setting to false will
        prevent empty fields from being displayed. Setting to a text
        string will display empty fields, and display the
        string entered.
    -   show\_element\_sets - An array of element sets (by name)
        to display.
    -   return\_type - array or html. Defaults to html.

<!-- -->

-   **\$item** - Item object or null (default). If null, the current
    item in the loop is used.

<span id="Examples" class="mw-headline"> Examples </span>
---------------------------------------------------------

### <span id="Hide_Empty_Elements" class="mw-headline"> Hide Empty Elements </span>

Set to "true" by default, the show\_empty\_elements option allows you to
limit the fields displayed to all fields or to non-empty fields for an
item. Setting this to "false" will only display fields that have data.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
 
echo show_item_metadata(array('show_empty_elements' => false)); 
 
?>
```

</div>

</div>

### <span id="Change_the_Empty_Element_String" class="mw-headline"> Change the Empty Element String </span>

If you'd like to change the text displayed for empty fields, pass the
use the text of the string for the show\_empty\_elements option.
Example:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
 
echo show_item_metadata(array('show_empty_elements' => 'Empty')); 
 
?>
```

</div>

</div>

This will display "Empty" instead of "\[no text\]" in your public theme.

### <span id="Display_Specific_Element_Sets" class="mw-headline"> Display Specific Element Sets </span>

If you'd like to display specific element sets, pass the list of sets as
an array to the \`show\_element\_sets\` option. The following example
would display only the Item Type Metadata element set:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
 
echo show_item_metadata(
    array(
        'show_element_sets' => array(
            'Item Type Metadata'
        )
    )
); 
 
?>
```

</div>

</div>

<span id="Using_show_item_metadata_for_a_specific_item" class="mw-headline"> Using show\_item\_metadata for a specific item </span>
-----------------------------------------------------------------------------------------------------------------------------------

If you'd like to use `show_item_metadata` to display the metadata of a
specific item, you must first use the
[get\_item\_by\_id](../Theme_API/get_item_by_id.html "Theme API/get item by id")
helper to get the item object of a specific item. The following example
sets the 'show\_empty\_elements' to false, and displays the metadata for
an item with a ID value of '44':

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php
 
$item = get_item_by_id(44);
 
echo show_item_metadata(array(), $item);
 
?>
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Functions/show\_item\_metadata](show_item_metadata.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Category](http://omeka.org/codex/Special:Categories "Special:Categories"):
<span dir="ltr">[Obsolete
pages](http://omeka.org/c/index.php?title=Category:Obsolete_pages&action=edit&redlink=1 "Category:Obsolete pages (page does not exist)")</span>

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

    [Page](show_item_metadata.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Functions/show_item_metadata&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/show_item_metadata&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/show_item_metadata&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Functions/show_item_metadata.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/show_item_metadata.html)
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
