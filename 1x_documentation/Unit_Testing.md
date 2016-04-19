<div id="wrap">

[Skip Navigation](Unit_Testing.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Unit%20Testing)

</div>

Unit Testing
============

<div id="primary">

Large code bases are prone to unintentional issues popping up as the
code grows and transitions in to more mature states. Small changes in
the way the way one piece of how the code works can have a cascading
effect on the code you are writing, causing a lot of wasted time spent
tracking down the cause of the issue. Perhaps the best way of
proactively dealing with this is writing [unit
tests](http://en.wikipedia.org/wiki/Unit_testing "wikipedia:Unit testing")
that test pieces of code individually, and [integration
tests](http://en.wikipedia.org/wiki/Integration_testing "wikipedia:Integration testing")
that test code against everything else that is happening in the
codebase. If an issue does arise, it is much easier to then track down
where the issues are and fix them quickly, and develop better code.

Omeka's testing suite relies on [PHPUnit](http://phpunit.de) a testing
framework for PHP. You can run the unit tests in three configurations,
test the core and plugins, just the core, and just the plugins. To run
the tests, go to the application/tests directory and run phpunit with
the following commands:

    cd /path/to/omeka/application/tests
    phpunit             # runs all tests
    phpunit AllTests    # runs all tests
    phpunit CoreTests   # runs tests on the Omeka core
    phpunit PluginTests # runs tests in plugins

<span id="Install_PHPUnit" class="mw-headline"> Install PHPUnit </span>
-----------------------------------------------------------------------

Omeka's test suite currently requires PHPUnit 3.5 or higher.

The preferred way to install PHPUnit is through
[PEAR](http://pear.php.net). Pretty much any recent PHP version already
includes PEAR by default

Before you install PHPUnit, you first have to let PEAR know where to get
PHPUnit and its dependencies. Run the following three commands in the
shell (this only needs to be done once):

    pear channel-discover pear.phpunit.de
    pear channel-discover components.ez.no
    pear channel-discover pear.symfony-project.com

Now, you can actually install PHPUnit:

    pear install phpunit/PHPUnit

To make sure the installation was successful, you can run:

    phpunit --version

Which should print something like the following if PHPUnit has been
installed:

    PHPUnit 3.5.10 by Sebastian Bergmann

<span id="Test_configuration" class="mw-headline"> Test configuration </span>
-----------------------------------------------------------------------------

Configuration for Omeka tests is in `application/tests/config.ini`.

<span id="Other_Tricks" class="mw-headline"> Other Tricks </span>
-----------------------------------------------------------------

### <span id="Plugin_Template" class="mw-headline"> Plugin Template </span>

### <span id="Code_Coverage" class="mw-headline"> Code Coverage </span>

### <span id="Static_Code_Analysis" class="mw-headline"> Static Code Analysis </span>

### <span id="Code_Metrics" class="mw-headline"> Code Metrics </span>

### <span id="Copy.2FPaste_Detection" class="mw-headline"> Copy/Paste Detection </span>

### <span id="Coding_Standards" class="mw-headline"> Coding Standards </span>

### <span id="Documentation" class="mw-headline"> Documentation </span>

### <span id="Ant" class="mw-headline"> Ant </span>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Unit\_Testing](Unit_Testing.html)"

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

    [Page](Unit_Testing.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Unit_Testing&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Unit_Testing&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Unit_Testing&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Unit_Testing.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related changes](Special:RecentChangesLinked/Unit_Testing.html)
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
