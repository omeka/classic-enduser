<div id="wrap">

[Skip Navigation](Looping_the_Omeka_Way.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Recipes/Looping%20the%20Omeka%20Way)

</div>

Recipes/Looping the Omeka Way
=============================

<div id="primary">

<span id="Problem" class="mw-headline"> Problem </span>
-------------------------------------------------------

My plugin creates new Omeka records, and I want to make theming
functions that follow Omeka's usual way of looping through them for
display.

<span id="Solution_1" class="mw-headline"> Solution 1 </span>
-------------------------------------------------------------

The usual Omeka way of looping through records to display looks roughly
like this, which would display info about items in Omeka

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php while(loop_items()): ?>
<h2><?php echo item('Dublin Core', 'Title'); ?></h2>
<!-- other code to display more metadata -->
<?php endwhile; ?>
```

</div>

</div>

The heart of this is building what you need to use Omeka's loop\_records
function, which loop\_items() calls. It takes four arguments:

\

-   \$recordType - The name of the record type, usually the class name,
    but can by string used to distinguish between loops. This lets
    multiple loops over different sets of records work
    without colliding.
-   \$records - An array of records to loop through
-   \$setCurrentRecordCallback - The name of a callback function as a
    string that sets the current record while looping

\
 The usual functions to create are the following, where you replace
'my\_record' with the name of the record type you will loop through:

\

-   set\_my\_record\_current\_record(\$record) - Sets the current record
    in the loop
-   loop\_my\_records() - Do the loop.
-   get\_my\_records\_for\_loop() - Gets the set of records to loop over
-   get\_my\_record\_current\_record() - Return the current record in
    the loop
-   set\_my\_records\_for\_loop(\$records) - Sets the records to loop
    over

The actual functions would look like:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
/**
 * This sets the current record as a property of the view being displayed
 * It is the callback that goes in loop_records (see below)
 * You can name the property whatever you want, but name it to avoid clashes
 * with other plugins
*/
 
function set_my_record_current_record($record) 
{
  __v()->myRecordCurrent = $record
}
 
function loop_my_records() 
{
  return loop_records('my_records', get_my_records_for_loop(), 'set_my_record_current_record';
}
 
/**
 * Usually, a controller will have already set the records on the view
 * but not always. If not, do your different logic and use set_my_records_for_loop
 */
function get_my_records_for_loop()
{
  return __v()->myRecords;
}
 
/**
 * Sets the records so the are available to get_my_records_for_loop() when
 * called in loop_my_records (see above)
 * Often, this is not needed because your controller will have set this property,
 * but some situations might call for a different way of setting the records
 */
 
function set_my_records_for_loop($records)
{
 __v()->myRecords = $records;
 
}
```

</div>

</div>

### <span id="Functions_Used" class="mw-headline"> Functions Used </span>

-   [loop\_records()](http://omeka.org/c/index.php?title=Functions/loop_records&action=edit&redlink=1 "Functions/loop records (page does not exist)")

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Recipes/Looping\_the\_Omeka\_Way](Looping_the_Omeka_Way.html)"

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

    [Page](Looping_the_Omeka_Way.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Recipes/Looping_the_Omeka_Way&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Recipes/Looping_the_Omeka_Way&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Recipes/Looping_the_Omeka_Way&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](../Special:WhatLinksHere/Recipes/Looping_the_Omeka_Way.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](../Special:RecentChangesLinked/Recipes/Looping_the_Omeka_Way.html)
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
