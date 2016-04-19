<div id="wrap">

[Skip Navigation](Release_Notes_for_2.0.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Release%20Notes%20for%202.0)

</div>

Release Notes for 2.0
=====================

<div id="primary">

Omeka 2.0 is the second major release. It represents many fundamental
changes and improvements to the core and development API

<span id="Core_Changes" class="mw-headline"> Core Changes </span>
-----------------------------------------------------------------

-   Fixed [numerous
    issues](https://github.com/omeka/Omeka/issues?milestone=1&page=1&state=closed)
-   Shifted naming conventions for better comformity to upcoming Zend
    2.0 standards
-   Removed Data Types from ElementTexts
-   Removed Entities to represent Users. All user information is now
    directly on User objects
-   Added Dublin Core information to Collections
-   Removed Orderable mixin
-   Added Searchable mixin
-   Ownable mixin now named Mixin\_Owner
-   Taggable mixin now named Mixin\_Tag
-   ActsAsElementText mixin now named Mixin\_ElementText
-   PublicFeatures mixin now named Mixin\_PublicFeatured
-   Omeka\_Acl removed. User Zend\_Acl instead
-   Derivative images now produced for many more file types
-   archive directory changed to files
-   archive/files directory changed to files/original
-   Phased loading is now removed in favor of loading resources when
    needed

\

<span id="API_Changes" class="mw-headline"> API Changes </span>
---------------------------------------------------------------

-   Removed many functions with overlapping or similar functionality
    [details](Updating_Plugins_For_2.0.html#Helper_Functions)
-   Functions no long echo directly and instead return values
-   Form functions have been removed in favor of using [Zend Form
    Helpers](http://framework.zend.com/manual/en/zend.view.helpers.html)
-   Many new and renamed hooks and filters
    [details](Updating_Plugins_For_2.0.html#Hooks_and_Filters)
-   Arguments passed to all hooks consolidated into one \$args array
-   beforeSaveForm() and afterSaveForm() callbacks removed from records
-   Omeka\_Form\_Admin class added to help build simple admin forms
-   Omeka\_Plugin class renamed Omeka\_Plugin\_AbstractPlugin
-   Controllers should now extend
    Omeka\_Controller\_AbstractActionController
-   Models should now extend Omeka\_Record\_AbstractRecord
-   Db wrappers removed :getDb, getTable, and findById are replaced by
    equivalent calls to \_helper-&gt;db-&gt;{methodName}.
-   Omeka\_Context removed in favor of using Zend\_Registry
-   Plugins can now add their content to search with Mixin\_Search

Additional details can be found [in the
codex](Updating_Plugins_For_2.0.html) and [in the new
documentation](http://omeka.readthedocs.org/en/latest/Tutorials/migratingCodeTo2.0.html)

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Release\_Notes\_for\_2.0](Release_Notes_for_2.0.html)"

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

    [Page](Release_Notes_for_2.0.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Release_Notes_for_2.0&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Release_Notes_for_2.0&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Release_Notes_for_2.0&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Release_Notes_for_2.0.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Release_Notes_for_2.0.html)
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
