Plugins/PdfSearch
=================

[Plugins](../Plugins.1.html "Plugins")


Use the PDF Search plugin if you want your PDF files to be searchable
within Omeka.

This plugin enables searching on PDF files by extracting their texts and
saving them to their parent items. This normally happens automatically,
but there are times when you'll want to extract text from all PDF files
that exist in your Omeka archive; for example, when first installing the
plugin and when items are being created by other plugins. You can run
the bulk text extraction process in the plugin's configuration page. The
process may take some time to complete.

Your server must have an up-to-date [pdftotext](http://en.wikipedia.org/wiki/Pdftotext) command-line utility
installed for the plugin to function. If you get an error message while
attempting to install the plugin, you don't have the required utility.
Speak with your server administrator about installing pdftotext. Older
versions of pdftotext may result in garbled or incomplete text during
extraction, particularly when the PDF contains Unicode characters. Make
sure your server is using the pdftotext that's available in
[poppler-utils](http://linuxappfinder.com/package/poppler-utils), not
the outdated Xpdf version.
