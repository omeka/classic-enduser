---
title: Release Notes for 2.1
---

Omeka 2.1 was released on August 27, 2013.

**Note:** Due to an update to Zend Framework's requirements, Omeka 2.1 officially requires PHP version 5.2.11 or higher.

New Features 
-----------------------------------------------------

-   REST API
    -   GET, PUT, POST, and DELETE methods implemented for items, collections, files, item types, elements, and element sets.
    -   GET method available for users and tags.
    -   DELETE method available for tags.

Enhancements
-----------------------------------------------------

-   Keyword search for users
    (*[\#59](https://github.com/omeka/Omeka/issues/59)*)
-   Direct links to plugin support\_link sites
    (*[\#258](https://github.com/omeka/Omeka/issues/258)*)
-   Direct links to files from files/show
    (*[\#542](https://github.com/omeka/Omeka/issues/542)*)
-   `record_url()` now accepts query string parameters
    (*[\#549](https://github.com/omeka/Omeka/issues/549)*)
-   Added methods for on-the-fly changes to storage adapters
    (*[\#550](https://github.com/omeka/Omeka/issues/550)*)
-   Show tags for non-Item records in tags browse
    (*[\#568](https://github.com/omeka/Omeka/issues/568)*)
-   New `get_record()` helper for getting single records
    (*[\#591](https://github.com/omeka/Omeka/pull/591), contributed by
    Jeremy Boggs*)
-   View object now automatically available for background processes
    (*[\#593](https://github.com/omeka/Omeka/issues/593)*)

Bugs Fixes
---------------------------------------------------

-   Plugin versions were stored as type 'text'
    (*[\#492](https://github.com/omeka/Omeka/issues/492)*)
-   Too many plugins could make the bottom of the admin navigation
    unreachable (*[\#519](https://github.com/omeka/Omeka/issues/519)*)
-   Styling on admin files/show was overly restrictive for some content
    (*[\#555](https://github.com/omeka/Omeka/issues/555)*)
-   "does not contain" items advanced search was acting like "contains"
    (*[\#588](https://github.com/omeka/Omeka/issues/588)*)
-   Items advanced search was incorrectly excluding some results

Plugin API
-------------------------------------------------------------

-   New 'activate' and 'deactivate' plugin hooks
    (*[\#349](https://github.com/omeka/Omeka/issues/349)*)
-   New 'admin\_collections\_show\_sidebar' hook
    (*[\#520](https://github.com/omeka/Omeka/issues/520)*)

Localization 
---------------------------------------------------

-   Strings to translate updated
-   All languages updated

Updated Libraries
----------------------------------------------------------

-   Zend Framework 1.12.3
-   getID3 1.9.6
-   pheanstalk 2.1.0
-   HTMLPurifier 4.5.0
-   jQuery 1.10.1
-   jQuery UI 1.10.3