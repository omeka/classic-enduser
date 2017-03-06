---
title: Release Notes for 2.0.2
----

Omeka 2.0.2 is the second maintenance release for the 2.0 series. It was released on March 19, 2013.

Bugs Fixed
-------------------------------------------------------------

-   An error occurred when clicking on File search results in the public theme (*[\#494](https://github.com/omeka/Omeka/issues/494)*)
-   Titles of files that had HTML got double-escaped     (*[\#490](https://github.com/omeka/Omeka/issues/490)*)
-   Contributor users didn't get the Item Type form that should appear when you change types, though it would work after saving and re-editing (*[\#499](https://github.com/omeka/Omeka/issues/499)*, reported by Iwe Muiser)
-   The entire top admin menu depended on "Plugins" permissions (reported by Iwe Muiser)
-   Alternate output formats were broken on some FastCGI hosts (*[\#502](https://github.com/omeka/Omeka/issues/502)*)
-   The error reporting switch was broken on some FastCGI hosts

Performance Improvements
----------------------------------------------------------------

-   A new, faster query is used for the Item-specific advanced search
-   Removed a query that checked for the sessions table on every request
    (*[\#498](https://github.com/omeka/Omeka/issues/498)*)
-   Sorting is now automatically skipped when searching for a single record (*[\#496](https://github.com/omeka/Omeka/issues/496)*)

Localization 
----------------------------------------------------
-   New Swedish translation
-   Updated translations: French (fr), Croatian (hr), Italian (it), Japanese (ja), Flemish (nl\_BE), European Portuguese (pt\_PT), Serbian (sr\_RS), Chinese (China) (zh\_CN)

Addon Updates
-------------------------------------------------------------------

### Plugins
-   Exhibit Builder is updated to version 2.0.2, fixing a major issue with deleting exhibits and pages.

### Themes
-   Berlin is now packaged with Omeka
