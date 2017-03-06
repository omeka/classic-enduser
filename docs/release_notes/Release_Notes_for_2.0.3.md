---
title: Release Notes for 2.0.3
---
Omeka 2.0.3 is the third maintenance release for the 2.0 series. It was released on April 25, 2013.

Bugs Fixed
-------------------------------------------------------------

-   `metadata()` calls inside metadata filters broke future filters
    (*reported by Iwe Muiser*)
-   Input element text data could be lost if the HTML editor was on and a new element was added
    (*[\#509](https://github.com/omeka/Omeka/issues/509), reported by Lincoln Mullen*)
-   CSS issue with the Themes section of the admin theme in Chrome 26+
-   An Exception problem with the Navigation component
-   Timestamps in the database only used the hours of 0-12, not 13-23. (*reported by daniel.lind*)
-   Error pages didn't escape HTML content in the backtrace or message
    (*[\#512](https://github.com/omeka/Omeka/issues/512))*
-   Deleted collections left behind linkages to Items
    (*[\#507](https://github.com/omeka/Omeka/issues/507), reported by  Lincoln Mullen*)
-   Searching for Items in nonexistent collections/types/etc. caused an error (*[\#527](https://github.com/omeka/Omeka/issues/527)*)
-   Tag hooks weren't being correctly thrown when saving Items
    (*[\#522](https://github.com/omeka/Omeka/issues/522)*)

Performance Improvements-----------------------------------------------------------------

-   A new, faster query is used for the Item-specific simple search
    (*[\#518](https://github.com/omeka/Omeka/issues/518))*

Localization
-----------------------------------------------------------------

-   A translation fix to the "Save Changes" button for plugin config
-   Updated translations for Catalan (Spain) (ca\_ES), Spanish (es), Croatian (hr), Italian (it), Japanese (ja), Flemish (nl\_BE),
    Brazilian Portuguese (pt\_BR), European Portuguese (pt\_PT).
-   New translation for Ukranian (uk).

Theme and Style Improvements
---------------------------------------------------------------------

-   Updated versions of Thanks Roy, Seasons, and Berlin.
-   Added new "Night" style to Seasons.
-   Public-side pagination made consistent with admin-side