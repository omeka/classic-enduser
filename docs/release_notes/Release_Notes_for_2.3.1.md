---
title: Release Notes for 2.3.1
---

Omeka 2.3.1 is the first maintenance release for version 2.3. It was released on August 27, 2015.

Enhancements  
-----------------------------------------------------------------

-   It is now possible to view tags assigned to zero records in the  admin interface for tags
-   The item shortcodes now allow filtering by item type     ([\#668](https://github.com/omeka/Omeka/issues/668)).
-   Invalid strings are now handled more gracefully when using PHP 5.4 or newer
-   The full set of available filters for Items are now available for use in the API
-   The ExternalImageMagick and Imagick file derivative strategies now have a `autoOrient` option to automatically fix the orientation of images that have an embedded orientation flag.

Bugs Fixed  
-------------------------------------------------------------

-   An error occurred when adding tags differing only in trailing spaces
-   Sessions containing invalid UTF-8 text data could be dropped or truncated
-   Invalid element text records could cause nonsensical API output
-   Element texts could be duplicated if a record was saved more than once in a single request
-   The linkToMetadata option for file\_markup could cause a PHP notice
-   The Imagick derivative strategy handled images with layers and transparency improperly
-   The Mixin\_ElementText::getAllElementTextsByElement function     introduced in 2.3 did not work correctly ([\#662](https://github.com/omeka/Omeka/pull/662,), fix contributed by Daniel Berthereau)
-   There was a typo in the admin interface ([\#664](https://github.com/omeka/Omeka/pull/664), fix contributed by Zach Ploskey)

Changes  
-------------------------------------------------------

-   PHP's error reporting level is now set the same regardless of the "environment" setting

 Localization  
-----------------------------------------------------------------

-   New translation for Latvian (lv\_LV)
-   Updates for Czech (cs), Estonian (et), Italian (it), Dutch (nl\_NL), Polish (pl), Swedish (sv\_SE), and Turkish (tr\_TR).

Bundled Add-ons  
-----------------------------------------------------------------------

### Themes  

-   Thanks, Roy 2.3.1 (fixed a problem with site logos not showing
    correctly on item pages)

###  Plugins  

-   Exhibit Builder 3.2.1 (fixed a problem that sometimes prevented exhibits from being deleted, updated translations)
-   Simple Pages 3.0.6 (updated translations)
