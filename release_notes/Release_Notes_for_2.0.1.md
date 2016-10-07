---
title: Release Notes for 2.0.1
---

Omeka 2.0.1 is the first maintenance release for the 2.0 series. It was released on February 21, 2013.

Bugs Fixed
-------------------------------------------------------------
-   Error messages from upgrading plugins were impossible to see
-   Adding new checkbox inputs to an admin element form would improperly affect the HTML editor status of(*[\#480](https://github.com/omeka/Omeka/issues/480), reported by Iwe Muiser*)
-   Spurious notice that triggered when loading views for some plugins (*[\#481](https://github.com/omeka/Omeka/issues/481), [\#484](https://github.com/omeka/Omeka/issues/484), reported and fix contributed by Dave Widmer*)
-   Installer error on some systems when guessing ImageMagick path (*[\#482](https://github.com/omeka/Omeka/issues/482)*)
-   The new version indicator was missing (*[\#485](https://github.com/omeka/Omeka/issues/485)*)
-   New invalid Item Types were partially added (*[\#487](https://github.com/omeka/Omeka/issues/487), reported by Jeremy Boggs*)

Localization
----------------------------------------------------
 -   Internationalized the new search results page (*reported and code contributed by Matti Lassila, [\#474](https://github.com/omeka/Omeka/pull/474)*)
-   Internationalized the item citation output (*reported and code     contributed by Matti Lassila, [\#476](https://github.com/omeka/Omeka/pull/476)*)
-   New translations for Tamil and Indonesian
-   Many updates to the existing translations

Addon Updates
------------------------------------------------------

### Plugins
-   Exhibit Builder is updated to version 2.0.1, fixing issues with upgrading and duplicate page slugs.
-   Coins is updated to version 2.0.1, resolving high memory and     database usage problems with the previous version.

### Themes

-   Thanks, Roy and Seasons are both updated to 2.0.1.