---
title: Release Notes for 1.4.1
---

Omeka 1.4.1 is the first bugfix release for the 1.4 series. This release is mainly focused on polish and improvements to the batch editing feature introduced in Omeka 1.4. It was released on July 14, 2011.

Fixes
----------------------------------------------

### Tickets

-   [\#1106](https://omeka.org/trac/ticket/1106) - Batch editing cannot change public/featured back to false.

### Other Issues

-   An issue with HTTP headers that caused fatal errors on some     FastCGI servers. (Thanks to Erin Bell for the bug report

Changes
-------------------------------------------------------

### Batch Editing

-   The batch edit page no longer loads as a dialog box, but on its     own page.
-   There are now separate checkboxes to allow Item Type and Collection to be removed.
-   Form controls are now disabled when the Delete or Remove checkboxes are selected.
