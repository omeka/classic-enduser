
Managing Themes
===============
*This documentation is for Omeka Classic versions 1.0-1.5*

Themes allow you to customize the look and feel of your public Omeka site.

They are a collection of template files and helper function that use data in your Omeka archive and display those data to end users. Themes include files for images (.gif, .jpg, .png), style sheets (.css) and various code files (.php).

From the admin side you can control some of that display through configurations.

Installing a Theme
------------------------------------------------------
To install and activate a new theme, do the following:

1.  Download and unzip the theme.
2.  Use an FTP client to upload the theme folder you've unzipped into a directory named "themes" in your Omeka install. You'll already see folders for the pre-packaged themes in this directory.
3.  Log in to the admin panel, navigate to Settings &gt; Themes, select the radio input beside the theme you wish to use, and click the "Switch Theme" button.


Configurable Themes in Omeka 1.2 and Above
----------------------------------------------------------------

In versions 1.2 and 1.2.1, some themes are configurable in Settings &gt; Themes admin screen. This functionality allowing users to change the color palette and/or add a logo without needing to edit files on the server.

### Rhythm

-   After choosing Rhythm, click Configure.
-   Choose from 3 style sheets that change the color palette of     this theme.
-   Save Changes.

### Seasons

-   After choosing Seasons, click Configure.
-   Choose from 4 style sheet that change the color palette of     this theme.
-   If desired, upload a logo file. Logo will appear in left corner of the site's header.
-   Save Changes.

Configurable Themes, 1.3 and Above
----------------------------------------------------------------
In versions 1.3 and above, all themes are configurable in Settings &gt; Themes admin screen.

Configurations are unique for each theme and will be saved with the theme. You must configure each theme when changing designs. But if you return to the original theme, all of your initial configurations will be saved.

After clicking "configure" (next to the name of your current theme), make choices about the look of your site, navigation, featured elements, homepage text, and metadata displayed.

-   Choose a logo file. You may upload a logo file that will replace the site title in the header of the theme. Recommended maximum width for the logo is 500px.
-   Custom Header Navigation: If you want to override the default     navigation in the theme header, enter a custom list in this     text box. Enter your desired navigation in the following way: ‘Name of Link Text | path/to/page’. Each link should be on its own line. If this field is blank, the navigation will be     generated automatically.
    -   For example if you want the link to the Browse Items page to be called Archive and the Browse Collections page to become Collections, enter this in the text box:
        -   Archive | /items
        -   Collections | /collections
    -   If you wish to sort items alphabetically or by a different Dublin Core field,(change 'Title' to whatever you'd like to sort by a different field), enter this in the text box:
        -   Browse Items | items?sort\_field=Dublin Core,Title
-   Display Featured Item: Check this box if you wish to show a featured item on the homepage.
-   Display Featured Collection: Check this box if you wish to show a link featuring a collection on the homepage.
-   Display Featured Exhibit: Check this box if you wish to show a link featuring an exhibit on the homepage.
-   Homepage Recent Items: Choose the number of recent items to be displayed on the homepage. These appear in the order in which they were mostly recently added to the archive.
-   Homepage Text: Add some text to be displayed on your homepage above the Featured Items. This is a good place to add a very short tagline or description of your site. Save longer explanations for an About page.
-   Display Dublin Core Fields: Choose from the Dublin Core metadata fields that you would like to display and in the order you would like to display them on the items/show page. For example, to display only the descriptions, subjects, and creators for every item in your archive, enter: ‘Description, Subject, Creator’. Be sure to spell each field correctly and to separate each field term with a comma. If you misspell or do not use commas, all of the fields will display. Also, if this text box is left blank, all available fields with data will be displayed.
-   Footer Text: Add some text to be displayed in your theme’s footer.This can be a good place to add credits or links to funders.
-   Display Copyright in Footer: Check this box if you wish to display your site’s copyright information in the footer. Site copyright information is found in the General Settings section.

Save Changes at the bottom of of the screen to save all of your
customizations.

Creating Themes
----------------------------------------------------------------

One of the easiest ways to develop your own theme is to modify one of the pre-existing ones in our themes directory. Hacking on a CSS file, you can create a dramatically different website with minimal work.

If you're interested in creating new themes, check out the [Theme Writing Best Practices](../1x_documentation/Theme_Writing_Best_Practices.md) to get started, and use the [Theme API](../1x_documentation/Theme_API.md) page as a reference.

