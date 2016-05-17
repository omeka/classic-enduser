<div id="wrap">

[Skip Navigation](TeiDisplay.html#content)
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
    In](https://omeka.org/c/index.php?title=Special:UserLogin&returnto=Plugins/TeiDisplay)

</div>

Plugins/TeiDisplay
==================

<div id="contentSub">

<span class="subpages">&lt;
[Plugins](../Plugins.1.html "Plugins")</span>

</div>

<div id="primary">

<span id="About_TeiDisplay" class="mw-headline"> About TeiDisplay </span>
-------------------------------------------------------------------------

TeiDisplay is a plugin created by the [Scholars'
Lab](http://scholarslab.org/) at the University of Virginia Library.
This will render an uploaded TEI file attached to an item in the
display. The default XSLT stylesheet allows for two display types:
entire and segmental. The entire display type will render out the entire
document in HTML while the segmental display type includes a table of
contents for displaying a selected div1 or div2, which is a useful
feature for larger documents. The display type and XSLT stylesheet can
be customized for each TEI File in the database through the TEI Config
tab in the administrative interface. Additionally, metadata from the TEI
Header is automatically mapped to Dublin Core fields for both the item
and file.

<span id="Requirements_in_the_TEI_Document" class="mw-headline"> Requirements in the TEI Document </span>
---------------------------------------------------------------------------------------------------------

The TEI document requires an id attribute in the TEI.2 root element. For
the table of contents in the segmental display to work properly, each
div1, div2, or div element at the top two levels under &lt;front&gt; or
&lt;body&gt; must also have an id attribute since generate-id() does not
provide the consistent results in PHP-XSL as it does in Xalan or Saxon.
The Entire display type will function without ids attached to divs.

### <span id="Required_Yum_or_Aptitude_Packages" class="mw-headline"> Required Yum or Aptitude Packages </span>

-   php-xml
-   php-xsl

<span id="Download" class="mw-headline"> Download </span>
---------------------------------------------------------

-   Subversion: <https://addons.omeka.org/svn/plugins/TeiDisplay/trunk/>
-   Package: [TeiDisplay
    0.9](http://www.scholarslab.org/wp-content/uploads/2010/09/TeiDisplay-0.9.zip)

<span id="Installing_and_Configuring" class="mw-headline"> Installing and Configuring </span>
---------------------------------------------------------------------------------------------

1.  The php5-xsl package is required for transformation. Please refer to
    Google for directions for installing the package on your
    operating system.
2.  Checkout from svn or download/extract zipped package to
    omeka/plugins (see
    [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin")).
3.  Install TeiDisplay on the Settings-&gt;Plugins page.
4.  Use the plugin Configure page to set the default stylesheet
    (default.xsl is packaged in libraries) and the display type (entire
    by default).
5.  XML uploads need to be enabled. Go to admin Settings-&gt;Security
    Settings and add 'xml' to allowed file extensions and
    'text/xml,application/xml' to allowed file types.
6.  To upload a new TEI file, create an item. Select an appropriate TEI
    file to upload from the disk. Save the item, and metadata will be
    pulled from the header automatically. The Type field in the File
    metadata is set to 'TEI Document.'
7.  The TEI Config tab can be used to change the default display
    behavior for each TEI XML File
8.  Edit the item display for your theme in themes/\[your
    theme\]/items/show.php . Add the following code where you wish the
    TEI document to be serialized (e. g., under the titles and above
    show\_item\_metadata()):

<!-- -->

    <?php if (function_exists('tei_display_installed')){ echo render_tei_files($item->id,  $_GET['section']); } ?>

<span id="XSLT_Stylesheet_Customization" class="mw-headline"> XSLT Stylesheet Customization </span>
---------------------------------------------------------------------------------------------------

The TeiDisplay/libraries folder contains XSLT stylesheets made available
to the plugin for serialization customization. All stylesheets require
two parameters, one for the display type ("entire" and "segmental") and
the other used in the segmental display for section. Refer to
default.xsl in the folder for an example. Below is the root template:

        <xsl:param name="display"/>
        <xsl:param name="section"/>

        <xsl:template match="/">
            <div id="tei_display">
                <xsl:choose>
                    <xsl:when test="$display = 'entire'">
                        <xsl:apply-templates select="//body"/>
                    </xsl:when>
                    <xsl:when test="$display='segmental'">
                        <div class="tei_toc">
                            <xsl:call-template name="toc"/>
                        </div>
                        <div class="tei_content">
                            <xsl:choose>
                                <xsl:when test="string($section)">
                                    <xsl:apply-templates select="descendant::node()[@id=$section]"/>
                                </xsl:when>
                                <xsl:otherwise>
                                    <xsl:apply-templates select="//front"/>
                                </xsl:otherwise>
                            </xsl:choose>
                        </div>
                    </xsl:when>
                </xsl:choose>
            </div>
        </xsl:template>

If one is familiar with XSLT, he or she can see that if the "entire"
display type is selected, a template is called on the TEI &lt;body&gt;.
If the display type is "segmental", the table of contents and TEI
content divs are constructed. The style of div.tei\_toc and
div.tei\_content is controlled in the plugin's public CSS file, and
therefore customized stylesheets should include divs of these classes
unless the CSS file will be modified.

<span id="FedoraConnector.2FTeiDisplay_Integration" class="mw-headline"> FedoraConnector/TeiDisplay Integration </span>
-----------------------------------------------------------------------------------------------------------------------

As of December 2010, the TeiDisplay plugin integrates with
FedoraConnector plugin functions (if the plugin is installed) to render
TEI datastreams directly from a Fedora repository. The plugins assume a
Text Encoding Initiative XML datastream is designated the id "TEI" in
Fedora. This can be modified in TeiDisplay/plugin.php
tei\_display\_install() and FedoraConnector/plugin.php
render\_fedora\_datastream(). Like Omeka Files, TEI files can be
configured for segmental/entire display and custom stylesheets.

<span id="Other_Notes" class="mw-headline"> Other Notes </span>
---------------------------------------------------------------

It is possible to upload multiple TEI files per item, but it is not
recommended. The documents can be displayed in their entirety, but
problems will arise attempting to render multiple TEI documents in
Segmental display mode. The metadata from multiple files will populate
the item metadata, but that metadata is not removed from the item if a
file is deleted.

<div class="printfooter">

Retrieved from
"[https://omeka.org/codex/Plugins/TeiDisplay](TeiDisplay.html)"

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

    [Page](TeiDisplay.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](https://omeka.org/c/index.php?title=Talk:Plugins/TeiDisplay&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](https://omeka.org/c/index.php?title=Plugins/TeiDisplay&action=edit)
-   <div id="nav-history">

    </div>

    [History](https://omeka.org/c/index.php?title=Plugins/TeiDisplay&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](https://omeka.org/codex/Special:WhatLinksHere/Plugins/TeiDisplay)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](https://omeka.org/codex/Special:RecentChangesLinked/Plugins/TeiDisplay)
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
