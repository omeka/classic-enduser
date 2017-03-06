---
title: Release Notes for 2.0.4
---

Omeka 2.0.4 is the fourth maintenance release for the 2.0 series. It was released on June 27, 2013.

Bugs Fixed
---------------------------------------------------

-   XSS vulnerabilities in the items and sitewide searches (*reported by Brad Spry*)
-   Permissions check bug and error on admin/files/show for contributor and researcher roles
    (*[\#569](https://github.com/omeka/Omeka/issues/569), reported by scampbell*)
-   Hooks for adding/removing tags weren't always fired
    (*[\#522](https://github.com/omeka/Omeka/issues/522)*)
-   Error on items/browse when using some incorrect or outdated search parameters (*[\#527](https://github.com/omeka/Omeka/issues/527)*)
-   Manual specific-page pagination broken on admin/users
    (*[\#530](https://github.com/omeka/Omeka/issues/530), reported by Wayne Graham*)
-   Admin sidebar nav can grow too long and make items on the bottom inaccessible (*[\#519](https://github.com/omeka/Omeka/issues/519)*)
-   Dervative file extension calculation was incompatible with     differently-formatted filenames
    (*[\#551](https://github.com/omeka/Omeka/pull/551), contributed by Daniel Berthereau*)
-   "Type" advanced searches were not preserved on the form
    (*[\#548](https://github.com/omeka/Omeka/pull/548), fix contributed by Jeremy Boggs\]*)
-   Some untranslated strings in some admin forms
-   "View Public Page" link was missing from admin/files/show
-   Nonfunctional "Delete" link shown for items even when user has no delete permissions

Localization
-----------------------------------------------------

-   Updated translations for: Catalan - Spain (ca\_ES), Greek (el\_GR), French (fr), Italian (it), Flemish (nl\_BE), Dutch (nl\_NL), Norwegian (no), Swedish (sv\_SE), Ukrainian (uk)

Add-ons
-----------------------------------------------

-   The bundled Exhibit Builder plugin is updated to 2.0.4, and the bundled Simple Pages is updated to 2.0.3. Both updates contain added and updated translations.