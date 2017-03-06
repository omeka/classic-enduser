Teaching Case Study
===================
Children and Youth in History
-----------------------------------------------------------

[Children and Youth in History](http://chnm.gmu.edu/cyh) is a teaching resource on the global history of childhood. The site uses Omeka (version 1.1) to create an archive of primary and secondary sources. CYH staff created custom [item
types](Managing_Item_Types.md) for 'Website Review', 'Case Study', and 'Teaching Module,' and created stand-alone pages for viewing those item types.

### Theme

CYH developed a custom theme, creating a folder called 'cyh' in the themes directory, then adding custom styles to the style sheet. See the [Getting Started with Themes](Getting_Started_with_Themes.html "Getting Started with Themes") and the [Theme API](Theme_API.html "Theme API") for more advice.

Our seasonal themes—Autumn, Spring, Summer, and Winter—are variations on the design for CYH.

### Plugins

-   [MyOmeka](http://omeka.org/codex/Plugins/MyOmeka "Plugins/MyOmeka")
-   [SimplePages](http://omeka.org/codex/Plugins/SimplePages "Plugins/SimplePages")

### Major Sections of the Site

**Homepage**

The homepage includes a custom background with several images related to the history of childhood. Using CSS, that background is positioned

**Website Reviews**

The Website Reviews page essentially provide a way to sort through items of a specific type—website review, case study, and teaching module. We've added a list of tags (regions) so the user can further narrow the list of items.

The page also includes a featured item, using the
[display\_random\_featured\_item](Theme_API/display_random_featured_item.html "Theme API/display random featured item") theme helper.

**Primary Sources**

Similar to Website Reviews, this page provides a way to sort through items by tag—in this case, regions. clicking on one of the tags takes you to the items/browse template, where items are narrowed by the tag you selected.

The page also includes a featured item, using the
[display\_random\_featured\_item](Theme_API/display_random_featured_item.html "Theme API/display random featured item")
theme helper.

**Case Studies and Teaching Modules**

Because these were so few in number, the project lists each of these items by title. You can use the [get\_items](Theme_API/get_items.html "Theme API/get items") theme helper to get items of a specific type, then display those on a page.
