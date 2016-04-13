<div id="wrap">

[Skip Navigation](SimpleVocab.html#content)
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
    In](https://omeka.org/c/index.php?title=Special:UserLogin&returnto=Plugins/SimpleVocab)

</div>

Plugins/SimpleVocab
===================

<div id="contentSub">

<span class="subpages">&lt;
[Plugins](../Plugins.1.html "Plugins")</span>

</div>

<div id="primary">

With the Simple Vocab plugin you can define a controlled vocabulary for
any field using a simple interface. A controlled vocabulary is a list of
predefined, authorized terms that are preselected by you or another
administrator. This plugin even helps you build vocabularies using texts
that already exist in your archive.

<span id="Configuring_the_Plugin" class="mw-headline"> Configuring the Plugin </span>
-------------------------------------------------------------------------------------

-   [Install the
    plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin"),
    and then go to the Simple Vocab tab in the top navigation bar
    in /admin.
-   Select the Element (all Dublin Core and item type metadata fields
    are available) you wish to have a controlled vocabulary.
-   Enter the custom terms you wish to be available for this element,
    one per line. To save your entries, click Add/Edit Vocabulary.
-   To delete the vocabulary, select the element (note, it should be
    starred), and the terms will appear in the text box below. Simply
    remove the terms and re-sumbit this form by clicking
    Add/Edit Vocabulary.

<span id="Viewing_Terms_Already_in_Use" class="mw-headline">Viewing Terms Already in Use</span>
-----------------------------------------------------------------------------------------------

You may view a list of texts for any selected element that currently
exist in your archive. This list may be a useful reference for building
controlled vocabulary, but be aware of some caveats:

-   Vocabulary terms must not contain newlines (line breaks).
-   Vocabulary terms are typically short and concise. If your existing
    texts are otherwise, avoid using a controlled vocabulary for
    this element.
-   Vocabulary terms must be identical to their corresponding texts.
-   Existing texts that are not in the vocabulary will be preserved —
    however, they cannot be selected in the item edit page, and will be
    deleted once you save the item.

<span id="Working_with_Other_Plugins" class="mw-headline"> Working with Other Plugins </span>
---------------------------------------------------------------------------------------------

Version 1.2 allows you to reveal an element's controlled vocabulary for
users filling out the contribution form, (read more about the
[Contribution plugin](Contribution.html "Plugins/Contribution")).

*Please note that you cannot offer different vocabularies for admin
users and public users. If a vocabulary is set for an element, only
those terms will be available if that specific element appears on the
public contribution form.*

### <span id="simple_vocab_routes_Filter" class="mw-headline"> simple\_vocab\_routes Filter </span>

As of version 1.2, the SimpleVocab plugin includes a filter that plugin
authors can use to activate the vocabulary on most any form.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
add_filter(
    'simple_vocab_routes', 
    array('module' => {module}, 
          'controller' => {controller}, 
          'actions' => array({action}, {action}, {...}))
);
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[https://omeka.org/codex/Plugins/SimpleVocab](SimpleVocab.html)"

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

    [Page](SimpleVocab.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Plugins/SimpleVocab&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Plugins/SimpleVocab&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Plugins/SimpleVocab&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](https://omeka.org/codex/Special:WhatLinksHere/Plugins/SimpleVocab)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](https://omeka.org/codex/Special:RecentChangesLinked/Plugins/SimpleVocab)
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
