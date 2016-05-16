Plugins/ImageResize
===================


[Plugins](../Plugins.1.html "Plugins")


Image Resize plugins allows users to re-size image derivatives from
within the admin interface (for public and admin side displays of
thumbnails, square thumbnails, and full size images) without editing
theme files. We highly recommended that you backup the archive directory
before resizing images.

Version Requirements 
---------------------------------------------------------------------------------

1.5 and above

Installation
-----------------------------------------------------------------

1.  Upload and install the Image Resize plugin (see
    [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin"))
2.  Once activated, the plugin automatically creates a tab in the Admin
    navigation called Image Resize.

Resizing Images
-----------------------------------------------------------------------

-   Go to the Image Resize page (admin/image-resize), where you will
    find the a table listing the current image size constraints.
-   To change image sizes, enter in a new size contraint (in pixels),
    and check the box in the "Select to Resize" column.
-   When you have determined the new images sizes, click the "Resize
    Selected Images" button in the bottom right of the table.
    -   Please note that this plugin will override any settings you set
        in the admin/settings section when you first set up your
        Omeka site.
-   The process will begin, and will be tracked below. Refresh the page
    to check on the progress. Resizing may take awhile, because the
    process runs through your entire archive.
-   Once completed, you will changes will be implemented across
    your archive.