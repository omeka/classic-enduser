Reports
===============

The **Bar Code & Reports** plugin allows users to create reports from Omeka items. The plugin can create reports in HTML and PDF formats, including bar codes, and is extensible to additional formats.

Using this plugin, you can create PDF [QR Codes](http://en.wikipedia.org/wiki/QR_Code) for your Omeka items, HTML
output, as well as other custom formats (see **Extending,** below)).

To read more about using QRCodes in museums and making them work in your gallery, see the [Powerhouse Museum](http://www.powerhousemuseum.com/dmsblog/index.php/2009/03/05/qr-codes-in-the-museum-problems-and-opportunities-with-extended-object-labels/).

Requirements 
-----------------------------------------------------

The Reports plugin requires Omeka version 1.0 or higher.

If you are using Omeka.net, please see [instructions for this plugin](http://info.omeka.net/build-a-website/manage-themes-and-plugins/reports-and-bar-codes/) in Help pages for Omeka.net.

Configuration
----------------------------------------------------

-   **Path to PHP-CLI:** This option must point to a PHP-CLI command that satisfies Omeka's requirements. For more information about the correct value for this option, check with your hosting provider.
    - Default: The plugin will attempt to guess an appropriate path to PHP-CLI
-   **Reports save directory:** This is the path (on your server, not on the Web) where created reports will be saved. This directory *must* be writable by the server for reports to be generated.
    - Default: `[Omeka directory]/plugins/Reports/generated_reports`

Screencast
-------------------------------------------------------------

Watch a [quick screencast](../../files/movies/Barcode_tutorial_small.mov) demonstrating
how a bar code might be used inside a museum.

Instructions
-----------------------------------------------------

A *report* is a named set of items in Omeka. You can create reports that encompass all items in the system, or choose to report on one specific item, or anything in between. Reports will automatically update as new items are added to Omeka.

### Creating a Report 
1.  Go to Admin - Reports
2.  Click the link in the top-right that reads "Add a Report."
3.  On the "Add" page, choose a name and a description for the report.
4.  On the "Edit Filter" page, you can choose the criteria under which items will be included in the report. Leaving the form blank will select all items in Omeka.

### Generating a File
Once you have created a report, you can create report files. To generate a file, you can either click the "Generate File" button on the main Reports page, or a specific report's details page (accessible by clicking the report's name).

The drop-down box next to the "Generate File" button allows you to select the type of report that will be generated.

The report will be generated in the background; you can refresh the report details page as the report's status changes from "In Progress" to "Completed."

### Built-in File Types

The Reports plugin ships with two output formats.

-   **HTML**
    -   Outputs all the metadata for each item as one HTML document

<!-- -->

-   **PDF (QR Code)**
    -   Outputs a PDF document containing [QR
        Codes](http://en.wikipedia.org/wiki/QR_Code) for each item, 10
        to a page.

Other report formats can be added (in the
Reports/libraries/Reports/ReportGenerator directory) to support
additional types of output (see [Extending](Reports.html#Extending)).

### <span id="Viewing_a_File" class="mw-headline"> Viewing a File </span>

All report files with a status of "Completed" on the report details page
have two links, allowing you to view or delete the file.

"View file" allows you to view the generated file in your browser. You
can then save the file to your local machine, and/or leave it on your
Omeka server.

"Delete file" deletes the generated file from your Omeka server. Before
clicking the "Delete file" link, make sure you have saved a copy of the
file if you want to keep it.

<span id="Extending" class="mw-headline"> Extending </span>
-----------------------------------------------------------

You can add new report output formats or edit the existing ones to add
or change the functionality of the reports plugin. The existing formats
give examples of how to accomplish PDF and HTML output, but you can add
other formats (text, XML, etc.) by creating new report generators.

### <span id="Adding_New_Formats" class="mw-headline"> Adding New Formats </span>

Report generators are stored in
Reports/libraries/Reports/ReportGenerator, and each generator is a PHP
class extending Reports\_ReportsGenerator.

All the generation takes place in the function generateReport(). For
examples of how to generate reports, study the two included report
generators.

### <span id="Altering_Existing_Formats" class="mw-headline"> Altering Existing Formats </span>

The included formats are an HTML and a PDF output. Both can be modified
from their original forms to suit specific needs.

When modifying a included report format, first make a copy of the file,
and change both the file name and the class name (so, for example, you
could copy HTML.php to HTMLCustom.php, and change the class name to
Reports\_ReportGenerator\_HTMLCustom).

The HTML report format is simple to edit. By default, all the elements
in all element sets are printed. You can replace this behavior with
printing only specific elements or specific element sets. This is
accomplished with the function \_outputSetElements(). It takes three
arguments. The first is the Item which will be printed, the second is
the name of the element set to print, and the third is an array of the
specific elements to print.

For example, this is the code that prints all elements for all sets (the
default).

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// Output all the metadata for all the element sets
foreach($sets as $set) :
    $this->_outputSetElements($item, $set->name);
endforeach;
```

</div>

</div>

In comparison, this would cause only Dublin Core elements to be printed:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// Output all Dublin Core elements
$this->_outputSetElements($item, 'Dublin Core');
```

</div>

</div>

Finally, this would cause only Dublin Core Item elements to be printed,
if any:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// Output all Dublin Core Title elements
$this->_outputSetElements($item, 'Dublin Core', array('Title'));
```

</div>

</div>

In this way, you can easily create a customized HTML report format. The
PDF output format can also be edited an customized, but requires some
more advanced techniques.

<div class="printfooter">

Retrieved from "[https://omeka.org/codex/Plugins/Reports](Reports.html)"

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

    [Page](Reports.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Plugins/Reports&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Plugins/Reports&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Plugins/Reports&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](https://omeka.org/codex/Special:WhatLinksHere/Plugins/Reports)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](https://omeka.org/codex/Special:RecentChangesLinked/Plugins/Reports)
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
