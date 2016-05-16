Plugins/MyOmeka
===============


[Plugins](../Plugins.1.html "Plugins")

About MyOmeka 
-------------------------------------------------------------------

The **MyOmeka plugin** allows users of an Omeka site to create their own
accounts and save items in the archive by tagging and creating personal
annotations. Those annotations can then easily be shared with others by
creating "posters," which are simple, one-page exhibits incorporating
those items and annotations into a single page.

The plugin is currently being used on several popular CHNM sites,
including the [Bracero History Archive](http://braceroarchive.org), and
[Making the History of 1989](http://chnm.gmu.edu/1989/).

Configuring Plugin
-----------------------------------------------------------------------------

During the installation process
([Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin")),
you'll have the option of customizing the plugin's URL slug, title,
disclaimer, and specify whether or not you're using the TermsOfService
plugin in conjunction with MyOmeka.

-   **Relative Page Path From Project Root:** This is the URL that the
    plugin creates. By default, the plugin creates URLs like
    *mywebsite.com/myomeka/*, however you can customize it by editing
    this field.
-   **MyOmeka Title:** The section's title can be customized for
    particular uses of the plugin, such as My Collection, My Archive, My
    Stuff, et al.
-   **MyOmeka Disclaimer:** The disclaimer text appears below every
    public poster created by MyOmeka users.
-   **Require Terms of Service And Privacy Policy:** By checking this
    box, you'll be required to have activated the [Terms of Service
    plugin](http://omeka.org/codex/Plugins/Terms_of_Service). These
    plugins will require users to check that they've read the TOS and
    privacy policy before registering for your site.


Creating a MyOmeka Account and Accessing Content
-----------------------------------------------------------------------------------------------------------------------------------------

-   Visitors click on the Register for "My Stuff" (or whatever you title
    this section) link in the main navigation. Users with accounts with
    click the Login tab to sign in.
-   To register, visitors fill out a short form and create a username
    and fill out their name and email address. They will receive a
    confirmation email that contains an acitvation link that they must
    follow to activate their new "My Stuff" account.
-   Once logged in, users can annotate and tag any item in your website.
    All items are accessible on the My Dashboard page, accessible by
    clicking "My Stuff" tab on the site's main navigation.
    -   Any content created by individual My Omeka users is viewable
        only to them. None of the tags or annotations are made public
        for other users.

### Editing Text on these pages

-   To edit the Dashboard, Register, Browse pages, find those files in
    this directory: plugins/MyOmeka/views/public/my-omeka/


-   To edit the text for adding tags and notes, find those files in this
    directory: /plugins/MyOmeka/views/shared/common/


-   To edit files related to poster builder, find files in this
    directory: plugins/MyOmeka/views/shared/poster

Sample Help Instructions for Using the My Omeka plugin on your Website 
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

To edit the Help page edit the help.php page found in the plugin's
files: plugins/MyOmeka/views/shared/my-omeka/help.php

**Using My Notebook**

To save a story in My Notebook (please fill in with what you have titled
this section), add tags or write notes in the My Notebook box available
for each item.

*Your Notes*

When logged in, you are able to add notes to any of the items on the
website. These notes will be stored and will appear on the item pages
any time you are logged in. A list of the items you have annotated will
appear on your dashboard. These notes will also be available for use if
you choose to make a poster with your items.

*Your Tags*

When logged in, you are also able to tag items on the website. Tags are
like keywords or labels, allowing you to categorize and group items.
Simply type a tag into the “Add a tag” field in “Your Notes,” and click
add. Add more than one tag by separating each term with a comma. Items
can have multiple tags. A list of all the tags you use will appear on
your dashboard. Clicking on any of these tags will list all of the items
to which you have given this tag. For example, clicking on “island” will
show you a list of all the items you have tagged “island.”

*Your Posters*

Once you are logged into My Notebook, you may create a short one-page
exhibit or poster using any items you have tagged or annotated.

Click the button that says "Create a new poster." Assign a title to your
poster, and fill in the description field with a description of your
project. Click the tab that says "Add an item," and select the items
that you wish to include in your poster.

Be sure to save your poster; you may return to edit your poster at any
time by clicking your username link at the top of the home page to the
right of "My Notebook."


### MyOmeka with other Plugins

Keep in mind that if you are activating other plugins that append the
items/show page for displaying content those elements may crowd the
page's public display.

You may need to adjust the CSS for the MyOmeka plugin, found in this
directory: plugins/MyOmeka/views/shared/css/

Editing Theme for Public Access Omeka versions 1.2 and earlier and plugin version 1.0 and earlier
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Once My Omeka is configured, you will want to make My Omeka available to
your users. To do so, you must edit the public theme.

-   On the server, find the directory for the current design theme. Open
    the directory and then the common folder. Inside open the header.php
    file (*/yourtheme/common/header.php*).
-   Insert the following snippet of code in header.php file just above
    the search div.

        ```<?php echo my_omeka_user_status(); ?>```

    Your can place the snippet of code anywhere in your theme file,
    depending on what modifications you've already made. After adding
    the code, your theme may look like this:

        ``` 
        <?php echo my_omeka_user_status(); ?>
        <div id="search-wrap">
            <h2>Search</h2>
            <?php echo simple_search(); ?>
            <?php echo link_to_advanced_search(); ?>
        </div>
        ```

-   Once saved and uploaded back to the server, users of your website
    will now have a link to create accounts and save their own items to
    My Omeka.
-   In addition to adding a link to MyOmeka on the site that indicates
    whether or not a user is logged in, you may wish to customize the
    CSS of your theme to style the look of the plugin. This varies
    from theme-to-theme.
-   You will also want to confirm that the following snippet of code is
    present on the items/show page so that users can add notes and tags
    as they browse the archive. This line should appear at the end of
    the page somewhere above &lt;?php foot(); ?&gt;

        ```<?php echo plugin_append_to_items_show(); ?>```
