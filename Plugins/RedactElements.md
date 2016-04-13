<div id="wrap">

[Skip Navigation](RedactElements.html#content)
<div id="header">

<div class="padding">

<span
id="logo">[![Omeka](../../ui/i/logo-horizontal-288px.gif)](../../index.html)</span>
<div id="search-form">

</div>

-   <div id="nav-showcase">

    </div>

    [Showcase](../../showcase/index.html)
-   <div id="nav-involved">

    </div>

    [Get Involved](../../get-involved/index.html)
-   <div id="nav-addons">

    </div>

    [Add-Ons](../../add-ons/index.html)
-   <div id="nav-forums">

    </div>

    [Forums](../../forums/index.html)
-   <div id="nav-documentation">

    </div>

    [Documentation](../index.html)
-   <div id="nav-download">

    </div>

    [Download](../../download/index.html)

</div>

</div>

<div id="content">

<div class="padding">

<div id="user-meta">

-   <div id="pt-login">

    </div>

    [Log
    In](https://omeka.org/c/index.php?title=Special:UserLogin&returnto=Plugins/RedactElements)

</div>

Plugins/RedactElements
======================

<div id="contentSub">

<span class="subpages">&lt;
[Plugins](../Plugins.1.html "Plugins")</span>

</div>

<div id="primary">

This plug-in allows enabled users of an Omeka install to redact specific
character sequences in a given element field in Omeka. For example, any
instance of an email address in the Contributor or Source field could be
replaced with “\[Redacted\].” You can select which elements have
redactions applied, and which redactions to use.

Text sequences to be redacted are specified using regular expressions.
For more information on regular expressions, see
[regularexpressions.info](http://www.regular-expressions.info). The
plugin comes with regular expressions for IP addresses, email addresses,
and urls; you can can add other patterns.

<span id="Configuration" class="mw-headline"> Configuration </span>
-------------------------------------------------------------------

Following
[installation](../Managing_Plugins_2.0.html#Installing_a_Plugin "Managing Plugins 2.0"),
configure the plugin by selecting Plugins from the top navigation of
your admin and clicking on the Configure button for Redact Elements From
here you can:

-   Set which user roles are able to edit redacted elements and
    patterns;
-   Specify what text replaces redacted information;
-   Add new patterns for redaction.

[![RedElU.jpg](https://omeka.org/c/images/a/a6/RedElU.jpg)](https://omeka.org/codex/File:RedElU.jpg)

Only Super users and Administrators can administer the plugin. By
default, only Super users see the redacted text, instead of the
redaction message, on the Admin side. The Role Overrides allow you to
enable Administrators, Researchers, and Contributors to view redacted
information on the admin side of the installation.

To give or remove redaction permission, simply check the box next to the
user role.

[![RedElT.png](https://omeka.org/c/images/2/23/RedElT.png)](https://omeka.org/codex/File:RedElT.png)

You can change the replacement text for reacted text patterns in the
Replacement Text field. The default replacement is \[REDACTED\].

[![RedElP.png](https://omeka.org/c/images/4/4a/RedElP.png)](https://omeka.org/codex/File:RedElP.png)

Adding or editing patterns requires knowledge of regular expressions.
Every redacted pattern requires a label, which is how you will identify
the pattern from the plugin administration page. Existing patterns in
the plugin are IP Address, email address, and url.

You can remove an existing pattern by deleting the label and regular
expression.

If altering the configuration, be sure to save changes before leaving
the page.

<span id="Administration" class="mw-headline"> Administration </span>
---------------------------------------------------------------------

Redaction implementation takes place in the Redact Elements
administrative page, accessible to enabled users from the left
navigation bar or from the link in the configure plugin page.

To add a redaction:

-   Select the field in which the redacted text may appear from the
    drop-down menu labeled “Add Element”.
    -   This drop-down includes all default element sets for your
        installation as well as custom element sets.
-   Select one or more of the patterns from the checkbox list below. To
    implement, click save changes.

[![RedEl1.jpg](https://omeka.org/c/images/a/ae/RedEl1.jpg)](https://omeka.org/codex/File:RedEl1.jpg)

You can add multiple redactions at a time by clicking the Add New
Element button, which will load another drop-down menu and checkbox set.

To delete a redacted element, uncheck all its patterns and save changes.

<div class="printfooter">

Retrieved from
"[https://omeka.org/codex/Plugins/RedactElements](RedactElements.html)"

</div>

<div id="catlinks" class="catlinks catlinks-allhidden">

</div>

</div>

<div id="secondary">

<div class="portlet">

Documentation
-------------

-   [Home](../index.html)
-   [Screencasts](../Screencasts.html)
-   [Themes](../Managing_Themes_2.0.html)
-   [Appearance](../Managing_Appearance_2.0.html)
-   [Plugins](../Plugins2.0.html)

</div>

<div class="portlet">

Page View
---------

-   <div id="nav-page">

    </div>

    [Page](RedactElements.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Plugins/RedactElements&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Plugins/RedactElements&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Plugins/RedactElements&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](https://omeka.org/codex/Special:WhatLinksHere/Plugins/RedactElements)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](https://omeka.org/codex/Special:RecentChangesLinked/Plugins/RedactElements)
-   <div id="t-specialpages">

    </div>

    [Special pages](../Special:SpecialPages.html)

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

-   [Project](../../about/index.html)
-   [Staff](../../about/staff/index.html)
-   [News](../../blog/index.html)
-   [License](http://www.gnu.org/copyleft/gpl.html)

</div>

<div class="section">

### Help

-   [User Forums](../../forums/index.html)
-   [Documentation](../index.html)
-   [Dev Listserv](http://groups.google.com/group/omeka-dev)
-   [Contact](../../contact/index.html)

</div>

<div class="section">

### Downloads

-   [Download Omeka](../../download/index.html)
-   [Plugins](../../addons/plugins.html)
-   [Themes](../../addons/themes.html)
-   [Packages](../../download/packages/index.html)

</div>

</div>

<div id="chnm-meta">

<span id="chnm-logo">[![Roy Rosenzweig Center for History and New
Media](../../ui/i/rrchnm-logo-regular.gif)](http://chnm.gmu.edu)</span>
Omeka is a project of the [Roy Rosenzweig Center for History and New
Media](http://chnm.gmu.edu), [George Mason
University](http://www.gmu.edu). Copyright © 2007–2016 CHNM.

</div>

</div>

</div>

</div>
