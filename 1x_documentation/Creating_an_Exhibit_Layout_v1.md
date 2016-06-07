---
title: Creating an Exhibit Layout
---
*This documentation is for Omeka Classic versions 1.0-1.5*

Exhibit layouts determine how the items on an exhibit page are displayed. A new layout can completely change the look and feel of and exhibit. To move beyond the layouts included in Exhibit Builder, you will need to create a new exhibit layout.

Exhibit page layouts require the following files:

-   **form.php** - The admin form that will be displayed when an exhibit page is created with this layout. This allows the admin form to mirror the public layout.
-   **layout.css** - CSS stylesheet for the public layout. This stylesheet will automatically be included in the exhibit page. Exhibit items will have the CSS class "exhibit-item".
-   **layout.php** - The public layout itself. This PHP and HTML code will be included on the page. Only exhibit content needs to be specified here; Exhibit Builder will automatically output the site's header and footer.
-   **layout.gif** - A representative image of the layout. This is used to make it easier to visualize the differences between layouts when using Exhibit Builder's admin interface. For consistency with the included images, the dimensions should be 83 x 103 pixels.

Exhibit Builder's pre-included layouts are located at `ExhibitBuilder/views/shared/exhibit_layouts/`. These provide good examples of the structure and best practices for exhibit layouts.