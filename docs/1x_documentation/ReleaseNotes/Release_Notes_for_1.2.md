---
title: Release Notes for 1.2
---
Omeka 1.2 was released on April 8, 2010.

Core Changes
-----------------------------------------------------------------

-   Adds theme configuration capabilities on a per-theme basis. Theme writers can now add configuration options to their themes, which can be changed by Omeka users from admin.
    -   Such configurations include switching CSS-style sheets and adding a logo to the theme's header.
-   Adds two new configurable themes to the pre-packaged group of     themes: Seasons and Rhythm.
    -   Rhythm offers three style sheets for different color palettes. Seasons offers four style sheets and option for uploading a logo file.
-   Adds security setting to enable/disable checking a file MIME type by looking at the file header.
-   Updates the omeka-xml output to use version 3 of the schema.
-   Adds a commented-out RewriteBase rule to various .htaccess files in Omeka.

Admin Theme Changes
------------------------------------------------------------

-   Adds button for configuring themes, if they have a configuration form.
-   Add styles to resize img and object elements to prevent overflowing in admin; Updates files/show.php and items/show.php to use the fullsize image when available.
-   Updates the Item Type edit form, to make adding elements to an Item Type more user friendly.
-   Fixes bug where form errors were not displaying correctly.
-   Adds cautionary text in confirm boxes for delete item, delete element set, delete item type, delete collection, delete user, and remove element from item type.

API Changes
---------------------------------------------------------------

-   Adds get\_theme\_option helper to retrieve current theme options set in the admin.
-   Updates image helpers for images so that they use the 'alt' option first, then the description in the file metadata, then the title in the file metadata, and finally, if these are unavailable, the item title.
-   Fixes get\_collections() helper to allow returning collections that are both public and featured.
-   Deprecates form helpers in favor of Zend Form methods. The following helpers can still be used, but will be removed in a future release:
    -   label()
    -   textarea()
    -   input()
    -   select()

Miscellaneous
-------------------------------------------------------------------

-   Update Zend to version 1.9.7.