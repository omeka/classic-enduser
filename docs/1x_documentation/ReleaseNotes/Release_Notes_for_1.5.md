---
title: Release Notes for 1.5
---

Omeka 1.5 was released on February 7, 2012.

New Features
-----------------------------------------------------------------

-   **Internationalization:** Users can now choose a language and locale to display the interface in. This affects the displayed text and formatting of other data like system-generated dates.
-   **Media Extension Awareness:** File extensions are now used as a fallback to determine how files should be displayed if the MIME type is incorrect or not detected.
-   **File Ordering:** Users can now reorder files within an item without re-uploading.

Bug Fixes
-----------------------------------------------------------

-   Files form doesn't automatically print extra element sets     ([\#34](https://github.com/omeka/Omeka/issues/34))
-   Item Type controller shows a "has encountered an error" page instead of a flash error ([\#70](https://github.com/omeka/Omeka/issues/70))
-   "Uninstall" button is enabled for plugins that need to be upgraded ([\#82](https://github.com/omeka/Omeka/issues/82))
-   "Add User" form lets you pick Active/Inactive ([\#89](https://github.com/omeka/Omeka/issues/89))
-   Retry when HTTP errors occur for S3 ([\#94](https://github.com/omeka/Omeka/issues/94))
-   Certain fields for collections should allow null ([\#95](https://github.com/omeka/Omeka/issues/95))
-   Incorrect URL building in collections/index/page/n ([\#96](https://github.com/omeka/Omeka/issues/96))
-   has\_permission always returns false if you're not logged in ([\#99](https://github.com/omeka/Omeka/issues/99))
-   New item types with duplicate names override the original  description ([\#125](https://github.com/omeka/Omeka/issues/125))

Changes
-------------------------------------------------------

-   The plugins page no longer warns about plugins that haven't been tested up to the current Omeka version.
-   Early errors that occur when starting Omeka are now logged to the PHP log.

For Developers
------------------------------------------------------

-   The new Omeka\_Plugin\_Abstract class gives developers an optional framework to simplify class-based plugins.
-   Plugin-added element sets can apply to specific record types.

### Library Upgrades
-   Zend Framework 1.11.11
-   jQuery 1.7.1
-   jQuery UI 1.8.16
-   TinyMCE 3.4.7-jQuery

### New Functions

-   add\_translation\_source()
-   get\_html\_lang()
-   format\_date()
-   queue\_js\_string()
-   queue\_css\_string()

### New Hooks

-   admin\_append\_to\_files\_show

### New Filters

-   display\_file