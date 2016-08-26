---
title  : SimplePages 2.0
---
The Simple Pages plugin allows you to create text rich pages, for example an "About" page. It is one of the plugins which comes bundled with downloads of Omeka.

Simple Pages can be written in plain text or using HTML. You can insert items, exhibits, and files into Simple Pages by using the[Shortcodes](../Shortcodes.md) available on Omeka. 

Configuration
-------------------------
Once activated, Simple Pages has a single configuration setting. To manage this setting, go to the Plugins tab, located in the top navigation in the admin dashboard. Scroll down to Simple Pages and click the blue *Configure* button. 

The setting for Simple Pages is a checkbox to *Filter User Input for Page Content.* If checked, the plugin will filter any user-entered text in a Simple Page against the HTML filters in the [security settings](../Managing_Security_Settings_2.md), removing any disallowed HTML tags. 

![Simple Pages configuration setting](../doc_files/plugin_images/simplePgsConfig.png)

Create a Page 
------------------------------------------------------




[![Simple
Pages.png](https://omeka.org/c/images/a/ac/Simple_Pages.png)](https://omeka.org/codex/File:Simple_Pages.png)

-   Find the Simple Pages tab in the left side menu under "Dashboard."
-   To start building a webpage, click Add a Page.
-   Titling the page is required, and add a unique URL slug for the page if you wish. For example, “about” is the slug in the following URL: www.myomekasite.com/about
-   Add any text you want to appear on the page in the designated text box below. If you want to format the text, you may use simple HTML markup.
    -   By checking the "Use HTML editor" button, you can add simple
        mark up to your text, including links, and you can embed
        multimedia web objects.
            -   If you wish to include PHP in your Simple Pages, do not use the
        HTML editor for this page.
-   To create a hierarchy of pages, or nested page, you may choose which page acts as the “Parent.” If you choose not to nest pages and want them linked on the homepage, choose Main Page (No Parent) option.
-   You may also choose to link to this page to the primary, or main site, navigation that appears on every page in the website.
-   To order the pages on the website's navigation, see [Managing\_Navigation\_2.0](../Managing_Navigation_2.0.html "Managing Navigation 2.0").
-   Click the green "Save Changes" button to save your page. Once you are ready to publish the page, click the Public box found under the Save Changes button.

[![Simple.png](https://omeka.org/c/images/thumb/2/2e/Simple.png/500px-Simple.png)](https://omeka.org/codex/File:Simple.png)


Viewing Pages
------------------------------------------------------

To view the public page, you may click "View Public Page" the Edit page
or by clicking the page's title from Simple Pages Browse page. To see
relationships of the pages, click on Hierarchy View available on the
Simple Pages Browse.

Advanced Users
-------------------------------------------------------
For advanced users, Simple Pages can accept nested slugs and PHP code.