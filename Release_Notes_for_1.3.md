<div id="wrap">

[Skip Navigation](Release_Notes_for_1.3.html#content)
<div id="header">

<div class="padding">

<span
id="logo">[![Omeka](http://omeka.org/ui/i/logo-horizontal-288px.gif)](../index.html)</span>
<div id="search-form">

</div>

-   <div id="nav-showcase">

    </div>

    [Showcase](../showcase.1.html)
-   <div id="nav-involved">

    </div>

    [Get Involved](../index.html%3Fp=124.html)
-   <div id="nav-addons">

    </div>

    [Add-Ons](../add-ons.1.html)
-   <div id="nav-forums">

    </div>

    [Forums](../forums/topic/mysqli-stmt.bind-result.html)
-   <div id="nav-documentation">

    </div>

    [Documentation](http://omeka.org/codex/)
-   <div id="nav-download">

    </div>

    [Download](../download.1.html)

</div>

</div>

<div id="content">

<div class="padding">

<div id="user-meta">

-   <div id="pt-login">

    </div>

    [Log
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%201.3)

</div>

Release Notes for 1.3
=====================

<div id="primary">

Omeka 1.3 was released on December 20, 2010.

For a complete list of changes in version 1.3, see the [Omeka 1.3
changelog](https://omeka.org/trac/wiki/Omeka1.3ChangeLog).

<span id="New_Features" class="mw-headline"> New Features </span>
-----------------------------------------------------------------

-   Converts Omeka admin to use jQuery and jQuery UI. Updates admin
    panel to use external javascript files. Updates jQuery UI styles to
    override default behavior for buttons.
-   Disables Prototype by default, adds admin panel option to switch it
    back on if needed for other plugins.
-   Adds subnavigation ability to the nav, public\_nav, and
    public\_nav\_main global helper functions.
-   Adds sortable tables to the browse pages in the admin.
-   Adds a table for user activations.
-   Adds filter for theme options.
-   Refactors collections to simplify data entry for collector names.
    Collector names can now be entered one per line into a textarea on
    the form, and do not need to be users in Omeka.
-   Adds ReCaptcha code and settings to Omeka core.
-   Adds [Omeka.wysiwyg](Omeka.wysiwyg.html "Omeka.wysiwyg") JS function
    for implementing TinyMCE.
-   Allow theme configs to add the TinyMCE editor.
-   Allows plugins to find/use theme configuration options.
-   New helpers:
    -   [element\_exists](Functions/element_exists.html "Functions/element exists") -
        Checks if an given element and element set are present in Omeka.
    -   [public\_nav\_items](Theme_API/public_nav_items.html "Theme API/public nav items") -
        Navigation for the items/\* pages, with filter.
    -   [queue\_js](Theme_API/queue_js.html "Theme API/queue js")
    -   [display\_js](Theme_API/display_js.html "Theme API/display js")
    -   [queue\_css](Theme_API/queue_css.html "Theme API/queue css")
    -   [display\_css](Theme_API/display_css.html "Theme API/display css")
    -   [button\_to](http://omeka.org/c/index.php?title=Theme_API/button_to&action=edit&redlink=1 "Theme API/button to (page does not exist)")
    -   [delete\_button](http://omeka.org/c/index.php?title=Theme_API/delete_button&action=edit&redlink=1 "Theme API/delete button (page does not exist)") -
        Creates a form with a single delete button, used instead of
        links to a delete action.
-   New hooks:
    -   Adds hook to add content to simple browse view.

<span id="Fixed_Tickets" class="mw-headline"> Fixed Tickets </span>
-------------------------------------------------------------------

-   Fixes \#18 Adds sortable tables.
-   Fixes \#443 by adding a filter to the display HTML flag.
-   Fixes \#733, upgrades getID3 to version 2.0.0b6.
-   Fixes \#787 by adding a callback parameter to the loop\_records
    function, as well as updating loop\_items, loop\_collections,
    loop\_files, and loop\_item\_types to internally specify their
    callback functions to loop\_records.
-   Fixes \#900 Adds notification that image derivatives are not
    being created.
-   Fixes \#905, files in Omeka are stored with hashed filenames.
-   Fixes \#912, organizes elements by element set when used in a
    form select.
-   Fixes \#916, logout should destroy session and its data.
-   Fixes \#929 RSS2 outputs don't return error when files are
    associated with items.
-   Fixes \#942 by adding a function to convert URL strings to links.
-   Fixes \#944, adds explanatory text in theme config that theme
    configuration is on a per-theme basis.
-   Fixes \#958, allows superusers to change all user passwords.
-   Fixes \#961 password reset no longer sent to deactivated users.

<span id="Miscellaneous_Improvements" class="mw-headline"> Miscellaneous Improvements </span>
---------------------------------------------------------------------------------------------

-   Improved test coverage of Omeka core. Refactors tests to make use of
    PHPUnit's test suites.
-   Fixes installer to set the
    'enable\_header\_check\_for\_file\_mime\_types' flag based on
    whether the fileinfo extension is loaded.
-   Fixes users/edit action to redirect back to dashboard instead of
    users/browse when a user edits their own info.
-   Fixes mod\_rewrite checking in installer by explicitly allowing
    access to check-mod-rewrite.html, which could be blocked by more
    restrictive .htaccess configurations.
-   Converts database migrations to use timestamps instead of
    incremented integers.
-   Fixes security hole where form POST could modify a user's salt.
-   Updates url\_to\_link function to use preg\_replace instead of
    ereg\_replace; Moves url\_to\_link function to the admin theme's
    custom.php file.
-   Fixes a javascript bug where the first Use HTML checkbox would save
    a blank value.
-   Fixes a bug on users form where user data was not displayed after
    invalid password change attempt.
-   Fixes Omeka\_Core to display the generic error page for all
    uncaught exceptions.
-   Fixes bug in item\_has\_type helper to use the get magic method to
    retrieve a given item's item type name instead of using the item()
    view helper.
-   Fixes bug in show\_item\_metadata / ItemMetadataList. Previous code
    only works correctly when the item being displayed is the "current
    item" on the view, would cause fatal error if the item has a type.
-   Fixes media helpers for display of AVI,WMV,WMA (particularly
    on Mac).
-   Fixes theme file upload validation check. Reverses check over so the
    validation will be enabled unless the "disabled" option is equal to
    1, leaves validation on in case of an invalid or null value for
    the option. Adds file size and restricted type/ext validation for
    theme uploads.
-   Moves "add" button for advanced search out of each row. Disables
    remove buttons when there is only one row.
-   Select form element for element sets are now organized by set.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_1.3](Release_Notes_for_1.3.html)"

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

    [Page](Release_Notes_for_1.3.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_1.3&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_1.3&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_1.3&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_1.3.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_1.3.html)
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
