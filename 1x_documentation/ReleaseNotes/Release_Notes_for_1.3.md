---
title: Release Notes for 1.3
---

Omeka 1.3 was released on December 20, 2010.

New Features
-----------------------------------------------------

-   Converts Omeka admin to use jQuery and jQuery UI. Updates admin panel to use external javascript files. Updates jQuery UI styles to override default behavior for buttons.
-   Disables Prototype by default, adds admin panel option to switch it back on if needed for other plugins.
-   Adds subnavigation ability to the nav, public\_nav, and public\_nav\_main global helper functions.
-   Adds sortable tables to the browse pages in the admin.
-   Adds a table for user activations.
-   Adds filter for theme options.
-   Refactors collections to simplify data entry for collector names. Collector names can now be entered one per line into a textarea on the form, and do not need to be users in Omeka.
-   Adds ReCaptcha code and settings to Omeka core.
-   Adds [Omeka.wysiwyg](Omeka.wysiwyg.html "Omeka.wysiwyg") JS function for implementing TinyMCE.
-   Allow theme configs to add the TinyMCE editor.
-   Allows plugins to find/use theme configuration options.
-   New helpers:
    -   element\_exists - Checks if an given element and element set are present in Omeka.
    -   public\_nav\_items - Navigation for the items/\* pages, with filter.
    -   queue\_js
    -   queue\_css
    -   button\_to
    -   delete\_button - Creates a form with a single delete button, used instead of links to a delete action.
-   New hooks:
    -   Adds hook to add content to simple browse view.
  
Fixed Tickets 
--------------
-   Fixes \#18 Adds sortable tables.
-   Fixes \#443 by adding a filter to the display HTML flag.
-   Fixes \#733, upgrades getID3 to version 2.0.0b6.
-   Fixes \#787 by adding a callback parameter to the loop\_records function, as well as updating loop\_items, loop\_collections, loop\_files, and loop\_item\_types to internally specify their callback functions to loop\_records.
-   Fixes \#900 Adds notification that image derivatives are not being created.
-   Fixes \#905, files in Omeka are stored with hashed filenames.
-   Fixes \#912, organizes elements by element set when used in a form select.
-   Fixes \#916, logout should destroy session and its data.
-   Fixes \#929 RSS2 outputs don't return error when files are associated with items.
-   Fixes \#942 by adding a function to convert URL strings to links.
-   Fixes \#944, adds explanatory text in theme config that theme configuration is on a per-theme basis.
-   Fixes \#958, allows superusers to change all user passwords.
-   Fixes \#961 password reset no longer sent to deactivated users.

Miscellaneous Improvements
---------------------------------------------------------------
-   Improved test coverage of Omeka core. Refactors tests to make use of PHPUnit's test suites.
-   Fixes installer to set the 'enable\_header\_check\_for\_file\_mime\_types' flag based on whether the fileinfo extension is loaded.
-   Fixes users/edit action to redirect back to dashboard instead of users/browse when a user edits their own info.
-   Fixes mod\_rewrite checking in installer by explicitly allowing access to check-mod-rewrite.html, which could be blocked by more restrictive .htaccess configurations.
-   Converts database migrations to use timestamps instead of incremented integers.
-   Fixes security hole where form POST could modify a user's salt.
-   Updates url\_to\_link function to use preg\_replace instead of ereg\_replace; Moves url\_to\_link function to the admin theme's custom.php file.
-   Fixes a javascript bug where the first Use HTML checkbox would save a blank value.
-   Fixes a bug on users form where user data was not displayed after invalid password change attempt.
-   Fixes Omeka\_Core to display the generic error page for all uncaught exceptions.
-   Fixes bug in item\_has\_type helper to use the get magic method to retrieve a given item's item type name instead of using the item() view helper.
-   Fixes bug in show\_item\_metadata / ItemMetadataList. Previous code only works correctly when the item being displayed is the "current item" on the view, would cause fatal error if the item has a type.
-   Fixes media helpers for display of AVI,WMV,WMA (particularly on Mac).
-   Fixes theme file upload validation check. Reverses check over so the validation will be enabled unless the "disabled" option is equal to 1, leaves validation on in case of an invalid or null value for the option. Adds file size and restricted type/ext validation for  theme uploads.
-   Moves "add" button for advanced search out of each row. Disables remove buttons when there is only one row.
-   Select form element for element sets are now organized by set.
