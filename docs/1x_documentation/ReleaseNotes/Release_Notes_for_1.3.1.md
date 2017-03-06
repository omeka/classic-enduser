---
title: Release Notes for 1.3.1
---
Omeka 1.3.1 is a bug-fix release. It was released on January 18, 2011.

The release addresses the following:

-   Ticket \#996 - Fixes the item\_file() helper when displaying files. Previous, this helper, incorrectly retrieved URLs for files. 
-   Ticket #1001 - Fixes inadvertently discarded collection data when migrating collections on upgrade. Upgrading database from 1.2.1 or earlier will now retrieve full names of collectors.
-   Ticket #1002 - Checks whether timezone is set in PHP 5.3. If not set, will ask the operating system.
-   Ticket #1003 - Fixes installer to prevent installation from breaking when non-alphanumeric characters are used for username.
-   Omeka admin now validates maintenance releases when checking 'tested\_up\_to' for plugins and themes.