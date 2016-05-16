Plugins/ExhibitBuilder
======================


[Plugins](../Plugins.1.html "Plugins")

Description
---------------------------------------------------------------

The Exhibit Builder plugin allows you to develop online exhibits, or
special web pages, that showcase a combination of digital objects in
your Omeka archive with narrative text. Using pre-built themes and
layouts, as well as our WYSIWYG visual editor, users can build complex
pages without any programming knowledge.

If you are using Omeka.net, see [instructions for using the plugin in
the Help section of
Omeka.net](http://info.omeka.net/build-a-website/manage-themes-and-plugins/exhibit-builder/).

Exhibits all follow the same structure, of sections and pages within
sections. You may create as many sections and pages per exhibit as you
like.

[![Exhibitstructure.jpg](https://omeka.org/c/images/4/42/Exhibit_structure.jpg)](../File:Exhibit_structure.jpg.html)

Configuring Exhibits, (version 1.0 and above)
-----------------------------------------------------------------------------------------------------------------------------------------

Exhibit builder 1.0, used in Omeka version 1.3 and above, may be
configured so that an exhibit/browse page is used for the website's
homepage, and you may choose how to sort exhibits on the exhibit/browse
page.

-   To configure the exhibits, go to the /admin/plugins page, also
    accessible from the site Settings button. Click "configure" button
    next to the Exhibit Builder name in your list of plugins.
-   Check the first box if you wish to make the Exhibit Browse page the
    homepage of your Omeka site.
-   To decide in which order your exhibits will be listed on the Exhibit
    Browse page, choose Date Added (oldest-&gt;newest), Alphabetical, or
    Recent (newest-&gt;oldest).

**If you created a custom exhibit theme for earlier versions of the
exhibit builder, please see:
[Changing\_Exhibit\_Themes\_to\_Public\_Themes](../Changing_Exhibit_Themes_to_Public_Themes.html "Changing Exhibit Themes to Public Themes").**

### Getting Started 

1\. Click on the Exhibits tab in the top nav bar of the Admin interface,
and click the "Add Exhibits" button on the right side. You will arrive
at an Exhibit Metadata page. Fill in the empty fields.

-   **Exhibit Slug (no spaces or special characters):** This is the
    exhibit name as it appears in the website URL, for example,
    <http://example.com/exhibits/show/myexhibitname>
-   **Exhibit Credits:** These will appear with description on the
    public site.
-   **Exhibit Description:** An introduction to the entire exhibit that
    appears on the public site.
-   **Exhibit Tags:** Tags help associate exhibits with other items in
    your archive.
-   **Exhibit is featured:** Will this exhibit be featured on the browse
    exhibit page?
-   **Exhibit is public/not public:** If you are designing the exhibit
    in stages, you probably do not want to make your exhibit public.
    *NB: Remember, if your exhibit is not public and you are logged in
    as a super or admin user, you will see the exhibit appear on your
    site as if it is public. Log out, and then look at your site.*
-   **Exhibit Theme:** By default, “Current Public Theme” is selected.

If you want the exhibit to retain the same design theme as the rest of
your site, do not choose a new theme. If you like the look and feel of
your website’s current public theme, but want to add a logo and
customize the exhibit, choose “default” theme. For a completely new
design, choose a different exhibit theme. You may edit the theme's CSS
to change exhibit design elements. See also [Creating an Exhibit
Theme](../Creating_an_Exhibit_Theme.html "Creating an Exhibit Theme"),
[Creating an ExhibitLayout](../Creating_an_Exhibit_Layout.html "Creating an Exhibit Layout"),
and [Exhibit Builder ThemeAPI](ExhibitBuilder/Theme_API.html "Plugins/ExhibitBuilder/Theme API").

### Sections 

2\. To proceed with your exhibit, you must create sections so click "Add
a Section."

3\. A field for a title will appear. After you title the new section,
click "Add a Section" again and it should appear under the Exhibit
Section heading on that page.

4\. To add text and items to an exhibit section, click the "edit" button
to the right of the section title. From there, add a
description/introduction/summary and create an optional URL slug for
this section. The next step is to add pages to your section.

5\. In Exhibit Builder 1.0 and above, sections may be reordered by
dragging and dropping.

6\. To delete a section, click the Delete Section button.

### Pages 

5\. Click "Add a page" and enter page metadata including a page title,
slug, and a layout for presenting different combinations of
interpretative text and items from the archive. By saving the page
metadata, a blank page has been created and you are redirected to the
page content form.

[![Exhibitpagelayout.png](https://omeka.org/c/images/f/fb/Exhibitpagelayout.png)](../File:Exhibitpagelayout.png.html)

6\. (If working in Exhibit Builder 1.0, see 6a.) At the top of the page
content form, you'll see items from your archive listed. You may browse
or search for specific items you want for the exhibit page. Once you
find an item, drag it onto the page layout box. Smaller square boxes are
for items. To change items, drag another item over the existing one. To
remove an item, click the minus sign.

The text boxes which are in most layouts feature an HTML visual editor
powered by TinyMCE. You can resize and format text that'll be printed on
the final layout. Note that CSS formatting in specific exhibit theme may
control the appearance of this text, so the editor may not always
reflect how the final page looks.

Learn more about
[Using\_HTML\_Editor-TinyMCE](../Using_HTML_Editor-TinyMCE.html "Using HTML Editor-TinyMCE").

*NB: Thumbnail previews are created only for image files in exhibit
pages. If you want to include an item that is a PDF, you also want to
upload a small image file first that can act as an illustration of that
PDF to appear in the items/show and exhibit page.*

6a. In Exhibit Builder 1.0 (with Omeka 1.3), you will find a combination
of text boxes and places to attach items within the exhibit layout.

To add an item to the page layout, click "Attach an Item." A lightbox
opens with a list of items from the archive for you to browse or to
search. To select item for the page, click the title and then click the
Attach Selected Item button in the bottom right of the lightbox.

[![Pageattachments.png](https://omeka.org/c/images/f/f1/Pageattachments.png)](../File:Pageattachments.png.html)

Once attached, a Caption box appears for you to fill in as desired with
an HTML WYSIWYG visual editor. Captions are associated with that item
only.

Text boxes also feature the HTML WYSIWYG visual editor. You can resize
and format text that'll be printed on the final layout. Note that CSS
formatting in specific exhibit theme may control the appearance of this
text, so the WYSIWYG editor may not always reflect how the final page
looks.

7\. Before navigating away from this screen, be sure to save your work by
clicking one of the two save options at the bottom of the screen. You do
not need to complete the page, but please remember to save.

8\. "Save and Add another Page" returns you to page layouts and allows
you to choose one for the next exhibit page. "Save and Return to
Section" takes you back to the exhibit section where you will find the
pages you added.

9\. Once you are finished adding pages to a section, be sure to hit "Save
and Return to Exhibit." From here you may create new sections or "Save
and Finish."

10\. If you wish to reorder pages, you may do so by editing the Section,
and then dragging and re-ordering pages.

### Editing Exhibits

10\. Once an exhibit, section, or page is created, it may be edited at
any time. To edit pages, first click edit next to the appropriate
exhibit, then edit the proper section to get to the pages from that
section.

When the exhibit is ready for your online visitors, don't forget to make
it public.

