Building Plugins for Public Release
===================================

Once you've developed an Omeka plugin, we encourage you to share it with the rest of the open source community. By adding your plugin to the [plugin directory](../plugins.html), your work will be recognized with a blog post on the official Omeka blog.

### Steps to Releasing a Plugin on the Plugin Directory

1.  Follow [Plugin Writing Best Practices](Plugin_Writing_Best_Practices.html "Plugin Writing Best Practices") and test your plugin to the best of your ability.
2.  Attach a zip file of the plugin's latest code to the [Omeka Developer Mailing List](http://groups.google.com/group/omeka-dev) and write a message to notify the rest of the developer community to check it out.
3.  Obtain access to the Addons Subversion repository to keep the plugin's code under version control.
4.  Following feedback or thumbs up from the developer community, make necessary changes to the plugin's code (if appropriate).
5.  Create an appropriate tag of a release in the subversion repository (creating a copy of the latest plugin code into a new folder /tags/versionnumber/).
6.  Notify Dave to arrange a blog post for the plugin's release.

### Things to Remember

-   **Choose a Unique Name** All plugins must have a unique folder name. For example, there cannot be two ImageViewer plugins, in part because you cannot have two folders named ImageViewer in the plugins directory. Browse the plugin directory before starting a plugin to double check that one doesn't already exist with the same name.
-   **Documenting Your Plugin** A good plugin is a documented plugin. We encourage you to use the official Omeka Documentation Wiki to document your own plugin, similar to the [Contribution Plugin](http://omeka.org/codex/Plugins/Contribution "Plugins/Contribution"). Remember to add a link to the plugin your plugin.ini file.
-   **Plugin Maintenance** Once a plugin has been released with you as the primary developer, you are responsible for maintaining its code. We suggest that all plugin writers join and stay active on the[Omeka Developer Mailing List](http://groups.google.com/group/omeka-dev), as well as subscribe to the [Omeka Forums](../forums/topic/mysqli-stmt.bind-result.html) to stay on top of questions about your plugin. Significant changes to the plugin API are shared directly on the developer mailing list, so look out for updates.

### Access to Addons Repository 

All plugins in the [plugin directory](../plugins.html) are currently
stored in our [Subversion Repository](https://addons.omeka.org/svn/plugins/). In addition to using subversion (SVN) for version control, plugin writers also have access to [Trac](https://addons.omeka.org/trac/) if they wish to create development milestones and tickets for their plugins.

If you're new to subversion and trac, don't worry -- we'll help lead you through the process and it isn't difficult. Pros and beginners alike should email Dave &lt;dave@omeka.org&gt; and he can set you up with access.