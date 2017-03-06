---
title: Theming Plugin Pages
---

*This documentation for Omeka versions up to 1.5 only*

Plugin pages can often be the most important and prominent parts of an Omeka site. However, most plugins are designed to work well with the default bundled themes. When a theme is heavily customized and is significantly different from the stock themes, pages added by plugins can be inconsistent with the look and feel of the rest of the site.

Starting with version 1.3 of Omeka, a theme can override and replace the views for any plugin. This way, a theme can customize pages that are created by plugins in just the same way themes have always been able to customize the "standard" pages in an Omeka site. Instead of trying CSS workarounds, theme writers can change the HTML directly, without editing the plugin's files.

Overriding a Plugin View
-----------------------------------------------------------------------------------------

A plugin's `views` directory contains the stock view scripts for the plugin's pages. In particular, the `views/public` directory contains scripts used on the public site.

To override a plugin view, all you have to do is place a file in the right place in your theme. To find out what file you need to include in your theme, start by finding the path for the plugin view you want to override. First, since a theme only contains public views, you remove the `views/public` part of the path. Second, you need to change the plugin name to be lowercase-with-hyphens instead of CamelCased.

So, to override SomePlugin's view at

    SomePlugin/views/public/controller/view.php

you place a file in your theme at

    some-plugin/controller/view.php

Example
-------------------------------------------------------

The [Simple Pages](../1x_documentation/Plugins_1x/SimplePages.md) plugin has one public view, at `views/public/page/show.php`. This view is used for displaying all the pages created by the administrator.

Often, users want to move or remove the internal navigation that the Simple Pages plugin outputs on every page. The simplest way to do this is to override the `page/show.php` view.

To do this, a theme writer (using a theme called \`my-theme\`) would start by copying the plugin view from

    plugins/SimplePages/views/public/page/show.php

to

    themes/my-theme/simple-pages/page/show.php

Once the view is copied to the theme, a theme writer can alter the theme's copy of the view, and those changes will be reflected on the public site.

Use Cases
-----------------------------------------------------------

-   Theme writers can customize their themes to work well with some specific set of plugins.
-   Individual site administrators can account for every plugin their site uses in one place, in their public theme.
-   Plugins can take advantage of this feature in other ways (ExhibitBuilder combines exhibit themes with normal public themes using this feature)