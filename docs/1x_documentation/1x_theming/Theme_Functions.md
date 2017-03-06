---
title:  Theme Functions for Omeka 0.9
---
*Please Note: The following documentation reflects theme functions included in Omeka version 0.9.*.

<span id="css.28.29" class="mw-headline"> css() </span>
-------------------------------------------------------

Returns the path to a css file in your public template, usually located
in `themes/yourtheme/css`

Available arguments:

-   \$file: the name of the file.

``
    <link rel="stylesheet" href="<?php echo css('screen'); ?>" />

Returns:

``
    <link rel="stylesheet" 
          href="http://example.com/themes/yourtheme/screen.css" />

<span id="collection.28.29" class="mw-headline"> collection() </span>
---------------------------------------------------------------------

Returns a specific collection by ID

<span id="collections.28.29" class="mw-headline"> collections() </span>
-----------------------------------------------------------------------

Returns an array of collections.

<span id="common.28.29" class="mw-headline"> common() </span>
-------------------------------------------------------------

Include a partial template within a theme page.

Available arguments:

-   \$file: The name of the file (stored in the 'common' directory)
-   \$vars: One or more variables to pass to the partial file. These are
    passed by giving an array of key =&gt; value pairs.

Example:

``
    <?php common('archive-nav', array('tags'=>$item->Tags)); ?>

<span id="current_user.28.29" class="mw-headline"> current\_user() </span>
--------------------------------------------------------------------------

Returns the User object for the currently logged-in user. The User
object can be used to display information for the user such as
first/last name, email address, username, and role (admin, researcher,
etc.). This function returns false if there is no user currently logged
in.

Example:

``
    <?php if($user = current_user()): ?>
    <p>Hello <?php echo $user->first_name; ?>!</p>  
    You are registered under the following email address: <?php echo $user->email; ?>
    <?php endif; ?>

<span id="display_empty.28.29" class="mw-headline"> display\_empty() </span>
----------------------------------------------------------------------------

Echoes a fully escaped and html-safe string, or if the string is empty,
it displays a placeholder value.

Available arguments:

-   \$val: Any string.
-   \$alternative: Default value of "\[Empty\]", which will display if
    the given string is empty.

Example:

``
    <?php echo display_empty($item->description); ?>

Outputs:

``
    <p>Here is the description</p>

<span id="entities.28.29" class="mw-headline"> entities() </span>
-----------------------------------------------------------------

Returns an array of entities.

<span id="flash.28.29" class="mw-headline"> flash() </span>
-----------------------------------------------------------

Returns any error messages, alerts, etc. that Omeka would need to
display on a given page.

Available arguments:

-   \$wrap: (true/false) Whether or not to wrap the message in a div
    with an appropriate class, i.e. ``

        <div class="error">Msg</div>

    Default value is true.

Example:

``
    <?php echo flash(); ?>

Outputs:

``
    <div class="alert">You are not wearing pants!</div>

\

<span id="foot.28.29" class="mw-headline"> foot() </span>
---------------------------------------------------------

Include the footer for the template, which is most commonly 'footer.php'
in the common directory.

For more information, see [\#head()](Theme_Functions.html#head.28.29)

<span id="fullsize.28.29" class="mw-headline"> fullsize() </span>
-----------------------------------------------------------------

<span id="h.28.24str_.5B.2C.24allowedTags.5D.29" class="mw-headline"> h(\$str \[,\$allowedTags\]) </span>
---------------------------------------------------------------------------------------------------------

A wrapper for htmlentities() with some more interesting behavior. h()
escapes a piece of text to make it html safe, but it leaves intact a
certain subset of tags which is specified as an argument. \$allowedTags
should be a string of pipe separated tags, for example,
"i|em|b|strong|del|span". By default, i, em, b, strong, del, and span
tags are allowed.

<span id="has_collectors.28.29" class="mw-headline"> has\_collectors() </span>
------------------------------------------------------------------------------

Determine whether or not a specific collection has collectors.

Available arguments:

-   \$collection: The collection that is to be tested.

Returns: boolean

Example:

``
    <?php if(has_collectors($collection) ): ?>
        <h3>Collector(s)</h3>
            <div class="field-value">
                <ul><?php foreach($collection->Collectors as $collector):?>
                    <li><?php echo nls2p(h($collector->name)); ?></li>
                    <?php endforeach; ?>
                </ul>
            </div>
    <?php endif; ?>

<span id="has_collection.28.29" class="mw-headline"> has\_collection() </span>
------------------------------------------------------------------------------

Determine whether or not a specific Item has a Collection associated
with it.

Available arguments:

-   \$item: The Item object that is to be tested.

Returns: boolean

<span id="has_files.28.29" class="mw-headline"> has\_files() </span>
--------------------------------------------------------------------

Determine whether or not an item has any files associated with it.

Example:

``
    <?php if(has_files($item): ?>
    <div id="files-for-item">
    This div only shows up if the Item has some files!
    </div>
    <?php endif; ?>

<span id="has_permission.28.29" class="mw-headline"> has\_permission() </span>
------------------------------------------------------------------------------

<span id="has_tags.28.29" class="mw-headline"> has\_tags() </span>
------------------------------------------------------------------

<span id="has_thumbnail.28.29" class="mw-headline"> has\_thumbnail() </span>
----------------------------------------------------------------------------

<span id="has_type.28.29" class="mw-headline"> has\_type() </span>
------------------------------------------------------------------

<span id="head.28.29" class="mw-headline"> head() </span>
---------------------------------------------------------

<span id="img.28.29" class="mw-headline"> img() </span>
-------------------------------------------------------

Returns a path to a file in the "images" directory in a public theme.

Example:

``
    <img src="<?php echo img('image.jpg'); ?>" />

<span id="is_current.28.29" class="mw-headline"> is\_current() </span>
----------------------------------------------------------------------

<span id="item.28.29" class="mw-headline"> item() </span>
---------------------------------------------------------

Returns a specific item by ID.

<span id="items.28.29" class="mw-headline"> items() </span>
-----------------------------------------------------------

Returns an array of items.

<span id="items_search_form.28.29" class="mw-headline"> items\_search\_form() </span>
-------------------------------------------------------------------------------------

Returns an advanced search form for searching items. Function has three
arguments: The first are any attributes to the &lt;form&gt; element you
want to add (id, class, et cetera); the second is the path you want the
search results to go (usually items/browse); the third allows you to set
the toggle for advanced search to true or false (true by default).

Example:

``
    <?php 
    echo items_search_form(array('id'=>'searchform'), uri('items/browse'), false); ?>

<span id="link_to.28.29" class="mw-headline"> link\_to() </span>
----------------------------------------------------------------

<span id="link_to_collection.28.29" class="mw-headline"> link\_to\_collection() </span>
---------------------------------------------------------------------------------------

<span id="link_to_exhibit.28.29" class="mw-headline"> link\_to\_exhibit() </span>
---------------------------------------------------------------------------------

<span id="link_to_home_page.28.29" class="mw-headline"> link\_to\_home\_page() </span>
--------------------------------------------------------------------------------------

Returns an html anchor to omeka's WEB\_ROOT.

Available arguments:

-   \$text: the text to be used as the link.
-   \$props: an array of properties to be used as tag attributes.

``
    <?php echo link_to_home_page('View Public Site', array('id'=>'public-link')); ?>

Returns:

``
    <a href="http://example.com/omeka" id="public-link">View Public Site</a>

<span id="link_to_item.28.29" class="mw-headline"> link\_to\_item() </span>
---------------------------------------------------------------------------

<span id="link_to_thumbnail.28.29" class="mw-headline"> link\_to\_thumbnail() </span>
-------------------------------------------------------------------------------------

<span id="link_to_fullsize.28.29" class="mw-headline"> link\_to\_fullsize() </span>
-----------------------------------------------------------------------------------

<span id="link_to_next_item.28.29" class="mw-headline"> link\_to\_next\_item() </span>
--------------------------------------------------------------------------------------

<span id="link_to_previous_item.28.29" class="mw-headline"> link\_to\_previous\_item() </span>
----------------------------------------------------------------------------------------------

<span id="nav.28.29" class="mw-headline"> nav() </span>
-------------------------------------------------------

Generate a navigation list

Available arguments:

-   \$links: array Key = Text of Navigation, Value = Link

``
    <?php echo nav(array('Items' => uri('items'),
       'Exhibits' => uri('exhibits'))); ?>"

Returns:

``
    <li class="nav-items current">
      <a href="http://example.com/omeka/items">Items</a></li>
    <li class="nav-exhibits">
      <a href="http://example.com/omeka/exhibits">Exhibits</a></li>

<span id="nls2p.28.29" class="mw-headline"> nls2p() </span>
-----------------------------------------------------------

Turns two or more consecutive line feeds within a string into a
&lt;p&gt; ... &lt;/p&gt; combination.

Example:

``
    <?php echo nls2p("This is a test\n\n"); ?>

Result:

``
    <p>This is at test</p>

<span id="pagination_links.28.29" class="mw-headline"> pagination\_links() </span>
----------------------------------------------------------------------------------

<span id="path_to.28.29" class="mw-headline"> path\_to() </span>
----------------------------------------------------------------

<span id="people.28.29" class="mw-headline"> people() </span>
-------------------------------------------------------------

Returns an array of people.

<span id="random_featured_item.28.29" class="mw-headline"> random\_featured\_item() </span>
-------------------------------------------------------------------------------------------

Returns a random item that has been checked "featured."

<span id="recent_collections.28.29" class="mw-headline"> recent\_collections() </span>
--------------------------------------------------------------------------------------

Returns an array of collections most recently added to your Omeka
installation.

Available arguments:

-   \$num: the number of collections to return in the array. Default
    = 10.

<span id="recent_exhibits.28.29" class="mw-headline"> recent\_exhibits() </span>
--------------------------------------------------------------------------------

Returns an array of exhibits most recently added to your Omeka
installation.

Available arguments:

-   \$num: the number of exhibits to return in the array. Default = 10.

<span id="recent_items.28.29" class="mw-headline"> recent\_items() </span>
--------------------------------------------------------------------------

Returns an array of items most recently added to your Omeka
installation.

Available arguments:

-   \$num: the number of items to return in the array. Default = 10.

<span id="recent_tags.28.29" class="mw-headline"> recent\_tags() </span>
------------------------------------------------------------------------

Returns an array of tags most recently added to your Omeka installation.

Available arguments:

-   \$num: the number of tags to return in the array. Default = 30.

<span id="settings.28.29" class="mw-headline"> settings() </span>
-----------------------------------------------------------------

<span id="snippet.28.29" class="mw-headline"> snippet() </span>
---------------------------------------------------------------

<span id="square_thumbnail.28.29" class="mw-headline"> square\_thumbnail() </span>
----------------------------------------------------------------------------------

<span id="src.28.29" class="mw-headline"> src() </span>
-------------------------------------------------------

<span id="tag_cloud.28.29" class="mw-headline"> tag\_cloud() </span>
--------------------------------------------------------------------

<span id="tag_string.28.29" class="mw-headline"> tag\_string() </span>
----------------------------------------------------------------------

<span id="tags.28.29" class="mw-headline"> tags() </span>
---------------------------------------------------------

Returns an array of tags.

<span id="text_to_id.28.29" class="mw-headline"> text\_to\_id() </span>
-----------------------------------------------------------------------

<span id="theme_path.28.29" class="mw-headline"> theme\_path() </span>
----------------------------------------------------------------------

<span id="thumbnail.28.29" class="mw-headline"> thumbnail() </span>
-------------------------------------------------------------------

<span id="total_collections.28.29" class="mw-headline"> total\_collections() </span>
------------------------------------------------------------------------------------

Returns the total number of collections added in your Omeka
installation.

<span id="total_items.28.29" class="mw-headline"> total\_items() </span>
------------------------------------------------------------------------

Returns the total number of items added to your Omeka installation

<span id="total_results.28.29" class="mw-headline"> total\_results() </span>
----------------------------------------------------------------------------

Returns the total number of results for a query.

<span id="total_tags.28.29" class="mw-headline"> total\_tags() </span>
----------------------------------------------------------------------

Returns the total number of tags added to your Omeka installation.

<span id="total_types.28.29" class="mw-headline"> total\_types() </span>
------------------------------------------------------------------------

Returns the total number of types added to your Omeka installation.

<span id="total_users.28.29" class="mw-headline"> total\_users() </span>
------------------------------------------------------------------------

Returns the total number of of users added to your Omeka installation.

<span id="type.28.29" class="mw-headline"> type() </span>
---------------------------------------------------------

Returns a specific type.

<span id="types.28.29" class="mw-headline"> types() </span>
-----------------------------------------------------------

Returns an array of types.

<span id="uri.28.29" class="mw-headline"> uri() </span>
-------------------------------------------------------

<span id="users.28.29" class="mw-headline"> users() </span>
-----------------------------------------------------------

Returns an array of users.

<span id="web_path.28.29" class="mw-headline"> web\_path() </span>
------------------------------------------------------------------

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Theme\_Functions\_for\_Omeka\_0.9](Theme_Functions_for_Omeka_0.9.html)"

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

    [Page](Theme_Functions_for_Omeka_0.9.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Theme_Functions_for_Omeka_0.9&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Theme_Functions_for_Omeka_0.9&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Theme_Functions_for_Omeka_0.9&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](Special:WhatLinksHere/Theme_Functions_for_Omeka_0.9.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Theme_Functions_for_Omeka_0.9.html)
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

-   [Project](../index.html%3Fp=2.html)
-   [Staff](../index.html%3Fp=3.html)
-   [News](../blog.1.html)
-   [License](http://www.gnu.org/copyleft/gpl.html)

</div>

<div class="section">

### Help

-   [User Forums](../forums/topic/mysqli-stmt.bind-result.html)
-   [Documentation](http://omeka.org/codex/)
-   [Dev Listserv](http://groups.google.com/group/omeka-dev)
-   [Contact](http://omeka.org/contact/)

</div>

<div class="section">

### Downloads

-   [Download Omeka](../download.1.html)
-   [Plugins](../plugins.html)
-   [Themes](../download/themes/index.html)
-   [Packages](../index.html%3Fp=222.html)

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
