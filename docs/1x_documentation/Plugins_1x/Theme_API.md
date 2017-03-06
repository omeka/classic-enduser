---
title: ExhibitBuilder 1 Theme API
---

*This documentation is for Exhibit Builder 1, for versions of Omeka Classic 1.3-1.5 ONLY*


The following functions are part of the [Exhibit Builder
plugin](../ExhibitBuilder.1.html "Plugins/ExhibitBuilder") that can be
used to create [exhibit
themes](../../Creating_an_Exhibit_Theme.html "Creating an Exhibit Theme")
and [exhibit page
layouts](../../Creating_an_Exhibit_Layout.html "Creating an Exhibit Layout").

-   [exhibit\_builder\_section\_has\_pages](https://omeka.org/codex/Exhibit_builder_section_has_pages "Exhibit builder section has pages")
-   [exhibit\_builder\_link\_to\_exhibit](https://omeka.org/c/index.php?title=Exhibit_builder_link_to_exhibit&action=edit&redlink=1 "Exhibit builder link to exhibit (page does not exist)")
-   [exhibit\_builder\_exhibit\_uri](https://omeka.org/codex/Exhibit_builder_exhibit_uri "Exhibit builder exhibit uri")
-   [exhibit\_builder\_link\_to\_exhibit\_item](https://omeka.org/c/index.php?title=Exhibit_builder_link_to_exhibit_item&action=edit&redlink=1 "Exhibit builder link to exhibit item (page does not exist)")
-   [exhibit\_builder\_exhibit\_item\_uri](https://omeka.org/c/index.php?title=Exhibit_builder_exhibit_item_uri&action=edit&redlink=1 "Exhibit builder exhibit item uri (page does not exist)")
-   [exhibit\_builder\_get\_exhibits](https://omeka.org/codex/Exhibit_builder_get_exhibits "Exhibit builder get exhibits")
-   [exhibit\_builder\_recent\_exhibits](https://omeka.org/codex/Exhibit_builder_recent_exhibits "Exhibit builder recent exhibits")
-   [exhibit\_builder\_get\_exhibit\_by\_id](https://omeka.org/codex/Exhibit_builder_get_exhibit_by_id "Exhibit builder get exhibit by id")
-   [exhibit\_builder\_get\_exhibit\_section\_by\_id](https://omeka.org/codex/Exhibit_builder_get_exhibit_section_by_id "Exhibit builder get exhibit section by id")
-   [exhibit\_builder\_exhibit\_head](https://omeka.org/codex/Exhibit_builder_exhibit_head "Exhibit builder exhibit head")
-   [exhibit\_builder\_exhibit\_foot](https://omeka.org/codex/Exhibit_builder_exhibit_foot "Exhibit builder exhibit foot")
-   [exhibit\_builder\_page\_text](https://omeka.org/c/index.php?title=Exhibit_builder_page_text&action=edit&redlink=1 "Exhibit builder page text (page does not exist)")
-   [exhibit\_builder\_page\_item](https://omeka.org/c/index.php?title=Exhibit_builder_page_item&action=edit&redlink=1 "Exhibit builder page item (page does not exist)")
-   [exhibit\_builder\_exhibit\_form\_item](https://omeka.org/c/index.php?title=Exhibit_builder_exhibit_form_item&action=edit&redlink=1 "Exhibit builder exhibit form item (page does not exist)")
-   [exhibit\_builder\_layout\_form\_item](https://omeka.org/c/index.php?title=Exhibit_builder_layout_form_item&action=edit&redlink=1 "Exhibit builder layout form item (page does not exist)")
-   [exhibit\_builder\_layout\_form\_text](https://omeka.org/c/index.php?title=Exhibit_builder_layout_form_text&action=edit&redlink=1 "Exhibit builder layout form text (page does not exist)")
-   [exhibit\_builder\_exhibit\_layout](https://omeka.org/c/index.php?title=Exhibit_builder_exhibit_layout&action=edit&redlink=1 "Exhibit builder exhibit layout (page does not exist)")
-   [exhibit\_builder\_exhibit\_css](https://omeka.org/c/index.php?title=Exhibit_builder_exhibit_css&action=edit&redlink=1 "Exhibit builder exhibit css (page does not exist)")
-   [exhibit\_builder\_layout\_css](https://omeka.org/c/index.php?title=Exhibit_builder_layout_css&action=edit&redlink=1 "Exhibit builder layout css (page does not exist)")
-   [exhibit\_builder\_section\_nav](https://omeka.org/c/index.php?title=Exhibit_builder_section_nav&action=edit&redlink=1 "Exhibit builder section nav (page does not exist)")
-   [exhibit\_builder\_page\_nav](https://omeka.org/codex/Exhibit_builder_page_nav "Exhibit builder page nav")
-   [exhibit\_builder\_nested\_nav](https://omeka.org/c/index.php?title=Exhibit_builder_nested_nav&action=edit&redlink=1 "Exhibit builder nested nav (page does not exist)")
-   [exhibit\_builder\_render\_exhibit\_page](https://omeka.org/c/index.php?title=Exhibit_builder_render_exhibit_page&action=edit&redlink=1 "Exhibit builder render exhibit page (page does not exist)")
-   [exhibit\_builder\_render\_layout\_form](https://omeka.org/c/index.php?title=Exhibit_builder_render_layout_form&action=edit&redlink=1 "Exhibit builder render layout form (page does not exist)")
-   [exhibit\_builder\_display\_exhibit\_thumbnail\_gallery](https://omeka.org/c/index.php?title=Exhibit_builder_display_exhibit_thumbnail_gallery&action=edit&redlink=1 "Exhibit builder display exhibit thumbnail gallery (page does not exist)")
-   [exhibit\_builder\_display\_random\_featured\_exhibit](https://omeka.org/c/index.php?title=Exhibit_builder_display_random_featured_exhibit&action=edit&redlink=1 "Exhibit builder display random featured exhibit (page does not exist)")
-   [exhibit\_builder\_random\_featured\_exhibit](https://omeka.org/c/index.php?title=Exhibit_builder_random_featured_exhibit&action=edit&redlink=1 "Exhibit builder random featured exhibit (page does not exist)")
-   [exhibit\_builder\_link\_to\_next\_exhibit\_page](https://omeka.org/c/index.php?title=Exhibit_builder_link_to_next_exhibit_page&action=edit&redlink=1 "Exhibit builder link to next exhibit page (page does not exist)")
-   [exhibit\_builder\_link\_to\_previous\_exhibit\_page](https://omeka.org/c/index.php?title=Exhibit_builder_link_to_previous_exhibit_page&action=edit&redlink=1 "Exhibit builder link to previous exhibit page (page does not exist)")
-   [exhibit\_builder\_exhibit\_display\_item](https://omeka.org/c/index.php?title=Exhibit_builder_exhibit_display_item&action=edit&redlink=1 "Exhibit builder exhibit display item (page does not exist)")
-   [exhibit\_builder\_exhibit\_page\_has\_item](https://omeka.org/c/index.php?title=Exhibit_builder_exhibit_page_has_item&action=edit&redlink=1 "Exhibit builder exhibit page has item (page does not exist)")
-   [exhibit\_builder\_use\_exhibit\_page\_item](https://omeka.org/c/index.php?title=Exhibit_builder_use_exhibit_page_item&action=edit&redlink=1 "Exhibit builder use exhibit page item (page does not exist)")
-   [exhibit\_builder\_exhibit\_thumbnail](https://omeka.org/c/index.php?title=Exhibit_builder_exhibit_thumbnail&action=edit&redlink=1 "Exhibit builder exhibit thumbnail (page does not exist)")
-   [exhibit\_builder\_exhibit\_fullsize](https://omeka.org/c/index.php?title=Exhibit_builder_exhibit_fullsize&action=edit&redlink=1 "Exhibit builder exhibit fullsize (page does not exist)")