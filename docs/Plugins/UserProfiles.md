# User Profiles

The [User Profiles plugin](https://omeka.org/classic/plugins/UserProfiles/){target=_blank} is designed to address many different situations in which gathering and/or displaying information about users is helpful on an Omeka Classic site. In many cases, these situations involve a combination of User Profiles with other plugins. Example use cases might be:

-   Create structured, consistent information about the creators of the site.
-   Give credit to researchers by having them create profiles that are automatically linked to from the items they add.
-   If commenting is used for discussion, create profiles for the moderators.
-   If the [Guest User](GuestUser.md) plugin is installed and active, guest users who comment could also create profiles.

[There is a screencast for this plugin](https://vimeo.com/165052886){target=_blank} that may be helpful:

<div style="padding:62.5% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/165052886?h=c2587c5d3a" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/165052886">Omeka Classic: User Profiles Plugin</a> from <a href="https://vimeo.com/omeka">Omeka</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

## Configuration

User Profiles depends on functionality provided by the [Record Relations plugin](RecordRelations.md). You will need to install Record Relations before installing User Profiles.

After you [install](../Admin/Adding_and_Managing_Plugins.md) the plugin, you will need to configure it. You can access this with the "Configure" button next to the plugin name on the Plugins tab. 

Initially, you will need to select whether you want Omeka to place a link from items in your archive to the person who added them. 

![Configuration option for User Profiles, immediately after activating plugin](../doc_files/plugin_images/UserProfileConfig1.png)

Then, from the User Profiles link on the left side of the administrative screen, you will find the customization options of the plugin.

## Manage profile types

To create a new category of user, click the "Add a Profile Type" button on the "User Profiles" tab.

![Arrow points to the add new button](../doc_files/plugin_images/userprofiles_browsenone.png)

The profile type form has two required fields: **Label** and **Description**.

If you are only creating one profile, these can be brief. If you plan to create multiple profiles, you should supply clear labels and robust descriptions. 

![Add new profile page, completely blank](../doc_files/plugin_images/userprofiles_newtype.png)

Profiles need at least one element. 

Every element needs an **Element Name** and a **Description**. 

The options for Elements are:

- Text boxes
- Radio buttons
- Check boxes
- Select (single option)
- Select (multiple options).

For all elements except the Text box, enter options in a comma-separated list ("apples, oranges, pears" for example).

![Sample elements](../doc_files/plugin_images/userprofiles_elements.png)

You can set whether a profile type is public and/or required with the checkboxes found under the "Add Profile Type" button. 

If the profile is not made public, it will only be visible to users with the role Super, Admin, or Researcher. This allows you to confidentially gather information for research. For public profiles, users may also set their own profiles to be private.

If the profile is required, users will be notified that they need to fill out their profile when they log in.

You may edit a profile at any time by going to the "User Profiles" tab and clicking the "Edit" button under the profile type's label in the table.

![Arrow points to the edit button](../doc_files/plugin_images/userprofiles_edit.png)

To delete a profile, click the "Delete" link under the profile type's name in the table of profile types. 

## Add information

To enter information for yourself in a user profile, go to the User Profiles tab on the left-hand navigation of the administrative dashboard. Click the "Add" link for the profile you want to complete. 

![Arrow points to the My Profile section](../doc_files/plugin_images/userprofiles_complete.png)

## Public user profiles

Non-admin-side Omeka users (i.e., Guest Users) who have profiles may view or edit their profiles by signing in. After sign-in, click the "My Profiles" link.