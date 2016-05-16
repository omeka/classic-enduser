Plugins/Commenting
==================

[Plugins](../Plugins.1.html "Plugins")

About
---------------------------------------------------

Commenting provides a beefier implementation of comments than the
earlier Comment plugin. It allows for comments on any record type (in
theory, at least), and includes both ReCaptchas and Akismet spam
detection.

Commenting also allows for moderation and commenting permissions based
on role. Logged-in users are not required to submit recaptchas.

Requirements
-----------------------------------------------------------------

Omeka 1.5 or higher.

The commenting plugin makes use of both ReCaptchas and the Akismet
spam-detection service. To prevent spam comments, you will want to get
API keys to both of these services and add them to the plugin's
configuration.

Configuration
-------------------------------------------------------------------

After installing the plugin, you will have options to configure various
settings related to display and permissions for commenting on the public
side of your website.

-   Threaded Comments
    -   Check to display threaded comments


-   ReCaptcha Keys
    -   The ReCaptcha keys duplicate the fields found in the Omeka
        Security settings, so if you have already entered a key in those
        settings, you do not need to re-enter. Go to
        [ReCaptcha](http://ReCaptcha.net) to get a key.


-   Permissions
    -   Options are available to specify what roles can moderate, add,
        and view comments
    -   Allowing Public commenting will override the permissions set for
        adding and viewing comments -- they will be open to all


-   Akismet API key
    -   If you allowing public commenting, you will need to obtain an
        [Akismet API key](http://akismet.com/) for spam management. You
        may use a key you are currently implementing on a blog or
        another site that collects public feedback.

See USE CASES below for examples of configuration combinations.

Moderating Comments
-------------------------------------------------------------------------------

Once the plugin is installed, a Comments tab will appear in the public
admin interface. To moderate comments, go to the Comments tab.

All comments collected will be listed on a browse page, and you may
filter them by Approved and Needs Approval for ease of vetting.

You may also batch approve or Unapprove submissions by checking the
Select All box.

Displaying Comments
-------------------------------------------------------------------------------

Commenting will automatically add comment fields to Item and Collection
show pages.

To enable commenting on other record types from modules (e.g.
SimplePages or ExhibitBuilder), you will have to add the following lines
to the appropriate place in the plugin's public view script:


``` {.de1}
<?php commenting_echo_comments(); ?>
<?php commenting_echo_comment_form(); ?>
```


For example, to show comments on exhibit sections and pages, the file
/plugins/ExhibitBuilder/views/public/exhibits/show.php could look like:



``` {.de1}
<?php head(array('title' => html_escape(exhibit('title') . ' : '. exhibit_page('title')), 'bodyid'=>'exhibit','bodyclass'=>'show')); ?>
<div id="primary">
    <h1><?php echo link_to_exhibit(); ?></h1>
 
    <div id="nav-container">
        <?php echo exhibit_builder_section_nav();?>
        <?php echo exhibit_builder_page_nav();?>
    </div>
 
    <h2><?php echo exhibit_page('title'); ?></h2>
 
    <?php exhibit_builder_render_exhibit_page(); ?>
 
    <div id="exhibit-page-navigation">
        <?php echo exhibit_builder_link_to_previous_exhibit_page(); ?>
        <?php echo exhibit_builder_link_to_next_exhibit_page(); ?>
    </div>
    <?php commenting_echo_comments(); ?>
    <?php commenting_echo_comment_form(); ?>
</div>
<?php foot(); ?>
```


Keep in mind that updating themes or plugins will clobber your addition
of the commenting functions.

The Commenting plugin knows how to work with SimplePages and
ExhibitBuilder. Due to variability in how plugins store their data in
the database, other record types and views supplied by other plugins
might or might not work out of the box. Please ask on the forums or dev
list if you would like Commenting to work with other plugins.



Use Cases
-----------------------------------------------------------

### Limited, moderated commenting

An institution wants only trusted people to leave comments for anyone to
read. It doesn't trust some of them enough to allow comments to be
automatically public.

The semi-trusted people could have the Researcher role in Omeka, with
commenting configured to allow Researchers to comment. The Admin role is
the only role that can moderate comments to approve them, and Public is
allowed to view comments.