---
title: Release Notes for 2.2.1
---

Omeka 2.2.1 is the first maintenance release in the 2.2 series. It was released on July 16, 2014. This is a security fix release, and users of earlier versions are recommended to upgrade.

Bugs Fixed  
-------------------------------------------------------------

-   A cross-site scripting vulnerability on the API keys page
-   A cross-site request forgery vulnerability on some user pages
-   In the API, items belonging to non-public collections output     non-working links to them

Enhancements  
-----------------------------------------------------------------

-   Untitled collections will use "\[Untitled\]" instead of blank string where titles are needed (like Items do)