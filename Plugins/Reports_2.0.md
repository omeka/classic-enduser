Plugins/Reports 2.0
===================

<div id="contentSub">

<span class="subpages">&lt;
[Plugins](../Plugins.1.html "Plugins")</span>

</div>

<div id="primary">

<span id="Introduction" class="mw-headline"> Introduction </span>
-----------------------------------------------------------------

A report generates a named set of items in Omeka. You can create reports
that encompass all items in the system, or choose to report on one
specific item, or anything in between. Reports will automatically update
as new items are added to Omeka.

Reports and Bar Codes plugin allows users to create reports of Omeka
items in an HTML list and a PDF of QR codes [QR
Codes](http://en.wikipedia.org/wiki/QR_Code), (10 per page, by default)
as well as other formats you can customize in the plugin files.

If you are using Omeka.net, please see [instructions for this
plugin](http://info.omeka.net/build-a-website/manage-themes-and-plugins/reports-and-bar-codes/)
in Help pages for Omeka.net.

### <span id="Screencast" class="mw-headline"> Screencast </span>

*Please note, this screencast uses an older version of Omeka, but the
process for generating QR codes is the same.* Watch a [quick
screencast](../../files/movies/Barcode_tutorial_small.mov) demonstrating
how a bar code might be used inside a museum.

<span id="Instructions" class="mw-headline"> Instructions </span>
-----------------------------------------------------------------

Note that a new Reports directory will be created once the plugin is
uploaded to the plugin directory on your server be saved:
OmekaSitedirectory/files/reports/. This directory \*must\* be writable
by the server for reports to be generated.

1.  [Install](../Managing_Plugins_2.0.html#Installing_a_Plugin "Managing Plugins 2.0")
    the plugin from the admin/plugins page. The Reports tab will then
    appear in the left navigation of the admin Dashboard (admin/Reports)
2.  Click the link in the top-left of the screen that reads "Add a
    Report."
3.  On the "Add" page, choose a name and a description for the
    report.[![Report
    add.jpg](https://omeka.org/c/images/thumb/4/4e/Report_add.jpg/500px-Report_add.jpg)](https://omeka.org/codex/File:Report_add.jpg)
4.  Choose which items to include in the Report on the "Edit
    Filter" page. This is essentially creating an advanced item query;
    you need to choose criteria to filter the items for this report. If
    you leave the form blank, all items in the installation will be
    included in the report. Click Search to create the report.[![Reports
    filter.jpg](https://omeka.org/c/images/thumb/b/b8/Reports_filter.jpg/500px-Reports_filter.jpg)](https://omeka.org/codex/File:Reports_filter.jpg)
5.  The new report now appears on the admin/reports page.

### <span id="Generating_a_File" class="mw-headline"> Generating a File </span>

Once you have created a report, you can publish report files in HTML or
as QR Codes.

1.  From the admin/Reports page, To generate a file, you can either
    click the "Generate File" button on the main Reports page, or a
    specific report's details page (accessible by clicking the
    report's name).

[![Reports
generate.jpg](https://omeka.org/c/images/thumb/1/1c/Reports_generate.jpg/500px-Reports_generate.jpg)](https://omeka.org/codex/File:Reports_generate.jpg)

1.  The drop-down menu next to the “Generate File” button allows you to
    select the type of report that will be generated, HTML or PDF for
    QR Codes.

The report will be generated in the background. Refresh the report
details page as the report’s status changes from “In Progress” to
“Completed.”

### <span id="Viewing_a_File" class="mw-headline"> Viewing a File </span>

All report files with a status of "Completed" on the report details page
have two links, allowing you to view or delete the file.

[![Rerports generated
download.jpg](https://omeka.org/c/images/thumb/6/67/Rerports_generated_download.jpg/500px-Rerports_generated_download.jpg)](https://omeka.org/codex/File:Rerports_generated_download.jpg)

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

Retrieved from
"[https://omeka.org/codex/Plugins/Reports\_2.0](Reports_2.0.html)"

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

    [Page](Reports_2.0.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Plugins/Reports_2.0&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Plugins/Reports_2.0&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Plugins/Reports_2.0&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](https://omeka.org/codex/Special:WhatLinksHere/Plugins/Reports_2.0)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](https://omeka.org/codex/Special:RecentChangesLinked/Plugins/Reports_2.0)
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
