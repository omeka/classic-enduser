---
title: Creating an Exhibit Theme
---
*This documentation is for Omeka Classic versions 1.0-1.5*

In Exhibit Builder 1.0 or newer, exhibit themes are now part of public themes. See [Changing Exhibit Themes to Public Themes](Changing_Exhibit_Themes_to_Public_Themes_v1.md) for an explanation of this new structure and instructions for converting
old exhibit themes.

In older versions of Exhibit Builder, the ExhibitBuilder/views/shared folder includes the subfolders for designing themes. Each theme folder includes:

-   **header.php** - is for header information, including the DOCTYPE, title, meta tags, stylesheets, and anything before the actually `page_layout` for an exhibit begins.
-   **footer.php** - is for code after the page layout.
-   **item.php** - allows exhibit theme creators to style the individual item show page to fit their exhibit, instead of sending exhibit visitors to the item show page of their public theme. The code for pulling in item metadata is similar to that used in the public theme.
-   **summary.php** - The home page for your exhibit. By default will include your exhibit's title, description, and a list of sections.
-   **show.php** - the template to show individual pages in a exhibit.
-   **screen.css** - is the default file name for the screen stylesheet. You call the stylesheet in your header with the function `exhibit_css` ('screen').

Consult the ExhibitBuilder Theme API documentation for details on functions used in Exhibit Builder.