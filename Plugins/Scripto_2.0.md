<div id="wrap">

[Skip Navigation](Scripto_2.0.html#content)
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
    In](https://omeka.org/c/index.php?title=Special:UserLogin&returnto=Plugins/Scripto%202.0)

</div>

Plugins/Scripto 2.0
===================

<div id="contentSub">

<span class="subpages">&lt;
[Plugins](../Plugins.1.html "Plugins")</span>

</div>

<div id="primary">

<span id="About" class="mw-headline"> About </span>
---------------------------------------------------

The Scripto plugin allows you to crowdsource the transcription of your
Omeka content. It adds a feature rich interface to the admin and public
sides that includes many features from
[MediaWiki](http://www.mediawiki.org/wiki/MediaWiki), the software
behind [Wikipedia](http://www.wikipedia.org/). All items with files can
be transcribed. For these purposes an item is a *document*, and an
item's files are its *pages*.

<span id="Features" class="mw-headline"> Features </span>
---------------------------------------------------------

With the Scripto plugin, users can:

-   Transcribe document pages
-   Discuss document pages
-   View contributions they've made
-   View recent transcription and discussion history
-   View the revision history of a page
-   View revisions of a page
-   View the difference between page revisions
-   Revert to a previous revision
-   Make a custom watchlist

In addition to this, administrators can:

-   Protect transcriptions and discussions
-   Edit protected transcriptions and discussions
-   Import transcriptions from MediaWiki as item and file metadata
-   View corresponding MediaWiki pages

<span id="Sandbox" class="mw-headline"> Sandbox </span>
-------------------------------------------------------

Interested in testing out Scripto's functionality in Omeka? Try our
[Sandbox demonstration site](http://scripto.org/omeka/).

<span id="Installing_MediaWiki" class="mw-headline"> Installing MediaWiki </span>
---------------------------------------------------------------------------------

This plugin requires you or your system administrator to
[download](http://www.mediawiki.org/wiki/Download) and
[install](http://www.mediawiki.org/wiki/Installation) MediaWiki, a
popular free web-based wiki software application that Scripto uses to
manage user and transcription data. You should install MediaWiki in a
separate directory from Omeka. It can be installed on another server and
it must be accessible to the Web.

<span id="Configuring_Scripto" class="mw-headline"> Configuring Scripto </span>
-------------------------------------------------------------------------------

-   **MediaWiki API URL:** URL to your [MediaWiki installation
    API](http://www.mediawiki.org/wiki/API:Quick_start_guide#What_you_need_to_access_the_API).
-   **Image viewer:** Select an image viewer to use when transcribing
    image files. [OpenLayers](http://openlayers.org/) and
    [Zoom.it](http://zoom.it/) can display JPEG, PNG, GIF, and
    BMP formats. Zoom.it can also display TIFF and ICO formats. By using
    Zoom.it you acknowledge that you have read and agreed to the
    [Microsoft Zoom.it Terms of Service](http://zoom.it/pages/terms/).
-   **Use Google Docs Viewer?:** Use Google Docs Viewer when
    transcribing document files? Document files include PDF, DOC, PPT,
    XLS, TIFF, PS, and PSD formats. By using this service you
    acknowledge that you have read and agreed to the [Google Docs Viewer
    Terms of Service](http://docs.google.com/viewer/TOS?hl=en).
-   **Import type:** Import transcriptions as HTML or plain text?
    Importing will copy document and page transcriptions from MediaWiki
    to their corresponding items and files in Omeka. Choose HTML if you
    want to preserve formatting. Choose plain text if formatting is
    not important.
-   **Home page text:** Enter text that will appear on the Scripto
    home page. Use this to display custom messages to your users, such
    as instructions on how to use Scripto and how to register for a
    MediaWiki account. Default text will appear if nothing is entered.
    You may use HTML. (Wrapping paragraph tags recommended.)

[![Scripto1.png](https://omeka.org/c/images/b/b8/Scripto1.png)](https://omeka.org/codex/File:Scripto1.png)
[![Scripto2.png](https://omeka.org/c/images/c/cb/Scripto2.png)](https://omeka.org/codex/File:Scripto2.png)

<span id="Quick_Start" class="mw-headline"> Quick Start </span>
---------------------------------------------------------------

Once you've installed MediaWiki and the Scripto plugin you can begin
transcribing document pages:

1.  Open an item page as normal (the item must have at least one file);
2.  Click on one of the pages (files) under "Transcribe This Item".
    You'll be taken to a user interface where you can view, transcribe,
    and discuss the selected page;
3.  Click "\[edit\]" beside "Current Page Transcription", an edit form
    will open;
4.  Transcribe the page and click "Edit transcription";

<span id="Restricting_Access" class="mw-headline"> Restricting Access </span>
-----------------------------------------------------------------------------

The Scripto interface is available to all users, but as a MediaWiki
administrator you can restrict access to certain actions. By default,
anonymous users can edit and revert pages. If you want to restrict these
actions, you must [follow these
directions](http://www.mediawiki.org/wiki/Manual:Preventing_access#Restrict_editing_of_all_pages),
and your users must create MediaWiki user accounts (see below).

<span id="Creating_Accounts" class="mw-headline"> Creating Accounts </span>
---------------------------------------------------------------------------

Scripto uses a separate login procedure from Omeka, so non-anonymous
users must have a MediaWiki account and administrators must manage them
via MediaWiki. (We recognize that this is not ideal, but the [MediaWiki
API](http://www.mediawiki.org/wiki/API:Main_page) does not provide the
means to create accounts.) To create an account, users must:

1.  Go to the MediaWiki website
2.  Click "log in / create account" in the top-right corner
3.  Click "Create an account."
4.  Fill in the information and submit the form

If you do not want to allow anonymous account creation, you must [follow
these
directions](http://www.mediawiki.org/wiki/Manual:Preventing_access#Restrict_account_creation)
and create accounts for all your users. To create user accounts, you
must:

1.  Go to the MediaWiki website
2.  Click "Special pages" in the toolbar
3.  Click "Log in / create account" under "Login / sign up"
4.  Click "Create an account."
5.  Fill in the information and do one of the following:
    1.  Fill in a password and click "Create account"
    2.  Fill in an email and click "By e-mail" (The user will receive an
        email with instructions on how to complete their
        account creation. You can modify the account creation email by
        editing the MediaWiki:Createaccount-text page.)

<span id="Importing" class="mw-headline"> Importing </span>
-----------------------------------------------------------

Once a document or page is transcribed, you may import the transcription
from MediaWiki into Omeka. *Importing a document* stitches together all
its page transcriptions and imports the result to the corresponding
item. *Importing a page* imports to the corresponding file. All
transcriptions are imported to the "Transcription" element in the
"Scripto" element set.

Import is only available to MediaWiki administrators. After logging into
Scripto via the Omeka interface, two buttons will appear on the
transcription page: "Import Document" and "Import Page." Just click
these buttons to import the transcription from MediaWiki to Omeka.

<span id="Advanced_Usage" class="mw-headline"> Advanced Usage </span>
---------------------------------------------------------------------

### <span id="Record_Client_IP_Address" class="mw-headline"> Record Client IP Address </span>

Scripto does not record a client's IP address by default. All
modifications to pages will be set to the IP address of the server
running Omeka. To record a client's IP address, you'll need to add the
following code to LocalSettings.php:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$wgSquidServersNoPurge = array('127.0.0.1');
```

</div>

</div>

Where '127.0.0.1' is your server's IP address.

### <span id="Base64_Decoding" class="mw-headline"> Base64 Decoding </span>

Scripto Base64 encodes document and page numbers to prevent incompatible
MediaWiki title characters. Because of this, corresponding page titles
in MediaWiki will be unusually named. You may place the following code
in LocalSettings.php to make page titles human readable:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// Decode the MediaWiki title from Base64.
// http://www.mediawiki.org/wiki/Manual:Hooks/BeforePageDisplay
$wgHooks['BeforePageDisplay'][] = 'fnScriptoDecodePageTitle';
function fnScriptoDecodePageTitle(&$out, &$sk, $prefix = '.', $delimiter = '.')
{
    $title = strtr($out->getPageTitle(), '-_', '+/');
    if ($prefix != $title[0]) {
        return false;
    }
    $title = array_map('base64_decode', explode($delimiter, ltrim($title, $prefix)));
    $title = 'Document ' . $title[0] . '; Page ' . $title[1];
    $out->setPageTitle($title);
    return false;
}
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[https://omeka.org/codex/Plugins/Scripto\_2.0](Scripto_2.0.html)"

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

    [Page](Scripto_2.0.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Plugins/Scripto_2.0&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Plugins/Scripto_2.0&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Plugins/Scripto_2.0&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](https://omeka.org/codex/Special:WhatLinksHere/Plugins/Scripto_2.0)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](https://omeka.org/codex/Special:RecentChangesLinked/Plugins/Scripto_2.0)
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
