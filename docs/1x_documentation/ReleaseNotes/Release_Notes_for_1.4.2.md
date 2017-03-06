---
title: Release Notes for 1.4.2
---

Omeka 1.4.2 is the second maintenance release for the 1.4 series.

It was released on October 26, 2011.

Fixes
---------------------------------------------------

### Files
-   Deleting an item with missing or corrupt files causes an error ([\#83](https://github.com/omeka/Omeka/issues/83)).
-   Some failed uploads leave behind empty File records ([\#88](https://github.com/omeka/Omeka/issues/88)).
-   Thumbnails can't be created for images with multiple pages or frames ([\#98](https://github.com/omeka/Omeka/issues/98)).
-   Bad formatting on invalid file messages from plugins ([\#106](https://github.com/omeka/Omeka/issues/106)).
-   Files added by some plugins can ignore the validators ([\#111](https://github.com/omeka/Omeka/issues/111)).
-   Files uploaded by URL fail the extension check if they have a query string ([\#120](https://github.com/omeka/Omeka/issues/120)).
-   Some Amazon S3 files can't be uploaded ([\#121](https://github.com/omeka/Omeka/issues/121)).

### Helpers

-   The `link_to` helpers keep the current page's parameters. ([\#96](https://github.com/omeka/Omeka/issues/96)).

### Installer

-   The installer doesn't work when using a non-standard port ([\#78](https://github.com/omeka/Omeka/issues/78)).
