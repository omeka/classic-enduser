---
title: Release Notes for 1.4
---

Omeka 1.4 was released on June 22, 2011.

General
-------------------------------------------------------

-   Batch editing for items
-   Improved update and installation scripts
-   Improved error handling and logging
-   Improved upload file handling
-   Allows configuration of tag delimiter
-   Improvements to database date and time formatting
-   Improvements to advanced search
    -   New "is exactly" advanced search type
    -   Fixed "is null" and "does not contain" search types
-   Atom feed output
    -   Next, previous, last, and first links
-   Improved user and access control handling
-   Miscellaneous tweaks and bedazzlings

Library Updates 
-------------------------------------------------------

-   Updated Zend Framework to 1.11.6
-   Updated jQuery to 1.6.1
-   Updated jQuery UI to 1.8.13
-   Updated TinyMCE to 3.4.2-jQuery

Security
---------------------------------------------------------

-   Cross Site Scripting and AJAX vulnerabilities addressed
-   CSRF protection for delete actions

UI/UX
-----------------------------------------------------

-   Improvements to admin theme
-   Many improvements and fixes to media helpers, esp. for display of AVI, WMV, WMA
-   Improvements to theme configuration
    -   TinyMCE integration
    -   Image preview
-   Improved item citation style
-   Modal AJAX for delete/confirm

For Developers
-------------------------------------------------------

-   Omeka\_Job component for background jobs (e.g., importing)
-   Omeka\_Storage Layer
    -   Amazon S3 storage
-   New functions
    -   plugin\_is\_active
    -   link\_to\_items\_atom
    -   clear\_filters
    -   body\_tag
    -   auto\_discovery\_link\_tags
    -   \_log
    -   random\_featured\_items
    -   [plugin\_body
    -   plugin\_page\_header
    -   plugin\_page\_content
    -   url\_to\_link
-   New filters
    -   item\_citation filter
-   New global functions
-   Deprecated functions
    -   auto\_discovery\_link\_tag

Tests
---------------------------------------------------

-   Tests now require PHPUnit 3.5 or newer
-   Fakemail no longer required for testing
-   Added test suites:
    -   All