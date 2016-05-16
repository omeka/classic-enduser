<div id="wrap">

[Skip Navigation](ZoteroImport.html#content)
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
    In](https://omeka.org/c/index.php?title=Special:UserLogin&returnto=Plugins/ZoteroImport)

</div>

Plugins/ZoteroImport
====================

<div id="contentSub">

<span class="subpages">&lt;
[Plugins](../Plugins.1.html "Plugins")</span>

</div>

<div id="primary">

With this plugin you can move your Zotero research into Omeka, making it
possible to further organize and exhibit your Zotero library. Just sync
your library to the Zotero server, tell the Zotero Import plugin what
library you want to import, and it'll pull in source items, notes,
files, and web snapshots.

<span id="Requirements" class="mw-headline">Requirements</span>
---------------------------------------------------------------

**Sync Zotero library**: The Zotero library must be synced to the Zotero
sync server prior to import. To import files, the Zotero client must be
set to sync attachment files. You can find instructions on how to do
this at the [Zotero website](http://www.zotero.org/support/sync).

**Atom Feed URL**: Every Zotero library and collection has an Atom feed
URL. You can find this URL on the library or collection page of the
Zotero website, under "Subscribe to this feed." Unpublished libraries do
not have a feed URL readily accessible, but you can construct it using
the following URLs as templates:

-   user library: <https://api.zotero.org/users/%7BuserID%7D/items>
-   user collection:
    <https://api.zotero.org/users/%7BuserID%7D/collections/%7BcollectionKey%7D/items>
-   group library: <https://api.zotero.org/groups/%7BgroupID%7D/items>
-   group collection:
    <https://api.zotero.org/groups/%7BgroupID%7D/collections/%7BcollectionKey%7D/items>

The user or group owner can get you the userID, groupID, and
collectionID.

**Private key**: To access access private libraries and collections and
to download attachments (files and web snapshots), a private key is
required. A key is not necessary to access citations saved in public
libraries and collections. The owner of the library can generate private
keys in their [account
settings](https://www.zotero.org/settings/keys/new). Private keys must
be set to allow third party access.

**PHP Zip extension**: Zotero stores web snapshots in ZIP files
containing files with [Base64](http://en.wikipedia.org/wiki/Base64)
encoded filenames. The import plugin attempts to decode the filenames
using [PHP's Zip extension](http://www.php.net/manual/en/book.zip.php).
If your server does not have this extension installed, the plugin does
not decode the filenames. The import will still save web snapshots, but
the filenames will be obfuscated, making access near-worthless.

<span id="Installation_and_Importing" class="mw-headline">Installation and Importing</span>
-------------------------------------------------------------------------------------------

1\. If you want to import all file types, *you must disable file upload
validation* in Omeka Admin &gt; Settings &gt; Security Settings before
import.

2\. Once you've installed the plugin, go to the "Zotero Import" tab in
the admin interface and fill out the form (/admin/zotero-import).

3\. To fill out the form, you will need find the feed URL to the Zotero
library you want to import and, if desired or necessary, a private key
to access those sources. Click "Continue" to begin the importing
process.

4\. Depending on the size of the library, the import process may take
some time to complete. Because of this we suggest that you log
background processes:

-   In omeka/application/config/config.ini make sure log.processes =
    true
-   In omeka/application/logs/ make sure a processes.log file exists and
    is writable

This is not required but will be helpful if something goes wrong halfway
through a long import. It's important to note that the import process is
only as stable as the Zotero API. If you encounter errors, delete the
import and try again.

<span id="Stopping_and_Deleting_an_Import" class="mw-headline">Stopping and Deleting an Import</span>
-----------------------------------------------------------------------------------------------------

If you make a mistake, you may stop an import at any time by clicking
"Stop Import" in the Zotero Import admin panel. You may also delete the
items from an import after the process finishes, by clicking "Delete
Import." Deleting imports will delete all imported items and files.

<span id="Features" class="mw-headline">Features</span>
-------------------------------------------------------

The plugin imports Zotero libraries and collections, including source
items, notes, files, and web snapshots. Web snapshots are zipped up
directories containing the files needed to render the web snapshot.

To minimize data loss that often occurs when migrating between systems,
the plugin adds a new Zotero element set containing elements identical
to the fields used by Zotero. In addition to mapping data to the Zotero
element set, the plugin maps data to the native Dublin Core element set
to maximize interoperability and ease integration with Omeka. The Zotero
element set is large, but the plugin provides a helper function to build
strings from the elements therein (see the
zotero\_import\_build\_zotero\_output() function below).

The plugin also adds a field to the advanced search page that narrows
search results by Zotero item type. Every Zotero item has an item type,
so it's a helpful way to sort through your items.

<span id="Using_Zotero_Data_in_Omeka" class="mw-headline">Using Zotero Data in Omeka</span>
-------------------------------------------------------------------------------------------

-   **Return custom text built from elements from the Zotero element
    set**:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
/**
 * Returns custom text built from elements from the Zotero element set.
 * 
 * @param array $parts The parts of the output text mapped from Zotero elements.
 * array(
 *     array(
 *         'element'   => {Zotero element name, text, required}, 
 *         'prefix'    => {part prefix, text, optional}, 
 *         'suffix'    => {part suffix, text, optional}, 
 *         'all'       => {get all element texts?, boolean, optional}, 
 *         'delimiter' => {element text delimiter, text, optional}
 *     ), 
 *     array([...])
 * )
 * @return string The output text.
 */
zotero_import_build_zotero_output($parts = array());
```

</div>

</div>

-   **Return all items of a particular Zotero item type**:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
/**
 * Returns items of a particular Zotero item type. Uses the Item Type element in 
 * the Zotero element set.
 *
 * @param string Search items with this Zotero item type.
 * @param int|null Search only in this collection.
 * @param int Maximum number of items to return.
 * @return array An array containing item results.
 */
zotero_import_get_items_by_zotero_item_type($typeName, 
                                            $collectionId = null, 
                                            $itemLimit = 10);
```

</div>

</div>

-   **Return all items of a particular Zotero user or group**:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
get_items(array('collection' => $collectionId), $itemLimit = 10)
```

</div>

</div>

-   **Return all notes of a particular item**:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
item('Zotero', 'Note', $options = array(), $item = null);
```

</div>

</div>

-   **Return all attachments of a particular item**:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
loop_files_for_item($item = null);
```

</div>

</div>

<div class="printfooter">

Retrieved from
"[https://omeka.org/codex/Plugins/ZoteroImport](ZoteroImport.html)"

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

    [Page](ZoteroImport.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Plugins/ZoteroImport&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Plugins/ZoteroImport&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Plugins/ZoteroImport&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](https://omeka.org/codex/Special:WhatLinksHere/Plugins/ZoteroImport)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](https://omeka.org/codex/Special:RecentChangesLinked/Plugins/ZoteroImport)
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
