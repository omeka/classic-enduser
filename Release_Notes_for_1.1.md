<div id="wrap">

[Skip Navigation](Release_Notes_for_1.1.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%201.1)

</div>

Release Notes for 1.1
=====================

<div id="primary">

Omeka 1.1 was released on October 15, 2009.

<span id="Core_changes" class="mw-headline"> Core changes </span>
-----------------------------------------------------------------

-   Omeka now shows only completed metadata for items by default. Adds
    an option in the settings panel to show all item metadata.
-   Adds an Omeka XML schema, and implements that schema in new outputs.
    More info at
    [http://omeka.org/codex/Response\_Formats](Response_Formats.html).
-   Adds PHP CLI setting to config.ini, for plugins to use instead of
    adding a setting.
-   Validation on the installer form and settings form. Adds helpful
    descriptions to settings fields.
-   Updates the File MIME Type listing in the Media helper

<span id="Admin_Interface_Improvements" class="mw-headline"> Admin Interface Improvements</span>
------------------------------------------------------------------------------------------------

-   Makes language in admin UI more consistent
-   Adds total number of items links for both admin collection browse
    pages and item type browse pages. \[4477\]
-   Plugins Page
    -   Uses metadata in plugin.ini file.
    -   Enforces plugin dependencies
    -   Adds plugin Upgrade button.
    -   Uninstalling - Establishes a new process for uninstalling
        plugins, including a confirmation page with a modifiable
        uninstall message.
-   Removing a collector takes user back to the collections/edit page
    instead of redirecting to the collections/show page.
-   Adds a 'View on Public Site' link on admin/items/show
    and admin/collections/show.
-   Database upgrade notice and button is now visible on all
    Admin pages.

<span id="API_changes" class="mw-headline"> API changes </span>
---------------------------------------------------------------

-   Theme API:
    -   Updates the item() helper to add 'date modified' as a
        special argument. \[4303\]
    -   New helper functions for Item Files \[4470\]
        -   recent\_files()
        -   set\_files\_for\_loop()
        -   get\_files()
        -   get\_files\_for\_loop()
        -   loop\_files()
        -   has\_files()
    -   New helper functions for Item Types \[4477\]
        -   get\_item\_types\_for\_loop()
        -   set\_item\_types\_for\_loop()
        -   loop\_item\_types()
        -   set\_current\_item\_type()
        -   get\_current\_item\_type()
        -   has\_item\_types\_for\_loop()
    -   New helper functions for linking to items browse pages \[4477\]
        -   link\_to\_items\_in\_collection()
        -   link\_to\_items\_with\_item\_type()
    -   collection() helper function - now includes parameter for
        specific Collection \[4501\]
    -   item\_image() helper function - uses the given item object for
        displaying alt text \[4501\]
    -   link\_to() helper function - adds a parameter for an array of
        query parameters \[4477\]
    -   display\_random\_featured\_item() helper function - does not set
        the current item to prevent conflicts with items set elsewhere
        (like on items/show) \[4501\]
    -   display\_random\_featured\_collection() helper function - does
        not set the current collection to prevent conflicts with
        collections set elsewhere (like on collections/show) \[4501\]

<!-- -->

-   Plugin API:
    -   Background processes - plugins can now easily encapsulate,
        instantiate, and run background processes \[4466\]
        -   Adds Process class
        -   Adds ProcessAbstract class
        -   Adds ProcessDispatcher class
        -   Adds ProcessTable class
    -   New helper functions:
        -   get\_specific\_plugin\_hook\_output() - gets the output of a
            specific hook belonging to a specific plugin. \[4322\]
    -   New plugin hooks:
        -   admin\_append\_to\_plugin\_uninstall\_message() - Lets
            plugin developers customize the uninstall message. \[4322\]
        -   upgrade()
        -   plugin\_append\_to\_admin\_site\_info() - Lets plugin
            developers add HTML to to the site\_info panel in the
            admin header.
        -   after\_save\_record()
        -   before\_save\_record()
        -   before\_save\_form\_record()
        -   after\_save\_form\_record()
        -   before\_delete\_record()
        -   after\_delete\_record()
        -   before\_insert\_record()
        -   after\_insert\_record()
        -   before\_update\_record()
        -   after\_update\_record()
        -   before\_validate\_record()
        -   after\_validate\_record()

<span id="Security_Fixes" class="mw-headline"> Security Fixes </span>
---------------------------------------------------------------------

-   Fixes XSS vulnerability in several helper functions. (\#838)
-   Uses html\_escape on URLs when necessary.

<span id="Miscellaneous" class="mw-headline"> Miscellaneous </span>
-------------------------------------------------------------------

-   Updates Zend to version 1.9.2.
-   Fixes a bug in the installer that only allows alpha-numeric
    characters in the password during validation. \[4408\]
-   Fixes a bug in Collection::totalItems() that returned the wrong
    count when there were collections of the same name. \[4298\]
-   \#688 Properly extract IPTC metadata during file uploads. \[4396\]
-   \#716 fixes errors when using snippet on strings shorter than the
    number of characters specified \[4240\]
-   \#801, which prevents users from adding a tag with name '0'. Also
    fixes the search item filtering so that it finds the a tag
    called '0'.
-   \#779, Sets the session name to a hash of BASE\_DIR, which is unique
    and unchanging for every Omeka installation. . This lets users log
    in at www.example.com, and still be logged in at example.com.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_1.1](Release_Notes_for_1.1.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Category](http://omeka.org/codex/Special:Categories "Special:Categories"):
<span dir="ltr">[Release
Notes](http://omeka.org/c/index.php?title=Category:Release_Notes&action=edit&redlink=1 "Category:Release Notes (page does not exist)")</span>

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

    [Page](Release_Notes_for_1.1.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_1.1&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_1.1&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_1.1&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_1.1.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_1.1.html)
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
