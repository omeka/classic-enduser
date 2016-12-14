<div id="wrap">

[Skip Navigation](upgrade.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Hooks/upgrade)

</div>

Hooks/upgrade
=============

<div id="contentSub">

<span class="subpages">&lt; [Hooks](../Hooks.html "Hooks")</span>

</div>

<div id="primary">

When Omeka detects that a user has installed a new version of the
plugin, it automatically deactivates the plugin and presents an
"Upgrade" button. This hook runs when a superuser clicks the "Upgrade"
button. It is primarily used to migrate database tables and other data
stored by older versions of the plugin.

<span id="Arguments" class="mw-headline"> Arguments </span>
-----------------------------------------------------------

 *string* `$oldVersion` {{\#if
:   | (optional)}}
:   The previous version that was installed and is being upgraded from.
:   {{\#if: | Default: `{{{default}}}`}}

 *string* `$newVersion` {{\#if
:   | (optional)}}
:   The new, current version of the plugin.
:   {{\#if: | Default: `{{{default}}}`}}

<span id="Example" class="mw-headline"> Example </span>
-------------------------------------------------------

The following example code has a switch statement, and based upon the
previous plugin version, runs specific code to upgrade versions.

Notice that there are no `break` statements inside the `switch`.
Omitting the switches allows the execution to "fall through"; once a
matching old version is found, the upgrade code for that version and
every subsequent version is executed. This means that you don't have to
duplicate code for upgrading from various different versions.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
add_plugin_hook('upgrade', 'myplugin_upgrade');
 
function myplugin_upgrade($oldVersion, $newVersion)
{
    switch($oldVersion)
    {
        // let the plugin cascade its upgrades
        case '1.0':
        // code to upgrade from 1.0 to 1.1
        case '1.1':
        // code to upgrade from 1.1 to 2.0
        case '2.0':
        // code to upgrade from 2.0 to 2.1
    }
}
```

</div>

</div>

<div class="printfooter">

Retrieved from "[http://omeka.org/codex/Hooks/upgrade](upgrade.html)"

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

    [Page](upgrade.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Hooks/upgrade&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Hooks/upgrade&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Hooks/upgrade&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](../Special:WhatLinksHere/Hooks/upgrade.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related changes](../Special:RecentChangesLinked/Hooks/upgrade.html)
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
