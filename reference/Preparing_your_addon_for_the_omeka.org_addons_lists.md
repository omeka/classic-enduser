<div id="wrap">

[Skip
Navigation](Preparing_your_addon_for_the_omeka.org_addons_lists.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Preparing%20your%20addon%20for%20the%20omeka.org%20addons%20lists)

</div>

Preparing your addon for the omeka.org addons lists
===================================================

<div id="primary">

The summer of 2011 saw the introduction of a self-serve mechanism for
having your addon listed on the theme or plugin pages on omeka.org.

The process involves some additional steps and changes to the .ini files
to help potential users of your theme or plugin.

First, in your .ini files, the following information must be present, in
addition to usual .ini information (See .ini examples for
[plugins](Plugin_Writing_Best_Practices.html#MyPlugin.2Fplugin.ini) and
[themes](Theme_Writing_Best_Practices.html#Theme.ini)):

`support_link` 
:   A URL where others can find support or report issues with
    your addon. This should not be the omeka-dev list. Instead, this
    should be where you will respond to questions or issues. A github
    issues page works fine.

`omeka_target_version` 
:   The version of Omeka that the current release was developed against,
    and/or that you intend the current release to work with. It is
    possible that this will replace the current
    `omeka_tested_up_to` field. We're exploring that possibility, and
    appreciate feedback.

`license` 
:   The software license you are releasing the plugin under. Often,
    developers choose to release under the GPL. In general, the Omeka
    community leans strongly toward some open source license.

Files should be compressed as .zip files. Our addons page will keep
track of versions based on what is in the .ini file, and will use the
name given in the .ini file. The page you create on omeka.org for your
addon need not be the same as what you give in the .ini file, but
obviously it makes more sense if you do.

When you are ready to share your plugin with the others, we recommend
that you start by telling us about it on the [dev
list](http://groups.google.com/group/omeka-dev/) with a link to it. That
will gives us a chance to get to know you if we don’t already, and get
more feedback from the community. Then, you can [sign up for an account
on our addons site](../wordpress/wp-login.php%3Faction=register.html)
(which runs on WordPress). When your account is approved, you will be
able to submit your plugin and make it available on our plugins page. If
you are part of an organization that will be contributing, you might
want to create an account for the organization, since users cannot edit
other users’ addons.

### <span id="Two_important_gotchas" class="mw-headline"> Two important gotchas </span>

1.  If you are using a version control system like git or svn, make sure
    you remove the hidden .git or .svn files and directories before
    zipping up your addon. (Consider using the [git
    archive](http://gitready.com/intermediate/2009/01/29/exporting-your-repository.html)
    or [svn
    export](http://svnbook.red-bean.com/en/1.5/svn.ref.svn.c.export.html)
    commands to do this for you.)
2.  Mac systems often create additional directory structures when
    creating a .zip file of your addon. You will need to make sure your
    .zip file accurately reflects the directory structure of your addon.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Preparing\_your\_addon\_for\_the\_omeka.org\_addons\_lists](Preparing_your_addon_for_the_omeka.org_addons_lists.html)"

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

    [Page](Preparing_your_addon_for_the_omeka.org_addons_lists.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Preparing_your_addon_for_the_omeka.org_addons_lists&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Preparing_your_addon_for_the_omeka.org_addons_lists&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Preparing_your_addon_for_the_omeka.org_addons_lists&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](Special:WhatLinksHere/Preparing_your_addon_for_the_omeka.org_addons_lists.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Preparing_your_addon_for_the_omeka.org_addons_lists.html)
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
