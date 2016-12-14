<div id="wrap">

[Skip Navigation](item.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Functions/item)

</div>

Functions/item
==============

<div id="contentSub">

<span class="subpages">&lt;
[Functions](../Functions.html "Functions")</span>

</div>

<div id="primary">

<span id="Summary" class="mw-headline"> Summary </span>
-------------------------------------------------------

The item() helper retrieves the data for a given field of a specific
item, usually the current item on the page. As arguments passed to the
function, it requires the name of the Element Set, you can optionally
specify the particular Element Name that you're retrieving data for, and
you can pass options to the function as well.

To use the item() helper function, you must get a specific item. You can
either use the
[set\_current\_item](../Theme_API/set_current_item.html "Theme API/set current item")
helper to set the current item, or get a specific item and set it as a
variable (like `$item`) to use inside the `item` helpers. For example,
the Items Show page (example.com/items/show/21) already has the metadata
for the specific item passed to the page (in that example, item 21), so
you can use item() without any additional code. For use on the Items
Browse page (example.com/items/), see
[loop\_items()](../Theme_API/loop_items.html "Theme API/loop items"), or
for using items on other pages, see
[set\_items\_for\_loop()](../Theme_API/set_items_for_loop.html "Theme API/set items for loop").

<span id="Since" class="mw-headline"> Since </span>
---------------------------------------------------

0.10

<span id="Usage" class="mw-headline"> Usage </span>
---------------------------------------------------

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php item($elementSetName, $elementName, $options = array, $item = null); ?>
```

</div>

</div>

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

 *string* `$elementSetName` {{\#if
:   | (optional)}}
:   The element set to use. Additionally, the item() helper accepts
    'special values' here that do not correspond to an Element Set
    or Element. Those values are:
    -   `id`
    -   `item type name`
    -   `date added`
    -   `date modified`
    -   `collection name`
    -   `featured`
    -   `public`
    -   `permalink`

:   {{\#if: | Default: `{{{default}}}`}}

 *string* `$elementName` {{\#if
:   null | (optional)}}
:   The name of the element to display.
:   {{\#if: null | Default: `null`}}

 *array* `$options` {{\#if
:   array() | (optional)}}
:   Options that affect the output of the function. See the
    [Options](item.html#Options) section below for details on
    valid options.
:   {{\#if: array() | Default: `array()`}}

 *Item* `$item` {{\#if
:   null | (optional)}}
:   The Item object to work on. The default (`null`) is to use the
    current item.
:   {{\#if: null | Default: `null`}}

<span id="Options" class="mw-headline"> Options </span>
-------------------------------------------------------

Each of the option names listed below is the array key. Some options
also have different behavior based on their associated value.

`'delimiter'` 
:   *String*
:   Return the entire set of metadata as a string, where each entry is
    separated by the string delimiter.

`'index'` 
:   *Integer*
:   Return the metadata entry at the specific integer index, starting
    at 0.

`'no_escape'` 
:   *Boolean*
:   If set to true, return the text without HTML-escaping.

`'no_filter'` 
:   *Boolean*
:   Return the set of metadata without running any of the filters.

`'snippet'` 
:   *Integer*
:   Trim the length of each piece of text to the given integer length.

`'all'` 
:   *Boolean*
:   If set to true, this will retrieve an array containing all values
    for a single element rather than a specific value. If set to false,
    an array is still returned containing only a single value. If set to
    null, no array is returned.

<span id="Return_Value" class="mw-headline"> Return Value </span>
-----------------------------------------------------------------

mixed 
:   A string or an array suitable for `echo`ing to the screen, or
    looping to `echo` each value

<span id="See_Also" class="mw-headline"> See Also </span>
---------------------------------------------------------

-   [set\_current\_item()](set_current_item.html "Functions/set current item")
-   [set\_items\_for\_loop()](set_items_for_loop.html "Functions/set items for loop")
-   [loop\_items()](loop_items.html "Functions/loop items")

<span id="Examples" class="mw-headline"> Examples </span>
---------------------------------------------------------

### <span id="Special_Values" class="mw-headline"> Special Values </span>

The following will retrieve and display the ID for an item:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo item('ID'); ?>
```

</div>

</div>

### <span id="Dublin_Core_Field" class="mw-headline"> Dublin Core Field </span>

The following code will retrieve and print the Dublin Core Title from
the current item:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo item('Dublin Core', 'Title'); ?>
```

</div>

</div>

### <span id="Item_Type_Metadata_Field" class="mw-headline"> Item Type Metadata Field </span>

Similarly, following code will retrieve and print the Text field from
the Item Type Metadata set for the current item:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo item('Item Type Metadata', 'Text'); ?>
```

</div>

</div>

### <span id="Passing_Options" class="mw-headline"> Passing Options </span>

The following examples pass various options to the item() helper.

#### <span id="Snippet" class="mw-headline"> Snippet </span>

Here's how to retrieve and print the Dublin Core Description of a
specific item, and trim the number of characters to approximately 150:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo item('Dublin Core', 'Description', array('snippet'=>150)); ?>
```

</div>

</div>

#### <span id="Displaying_All_Values" class="mw-headline"> Displaying All Values </span>

Omeka allows you to store multiple values for each item field, but by
default, the item() helper will only return the first value for any
field.

The simplest way to display all the values for a field is to use the
'delimiter' option.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
    echo item('Dublin Core', 'Creator', array('delimiter' => ', '));
?>
```

</div>

</div>

This will print all the Creator values, separated by commas. The helper
includes the 'delimiter' text in between each of the different values
automatically.

If you want to do something more complex, you'll need to get an array of
the values. item() will return an array if you set the 'all' option to
'true', like so:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
    $creators = item('Dublin Core', 'Creator', array('all' => true)); 
?>
```

</div>

</div>

Note that there is no **echo** in the above example. You need to do a
little more work to print out an array. To display each value in this
array, one value per line, you can use a **foreach** block along with
**echo**:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
    $creators = item('Dublin Core', 'Creator', array('all' => true));
    foreach ($creators as $creator) {
        echo "$creator<br />";
    }
?>
```

</div>

</div>

#### <span id="Specify_an_Item_Object" class="mw-headline"> Specify an Item Object </span>

If you want to display metadata for a particular object, you can specify
that item by its ID using the `get_item_by_id` helper function, like so:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php 
  $creators = item('Dublin Core', 'Creator', array('all' => true), get_item_by_id(17)); 
?>
```

</div>

</div>

This will get an array of all the Dublin Core Creator texts for Item
\#17.

<div class="printfooter">

Retrieved from "[http://omeka.org/codex/Functions/item](item.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Category](http://omeka.org/codex/Special:Categories "Special:Categories"):
<span
dir="ltr">[Functions](../Category:Functions.html "Category:Functions")</span>

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

    [Page](item.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](../Talk:Functions/item.html)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions/item&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions/item&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](../Special:WhatLinksHere/Functions/item.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Functions/item.html)
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
