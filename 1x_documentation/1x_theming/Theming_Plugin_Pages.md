<div id="wrap">

[Skip Navigation](Theming_Plugin_Pages.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theming%20Plugin%20Pages)

</div>

Theming Plugin Pages
====================

<div id="primary">

Plugin pages can often be the most important and prominent parts of an
Omeka site. However, most plugins are designed to work well with the
default bundled themes. When a theme is heavily customized and is
significantly different from the stock themes, pages added by plugins
can be inconsistent with the look and feel of the rest of the site.

Starting with version 1.3 of Omeka, a theme can override and replace the
views for any plugin. This way, a theme can customize pages that are
created by plugins in just the same way themes have always been able to
customize the "standard" pages in an Omeka site. Instead of trying CSS
workarounds, theme writers can change the HTML directly, without editing
the plugin's files.

<span id="Overriding_a_Plugin_View" class="mw-headline"> Overriding a Plugin View </span>
-----------------------------------------------------------------------------------------

A plugin's `views` directory contains the stock view scripts for the
plugin's pages. In particular, the `views/public` directory contains
scripts used on the public site.

To override a plugin view, all you have to do is place a file in the
right place in your theme. To find out what file you need to include in
your theme, start by finding the path for the plugin view you want to
override. First, since a theme only contains public views, you remove
the `views/public` part of the path. Second, you need to change the
plugin name to be lowercase-with-hyphens instead of CamelCased.

So, to override SomePlugin's view at

    SomePlugin/views/public/controller/view.php

you place a file in your theme at

    some-plugin/controller/view.php

<span id="Example" class="mw-headline"> Example </span>
-------------------------------------------------------

The [Simple
Pages](http://omeka.org/codex/Plugins/SimplePages "Plugins/SimplePages")
plugin has one public view, at `views/public/page/show.php`. This view
is used for displaying all the pages created by the administrator.

Often, users want to move or remove the internal navigation that the
Simple Pages plugin outputs on every page. The simplest way to do this
is to override the `page/show.php` view.

To do this, a theme writer (using a theme called \`my-theme\`) would
start by copying the plugin view from

    plugins/SimplePages/views/public/page/show.php

to

    themes/my-theme/simple-pages/page/show.php

Once the view is copied to the theme, a theme writer can alter the
theme's copy of the view, and those changes will be reflected on the
public site.

<span id="Use_Cases" class="mw-headline"> Use Cases </span>
-----------------------------------------------------------

-   Theme writers can customize their themes to work well with some
    specific set of plugins.
-   Individual site administrators can account for every plugin their
    site uses in one place, in their public theme.
-   Plugins can take advantage of this feature in other ways
    (ExhibitBuilder [combines exhibit
    themes](http://omeka.org/codex/Changing_Exhibit_Themes_to_Public_Themes "Changing Exhibit Themes to Public Themes")
    with normal public themes using this feature)

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Theming\_Plugin\_Pages](Theming_Plugin_Pages.html)"

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

    [Page](Theming_Plugin_Pages.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Theming_Plugin_Pages&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Theming_Plugin_Pages&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Theming_Plugin_Pages&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Theming_Plugin_Pages.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Theming_Plugin_Pages.html)
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
