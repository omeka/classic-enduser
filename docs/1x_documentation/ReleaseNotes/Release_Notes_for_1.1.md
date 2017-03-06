---
title: Release Notes for 1.1
---

Omeka 1.1 was released on October 15, 2009.

Core Changes 
-----------------------------------------------------------------

-   Omeka now shows only completed metadata for items by default. Adds an option in the settings panel to show all item metadata.
-   Adds an Omeka XML schema, and implements that schema in new outputs.
-   Adds PHP CLI setting to config.ini, for plugins to use instead of  adding a setting.
-   Validation on the installer form and settings form. Adds helpful descriptions to settings fields.
-   Updates the File MIME Type listing in the Media helper

Admin Interface Improvements
------------------------------------------------------------------------------------------------

-   Makes language in admin UI more consistent
-   Adds total number of items links for both admin collection browse pages and item type browse pages. \[4477\]
-   Plugins Page
    -   Uses metadata in plugin.ini file.
    -   Enforces plugin dependencies
    -   Adds plugin Upgrade button.
    -   Uninstalling - Establishes a new process for uninstalling plugins, including a confirmation page with a modifiable uninstall message.
-   Removing a collector takes user back to the collections/edit page instead of redirecting to the collections/show page.
-   Adds a 'View on Public Site' link on admin/items/show and admin/collections/show.
-   Database upgrade notice and button is now visible on all Admin pages.

API changes
---------------------------------------------------------------

-   Theme API:
    -   Updates the item() helper to add 'date modified' as a
        special argument. \[4303\]
    -   New helper functions for Item Files \[4470\]
        -   recent\_files()
        -   set\_files\_for\_loop()
        -   get\_files()
        -   get\_files\_for\_loop()
        -   loop\_files()
        -   has\_files()
    -   New helper functions for Item Types \[4477\]
        -   get\_item\_types\_for\_loop()
        -   set\_item\_types\_for\_loop()
        -   loop\_item\_types()
        -   set\_current\_item\_type()
        -   get\_current\_item\_type()
        -   has\_item\_types\_for\_loop()
    -   New helper functions for linking to items browse pages \[4477\]
        -   link\_to\_items\_in\_collection()
        -   link\_to\_items\_with\_item\_type()
    -   collection() helper function - now includes parameter for specific Collection \[4501\]
    -   item\_image() helper function - uses the given item object for displaying alt text \[4501\]
    -   link\_to() helper function - adds a parameter for an array of query parameters \[4477\]
    -   display\_random\_featured\_item() helper function - does not set the current item to prevent conflicts with items set elsewhere (like on items/show) \[4501\]
    -   display\_random\_featured\_collection() helper function - does not set the current collection to prevent conflicts with collections set elsewhere (like on collections/show) \[4501\]
-   Plugin API:
    -   Background processes - plugins can now easily encapsulate,
        instantiate, and run background processes \[4466\]
        -   Adds Process class
        -   Adds ProcessAbstract class
        -   Adds ProcessDispatcher class
        -   Adds ProcessTable class
    -   New helper functions:
        -   get\_specific\_plugin\_hook\_output() - gets the output of a specific hook belonging to a specific plugin. \[4322\]
    -   New plugin hooks:
        -   admin\_append\_to\_plugin\_uninstall\_message() - Lets plugin developers customize the uninstall message. \[4322\]
        -   upgrade()
        -   plugin\_append\_to\_admin\_site\_info() - Lets plugin developers add HTML to to the site\_info panel in the admin header.
        -   after\_save\_record()
        -   before\_save\_record()
        -   before\_save\_form\_record()
        -   after\_save\_form\_record()
        -   before\_delete\_record()
        -   after\_delete\_record()
        -   before\_insert\_record()
        -   after\_insert\_record()
        -   before\_update\_record()
        -   after\_update\_record()
        -   before\_validate\_record()
        -   after\_validate\_record()

Security Fixes 
------------------------------------------------------

-   Fixes XSS vulnerability in several helper functions. (\#838)
-   Uses html\_escape on URLs when necessary.

Miscellaneous
------------------------------------------------------
-   Updates Zend to version 1.9.2.
-   Fixes a bug in the installer that only allows alpha-numeric characters in the password during validation. \[4408\]
-   Fixes a bug in Collection::totalItems() that returned the wrong count when there were collections of the same name. \[4298\]
-   \#688 Properly extract IPTC metadata during file uploads. \[4396\]
-   \#716 fixes errors when using snippet on strings shorter than the number of characters specified \[4240\]
-   \#801, which prevents users from adding a tag with name '0'. Also fixes the search item filtering so that it finds the a tag called '0'.
-   \#779, Sets the session name to a hash of BASE\_DIR, which is unique and unchanging for every Omeka installation. . This lets users log in at www.example.com, and still be logged in at example.com.