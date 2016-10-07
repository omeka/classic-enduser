---
title: Preparing your addon for the omeka.org addons lists
---

The summer of 2011 saw the introduction of a self-serve mechanism for having your addon listed on the theme or plugin pages on omeka.org.

The process involves some additional steps and changes to the .ini files to help potential users of your theme or plugin.

First, in your .ini files, the following information must be present, in addition to usual .ini information:

`support_link` 
:   A URL where others can find support or report issues with your addon. This should not be the omeka-dev list. Instead, this should be where you will respond to questions or issues. A github issues page works fine.

`omeka_target_version` 
:   The version of Omeka that the current release was developed against, and/or that you intend the current release to work with. It is possible that this will replace the current `omeka_tested_up_to` field. We're exploring that possibility, and appreciate feedback.

`license` 
:   The software license you are releasing the plugin under. Often, developers choose to release under the GPL. In general, the Omeka community leans strongly toward some open source license.

Files should be compressed as .zip files. Our addons page will keep track of versions based on what is in the .ini file, and will use the name given in the .ini file. The page you create on omeka.org for your addon need not be the same as what you give in the .ini file, but obviously it makes more sense if you do.

When you are ready to share your plugin with the others, we recommend that you start by telling us about it on the [dev list](http://groups.google.com/group/omeka-dev/) with a link to it. That will gives us a chance to get to know you if we don’t already, and get more feedback from the community. Then, you can [sign up for an account on our addons site](../wordpress/wp-login.php%3Faction=register.html) (which runs on WordPress). When your account is approved, you will be able to submit your plugin and make it available on our plugins page. If you are part of an organization that will be contributing, you might
want to create an account for the organization, since users cannot edit other users’ addons.

### Two important gotchas
1.  If you are using a version control system like git or svn, make sure you remove the hidden .git or .svn files and directories before zipping up your addon. (Consider using the [git archive](http://gitready.com/intermediate/2009/01/29/exporting-your-repository.html) or [svn export](http://svnbook.red-bean.com/en/1.5/svn.ref.svn.c.export.html) commands to do this for you.)
2.  Mac systems often create additional directory structures when creating a .zip file of your addon. You will need to make sure your .zip file accurately reflects the directory structure of your addon.