---
title: Release Notes for 2.2
---

Omeka 2.2 was released on July 2, 2014.

 New Features  
-----------------------------------------------------------------

### Shortcodes  

-   Omeka now supports [shortcodes](http://omeka.org/codex/Shortcodes "Shortcodes") for embedding content such as a list of recent or featured items, as well as plugin content, such as a map from the Geolocation plugin.
-   The new Simple Pages plugin bundled with Omeka supports shortcodes in the page text.

###  Derivative Images  

-   Configurable and extensible derivative image (thumbnail) creation 
-   Blacklisting and whitelisting image creation by MIME type in config.ini
-   Support for using `ext/imagick` instead of command-line ImageMagick
-   The default ImageMagick derivative creator no longer separately tries to run `identify`; this can double thumbnail creation speed for some files

### Representative Files for Records  

-   Any record type can return a "representative" file Omeka can use for displaying thumbnails
-   Collections and Exhibits select a representative image for
    themselves and so will show thumbnails on the front page, their
    browse pages, and in shortcodes
-   Items, Files, Collections, Exhibits, and any other records with
    representative images will show thumbnails on sitewide search
    results

### <span id="Appearance" class="mw-headline"> Appearance  

-   Admins can hide the header listing the element set ("Dublin Core")
    on item/collection/file pages through Appearance Settings
-   Additional fallback thumbnail icons for audio, video, and image
    types
-   Sorting links on the default public collections browse view
-   Common "single.php" themeable display for Items, Collections, and
    Exhibits used in recent and featured sections and shortcodes
-   Dev-editable button text for items-specific search

### <span id="Admin_Interface" class="mw-headline"> Admin Interface  

-   New interface for manually resending the user activation email message to a user.
-   The user edit page is split among three subpages and more closely follows the admin style
-   The Item-specific advanced search page more closely follows the admin style
-   The File edit page has tabs for each element set and filter-added section, like the Item and Collection add/edit pages
-   The dropdown for selecting a Collection for an item is sorted alphabetically by collection title
-   HTML edit boxes for metadata will automatically grow with the text input

### Security  

-   Admins can now specify more Allowed HTML Elements, such as `iframe`
-   Ability to enable or disable element filtering for the API

### Other  

-   Username restrictions greatly relaxed to allow email addresses as usernames
-   Theme configuration can now be divided into named sections
-   Accessibility improvements throughout the admin and public themes
-   jQuery and jQuery UI now automatically fall back to local copies if the CDN copy can't be loaded
-   All records can be sorted randomly
-   Search term input on "Narrow by Specific Fields" disables for "is empty" and "is not empty" types
-   Files can be internally filtered by original filename (*[\#616](https://github.com/omeka/Omeka/pull/616), thanks to Daniel Berthereau*)
-   Simple "OR" searches on records by providing an array of values (*[\#622](https://github.com/omeka/Omeka/pull/622), thanks to Daniel Berthereau*)

Bugs Fixed  
-------------------------------------------------------------

-   MIME types could be incorrectly set for multiple files uploaded     simultaneously
-   HTML in titles shown incorrectly on batch-edit
-   Invalid XML characters could break omeka-xml and omeka-json output (*[\#617](https://github.com/omeka/Omeka/pull/617), thanks to Rachel     Donahue*)
-   Emails sent by Omeka did not support non-Latin characters (*[\#618](https://github.com/omeka/Omeka/pull/618), thanks to Marios Bekatoros*)
-   Element names were not localized on items/browse listing of filters (*[\#620](https://github.com/omeka/Omeka/issues/620), thanks to Matti Lassila*)
-   On the item-specific advanced search, "does not contain" did not include items that completely omitted the element (*[\#621](https://github.com/omeka/Omeka/pull/621), thanks to Daniel     Berthereau*)

Localization  
----------------------------------------------------------------

Add-ons  
-------------------------------------------------------

### Bundled Plugins  

-   Exhibit Builder 3.1
-   Simple Pages 3.0

### Bundled Themes  

-   Thanks, Roy 2.2
-   Seasons 2.2
-   Berlin 2.2

### Incompatibilities  

A small number of plugins need to be upgraded to work with version 2.2:

-   [Derivative Images](../add-ons/plugins/derivative-images.1.html) must be upgraded to version 2.0
-   [Item Order](../add-ons/plugins/item-order.1.html) must be upgraded to version 2.0.1

For Developers  
---------------------------------------------------------------------

For release information aimed at developers, see [What's new in Omeka 2.2](http://omeka.readthedocs.org/en/latest/whatsnew/2.2.html) in the developer documentation.

###  Library Updates  

-   Zend Framework 1.12.7
-   HTML Purifier 4.6.0
-   jQuery 1.11.1
-   jQuery UI 1.10.4
-   TinyMCE 3.5.10 (jQuery version)