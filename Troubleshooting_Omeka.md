<div id="wrap">

[Skip Navigation](Troubleshooting_Omeka.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Troubleshooting%20Omeka)

</div>

Troubleshooting Omeka
=====================

<div id="primary">

<span id="404_Errors" class="mw-headline"> 404 Errors </span>
-------------------------------------------------------------

If you follow a link in Omeka and you get a 404 error or an error saying
the URL is not valid, this is likely caused by a mod\_rewrite problem on
your server. There are two possibilities:

1.  You forgot to copy the .htaccess file when FTPing your install.
    Double check that it transferred properly.
2.  Your server may not have mod\_rewrite installed. Create a PHP file
    with the following code: &lt;?php phpinfo(); ?&gt; and double check
    that it's currently enabled. (How? Where?) If not, contact your
    system administrator. mod\_rewrite is currently a requirement
    for Omeka.

If installing mod\_rewrite does not solve the problem, check that your
Apache configuration allows .htaccess overrides. You will need the
`AllowOverrides All` directive in the appropriate place in httpd.conf.

<span id="Getting_Better_Error_Messages" class="mw-headline"> Getting Better Error Messages </span>
---------------------------------------------------------------------------------------------------

A blank or white screen is often an indication that Omeka or PHP has
encountered an error. Since error messages can often contain private or
technical information, Omeka hides them by default. See [retrieving
error
messages](Retrieving_error_messages.html "Retrieving error messages")
for instructions on how to show these messages. The content of error
messages can be extremely useful for troubleshooting, so try these steps
before seeking further help.

<span id="Further_Help_Troubleshooting" class="mw-headline"> Further Help Troubleshooting </span>
-------------------------------------------------------------------------------------------------

General questions should be asked on the [Omeka
Forums](../forums/topic/mysqli-stmt.bind-result.html). Advanced users
may wish to post their technical questions on the [Developer Mailing
List](http://groups.google.com/group/omeka-dev) for a more specific
solution to their problem.

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Troubleshooting\_Omeka](Troubleshooting_Omeka.html)"

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

    [Page](Troubleshooting_Omeka.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Troubleshooting_Omeka&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Troubleshooting_Omeka&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Troubleshooting_Omeka&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Troubleshooting_Omeka.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Troubleshooting_Omeka.html)
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
