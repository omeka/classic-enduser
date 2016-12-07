Plugins/PdfMeNot
================

[Plugins](../Plugins.html "Plugins")


The **PdfMeNot plugin** embeds [PdfMeNot](http://www.pdfmenot.com/)
document viewers into your Omeka item pages.

Developed by the web startup workshop [Stateless Systems](http://www.statelesssystems.com), PdfMeNot is a free service
that converts your documents to a format that is viewable within in your
web browser. With Omeka's PdfMeNot plugin you'll be able to
automatically convert your .pdf files and embed them directly into your
website. PdfMeNot only supports Portable Document Format (pdf).

Installation 
-----------------------------------------------------------------

1.  Upload and activate the PdfMeNot plugin (see
    [Installing\_a\_Plugin](../Installing_a_Plugin.html "Installing a Plugin"))
2.  Configure the plugin in Omeka (see below)

Using the PdfMeNot plugin
-------------------------------------------------------------------------------------------

The PdfMeNot plugin has several configurations:

-   The height of the PdfMeNot viewer, in pixels (required)
-   The width of the PdfMeNot viewer, in pixels (required)

If you want to include the PdfMeNot functionality in your public theme,
follow these steps:

Within your items/show.php template file write the following code
anywhere you want the PdfMeNot document viewer(s) to appear:



``` {.de1}
<?php
if (function_exists('PdfMeNot_embed')):
    PdfMeNot_embed($item);
endif;
?>
```

