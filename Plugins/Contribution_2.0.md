Plugins/Contribution 2.0
========================


[Plugins](../Plugins.1.html "Plugins")

Summary and What's New
--------------------------------------------------------------

The Contribution plugin provides a way to collect stories, images, and other files from the public and manage those contributions in your Omeka site as items. Contributors may share and upload content anonymously, and their information will only be available site administrators. The form can also automatically add a reCAPTCHA box at the bottom of each form to prevent spam-bots from spamming your website.

All contributions are private by default and require a site
administrator to make them public on the Omeka site.

Contribution 2.0 now offers site administrators the ability to let contributors create guest user accounts to better enable multiple contributions from the same user. Administrators can collect specific information about those users with the User Profiles plugin.

An Omeka site with the Contribution plugin now requires you to upload and install 2 separate plugins, and 2 additional plugins if you want to collect any user information:

-   [Guest User](../../add-ons/plugins/guest-user.1.html)
-   [Contribution](../../index.html%3Fp=1284.html)
-   [Record Relations](../../add-ons/plugins/record-relations.1.html) (optional, only required for collecting user information)
-   [User Profiles](../../add-ons/plugins/user-profiles.1.html) (optional, only required for collecting user information)

Preparing to Update an Omeka 1.x site with Contribution
-------------------------

*Back up your database and be sure to copy the plugin’s files before upgrading.* Be sure to follow upgrading process for all [Omeka sites](http://omeka.org/codex/Upgrading).

This is especially important if you made any changes to the wording of the form itself. These changes will not be saved when you upgrade the plugin.

Please follow the [directions below for upgrading.](http://omeka.org/codex/Plugins/Contribution_2.0#Upgrading_from_1.x_to_2.x) You will need to prepare by uploading each of these plugins in your new
Omeka installation:

-   Guest User
-   Contribution
-   Record Relations
-   User Profiles

Getting Started with a New Omeka Installation
------------------------------------------------------------

-   Upload and [install](../Managing_Plugins_2.0.html#Installing_a_Plugin ) the Guest User plugin first. If you have uploaded the other plugins first, you will see in the plugin directory that you cannot install other Contribution-related plugins until Guest User is installed first.

### Guest User Configuration

1. After installing the plugin, click the Configure button. For more information go to the [Guest User documentation](http://omeka.org/codex/Plugins/GuestUser_2.0).
    1. Let visitors know a bit about how their contributions will be used and why they are so valuable in the 'Registration
    Features' information.
    2. All contributors must register as a guest user in order
    to contribute.
    3. It is easiest to contribute if administrator approval is not required and you allow 20 minute instant access. To prevent spam, using ReCaptcha is recommended.
    4. Additional contribution-specific information for guest users can be created here.
2. If you do not wish for your contributors to create an account or to log in to contribute an item, use the following configurations in the Guest User plugin:
    1. Check the box to "Allow open registration," that gives contributor the ability to register without administrator approval
    2. Additionally, you can allow instant access, that gives contributors the ability to contribute without getting an account. This gives them 20 minutes to submit their contribution, from the time they access the form.

### Configuring the Contribution Form

1. Upload and install the Contribution plugin in the plugin directory.
2. Contribution settings: A new tab will appear in the left side
navigation bar labeled, “Contribution.” Click on Contribution to configure the form and submission settings.
    - Note: a link to the contribution form will automatically be added to the site’s navigation. If you wish you draft the form first, go to the site’s Appearance tab at the top of the Dashboard and click on Navigation. Uncheck the “Contribute an Item” link. At this point you can edit the label, or do that later.
3. *Getting Started* tab offers instructions for setting up for the form and submission settings.
4. *Contribution Settings* 
    1. To include questions on the public form, you must first choose the types of items you wish users to add (document, image, sound, moving images) and then create questions whose answers map to specific metadata fields.
    2. Click on the Contribution Types tab to select the item types you want contributors to select from on the public form. Read more about [Managing Item Types](http://omeka.org/codex/Managing_Item_Types_2.0) in Omeka.
    3. Story and Image types are already selected, and you may add other existing types.
    4. Choose a label for this type. For example, a document type is called a Story.
    5. Decide whether to allow and/or require file uploads when this type is selected on the form.
    6. Be sure to add metadata fields for information you wish to collect for those specific Item Types. If there are custom questions for this form that you wish each person to fill out, regardless of type, you will need to add each element to each item type. Read more about [Managing Item Types](http://omeka.org/codex/Managing_Item_Types_2.0) in Omeka.
    7. Save Changes.
        - At any time you may go back and edit the item types and those configurations.
5. *Submission Settings*: Click on Submission Settings Tab.
    1. Choose a slug to customize the url for the contribution form.
    1. Add confirmation email: An email message will be sent to each contributor from this address confirming that they submitted a contribution to this website. Leave blank if you do not want an email sent.
    1. Add emails to which you want a notification sent when new contributions are received. You can enter multiple email addresses, separated by a comma.
    1. Terms of service: paste in text of language of consent for anyone contributing to the site.
    1. Decide whether to use the ‘Simple’ options. This requires that contributors only provide an email address. Select this option if you have set up the Guest User plugin enabling “instant access.”
    1. Add text for Contribution notification emails.
    1. Specify a collection for all new contributed items to be added--remember collections must be created first.
    1. Select a default contribution type (the type that is visible on the top of the dropdown menu, or choose No default type).
    1. If you’re collecting user data with the User Profiles plugin, you must select which profile to make available for your contribution users. See below for more information about creating a user profile.
    1. Save changes.

6. *Contributions*
    1. Contributions tab is where you can view all submissions through the public contribution form.
    1. From this screen, it is possible to review and make items public or change their status.
    1. All contributions through the form will also be available to browse and search on from the Items tab in your Omeka site.

### Collecting Information from Contributors (optional)

To ask for additional information about your contributors, you will need to install 2 additional plugins. If you were not collecting contributor information, you do not need to install Record Relations or User Profiles to use Contribution.

1. Upload and install the [Record Relations plugin](http://omeka.org/codex/Plugins/RecordRelations_2.0)

2. Upload and install the [User Profiles plugin](http://omeka.org/codex/Plugins/UserProfile_2.0). Once Record Relations is installed, the User Profiles plugin will become available to install. Follow directions for creating [user profiles](http://omeka.org/codex/Plugins/UserProfile_2.0).

Upgrading from 1.x to 2.x 
---------------------------------

*Be sure to make a copy of the plugin’s files and a backup copy of the database before upgrading.*
1. Follow upgrading process for all [Omeka sites](http:/omeka.org/codex/Upgrading).
2. Upload and install the following plugins, following all of the steps above for installing plugins and configuring the form above.
    - [Guest User](../../add-ons/plugins/guest-user.1.html)
    - [Contribution](../../index.html%3Fp=1284.html)
    - [Record Relations](../../add-ons/plugins/record-relations.1.html)
    - [User Profiles](../../add-ons/plugins/user-profiles.1.html)
3. If you have asked Contributor Questions on 1.5 form, go to User Profiles plugin page. Locate the check box asking if you want to import Contributor settings: check the box and save changes.
4. Contributor pages should be linked to a Contributor’s profile, and the questions you asked before should be available in the User Profile.
5. If you have modified the text on the Contribution form itself, those changes will not be transferred. You will need to modify the text on the contribute.php form again in the plugin directory on the server.

Adding Contribution link to Site Navigation
----------------------------------------------------------

- A link to the contribution form is automatically added to the main site navigation.
    - Go to the site’s Appearance tab at the top of the Dashboard and click on Navigation. You may rename the public link to the Contribution form. The default label is “Contribute an Item.”
-   Drag and drop the links if you wish to re-order the navigational
    elements of your site.

Vetting and Managing Contributions ------------------------------------------------------------

All new contributions will be not be made public, and by default will be
marked as “Needs Review.”

1\. To review, go to the **Contributed Items** tab in the left navigation
(once you start collecting, this tab changes name from Contribution to
Contributed Items).

2\. Go to the **Contributions** tab and browse contributions.

3\. You may filter by status to see what Needs Review. Any item you wish
to approve, you must make public and save changes.

-   Users have the option to contribute an item that they do not wish to
    be made public. You will not be able to override this request from
    the user, so you cannot make those items "public."
-   Contributors can also make their contributions anonymously. In that
    case, contributor information is only visible to
    site administrators.