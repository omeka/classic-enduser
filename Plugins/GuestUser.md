---
title: GuestUser
---
*Current version: 1.1.1*

The Guest User plugin adds an additional user role to your Omeka site. The Guest role works behind the scenes with other plugins (Commenting, and User Profiles, for example), without giving the guests admin access to your Omeka site.

Install and Configure
-----------------------------------------------------------------
After  [installing](../Managing_Plugins.md#installing-a-plugin) the plugin, you should be automatically redirected to the configuration settings for the plugin. You can access these again at any time by clicking the Configure button for Guest User from the Plugins menu.

You can enter text for the following fields:
-   Registration Features: this text will appear at the top of the registration page. You can use it to explain what users are signing up to do, and what the limitations may be.
-   Short Registration Features: brief text appearing as a dropdown from the user bar.
-   Dashboard Label: By default, this is "My Account" and will appear when the user is logged in.
-   Login Text: What is displayed for the login button, defaults to Login.
-   Register Text: What is displayed for the Register link, defaults to Register.

![Settings described above](../doc_files/plugin_images/GUConfig1.png)

There are also two checkboxes:

-   Allow open registration to allow individuals to register without administrators approving their accounts.
-   Allow instant access enables new users to access their accounts for 20 minutes after registering without administrator approval.

![Checkboxes described above, neither checked](../doc_files/plugin_images/GUConfig2.png)

If you have [ReCaptcha enabled](https://omeka.org/codex/ReCaptcha), you can require a ReCaptcha key for registration.

Using the Plugin
-----------------------------------------------------------------
It is important to note that almost all the functionality of the will be with other plugins; Guest user does not do much on its own. You will have to do additional configuration within other plugins (User Profiles, for instance) to realize the full benefits of the Guest User plugin.