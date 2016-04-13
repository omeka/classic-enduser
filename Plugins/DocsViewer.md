Plugins/DocsViewer
==================


[Plugins](../Plugins.1.html "Plugins")


Embeds a Google document viewer into item show pages. [Several file types are supported](http://docs.google.com/support/bin/answer.py?hl=en&answer=1189935).
Some files may take a long time to load, and some may not load at all,
depending on file size, connection speed, and other variables. By using
this service you acknowledge that you have read and agreed to the
[Google Docs Viewer Terms of Service](http://docs.google.com/viewer/TOS?hl=en).

Installation 
-----------------------------------------------------------------

1.  Upload and install the Docs Viewer plugin (see
    [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin"))
2.  Configure the plugin in Omeka (see below)

If you are using Omeka.net, go to the [instructions in the Help section of Omeka.net](http://info.omeka.net/build-a-website/manage-themes-and-plugins/docs-viewer/).



Configuration
-------------------------------------------------------------------

-   **Embed viewer in admin/public item show pages?**: Check whether to
    automatically append the document viewer to the admin/public item
    show pages, if a valid document exists for that item.
-   **Viewer width, in pixels**: The width of the document viewer, in
    pixels, (admin or public).
-   **Viewer height, in pixels**: The height of the document viewer, in
    pixels, (admin or public).

If you do not wish to automatically append the document viewer to the
item show pages, you have full control over the placement of the viewer
by toggling off the "Embed viewer in..." checkbox in the plugin's
configuration form, and adding the following code block to your theme's
items/show page:


``` {.de1}
<?php
if (class_exists('DocsViewerPlugin')):
   $docsViewer = new DocsViewerPlugin;
   $docsViewer->embed();
endif;
?>
```

