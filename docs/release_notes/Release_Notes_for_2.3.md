---
title: Release Notes for 2.3
---

Omeka 2.3 was released on March 19, 2015.

Enhancements
----------------------------------------------------

-   Accessibility improvements (added ARIA roles and landmarks, improved labels, navigation skip links)
-   New file derivative strategy using PHP's GD extension
-   Built-in support for setting default sort orders for browse pages
-   Element dropdowns on item advanced search respect the admin-configured element sorting order ([\#643](https://github.com/omeka/Omeka/issues/643))
-   The admin-configured page limits for browse pages are used for more controllers, including plugins
-   The listing of items on collection pages now follows the admin page limits ([\#601](https://github.com/omeka/Omeka/issues/601))
-   Support for the new access control directives used by Apache 2.4     ([\#631](https://github.com/omeka/Omeka/issues/631))
-   URLs within the default citation output now include a span wrapper to allow specific styling
-   New interface for resetting customized navigation to default settings
-   Improved error output for exceptions
-   Detailed error messages are now always shown for exceptions during upgrade
-   Support for newer versions (4.2+) of PHPUnit
-   The API now accepts `sort_field` and `sort_dir` GET parameters for sorting results
-   Omeka will hide the "Path to ImageMagick" setting when an alternative derivative strategy is in use
-   The System Information panel now uses internal "folder" names for both themes and plugins
-   Improved translation coverage ([\#655](https://github.com/omeka/Omeka/pull/655), [\#659](https://github.com/omeka/Omeka/issues/659))

Bugs Fixes
-------------------------------------------------------------
 -   Tags were incorrectly treated as case-sensitive in some places
-   Assigning tags to records caused an SQL error for some newer MySQL servers
-   The item advanced search "does not contain" worked incorrectly with elements having multiple texts
-   API authentication did not work properly on installations with no database prefix
-   `browse_sort_links` for "bare" links handled attributes incorrectly ([\#648](https://github.com/omeka/Omeka/issues/648))
-   Setting a custom homepage including a query string would silently set that query on all pages
-   Upgrades could fail on some "strict mode" MySQL configurations
-   Upgrades directly from old 1.x versions could fail when migrating collections
-   Theme overrides of plugin views did not apply when on a different plugin's page ([\#635](https://github.com/omeka/Omeka/issues/635))
-   The display of item search filters did not always recognize when users filtered by tag
-   Automatic `alt` attributes for file display were over-escaped
-   Admin-side page titles on hover were over-escaped
-   Long titles for records indexed for the sitewide search could be silently truncated or cause an error
-   The sitewide search form did not respect the documented     `submit_value` option
-   Errors on individual items could cause the "Index Records" job to fail
-   Item Types did not properly clean up after themselves after they were deleted

Localization
-----------------------------------------------------

-   The Norwegian (no) translation has been moved to Norwegian Bokmål (nb).
-   New translations for Bulgarian (bg\_BG), Korean (ko\_KR).
-   Updates to many existing translations

External Libraries
-----------------------------------------------------------

Omeka 2.3 updates to the following versions of its external
dependencies:

-   Zend Framework 1.12.11
-   jQuery 1.11.2
-   jQuery UI 1.11.2
-   TinyMCE 3.5.11

Bundled Add-ons
-------------------------------------------------------

### Plugins

-   Exhibit Builder 3.2
-   Simple Pages 3.0.5

### Themes

-   Thanks, Roy 2.3
-   Seasons 2.3
-   Berlin 2.3

For Developers
------------------------------------------------------

For change information geared toward developers, see [What's New in Omeka 2.3](http://omeka.readthedocs.org/en/latest/whatsnew/2.3.html) on Omeka's Read the Docs site.

Acknowledgements
---------------------------------------------------------

The following members of the Omeka community contributed code, fixes,
and improvements to Omeka 2.3:

-   Erin Bell ([PR \#636](https://github.com/omeka/Omeka/pull/636))
-   Daniel Berthereau ([PR \#640](https://github.com/omeka/Omeka/pull/640), [PR \#647](https://github.com/omeka/Omeka/pull/647), [PR \#650](https://github.com/omeka/Omeka/pull/650), [PR \#652](https://github.com/omeka/Omeka/pull/652), [PR      \#653](https://github.com/omeka/Omeka/pull/653))
-   Adam Doan ([PR \#629](https://github.com/omeka/Omeka/pull/629))
-   Wayne Graham ([PR \#630](https://github.com/omeka/Omeka/pull/630))
-   Anna Michelle ([PR \#651](https://github.com/omeka/Omeka/pull/651))
-   Michał Seweryniak ([PR \#655](https://github.com/omeka/Omeka/pull/655))