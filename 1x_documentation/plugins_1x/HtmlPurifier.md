---
title: HtmlPurifier
---
This documentation is for an Omeka 1.x [Plugins](../Plugins_1.md)

About Html Purifier
-------------------------------------------------------------------------------

The Html Purifier plugin comes pre-loaded with your Omeka installation.
It protects Omeka from cross-site scripting attacks (XSS) by filtering
HTML/XHTML using the HTML Purifier library. This is a non-required
plugin, but highly suggested whenever allowing data to be sent through
public-facing forms.

1.  Go to the /admin/plugins page and click the Install button.
2.  Once installed, please click Configure to finish setting up
    the plugin.
3.  By default, the plugin only purifies HTML code coming in from the
    public interfaces. If you wish to pull out simple HTML code from
    your administrative forms (such as when adding items or building
    exhibits), check off the first box.
4.  You may also specify which HTML elements to allow in administrative
    and public forms.
5.  Save all configurations by clicking the Save Changes button.