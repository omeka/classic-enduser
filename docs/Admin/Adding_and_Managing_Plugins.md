# Working with Plugins

Plugins are tools to extend the basic functionality of Omeka Classic. A list of plugins available for download is on the [Plugins Directory](http://omeka.org/classic/plugins){target=_blank}. Instructions are available on each plugin's documentation page.

!!! Note
    Not every plugin will work with every version of Omeka, especially newer plugins on old installations. Older versions of plugins may be available on their Github pages. Use the Plugins Directory to find the "Github" link on the right side of the screen for each plugin, then look on the right hand side of the Github page for the "Releases" section. 

![A screenshot of the Plugins page, with one not yet installed, one installed but not activated, and one active plugin](../doc_files/Plugins.png "A screenshot of the Plugins page, with one not yet installed, one installed but not activated, and one active plugin")

Manage plugins from the Plugins page found at the top of your Dashboard. Plugins will be listed alphabetically. Each plugin listed will have links to perform various actions:

-   **Install**: Runs the installer and activates the plugin.
-   **Configure**: Takes you to a page for customizing the plugin's unique settings. 
-   **Deactivate**: Deactivating merely "unplugs" the plugin, but does not delete any data collected while the plugin was active. 
-   **Activate**: Activates the plugin after it has been manually deactivated. All plugins are automatically activated once installed.
-   **Uninstall**: Runs the uninstaller for the plugin and deletes nformation in your installation related to the plugin, including data in metadata fields.

In some cases, uninstalling plugins can delete data associated with the plugin from your database, such as information entered into metadata fields on items or collections. Check the plugin's documentation. We recommend deactivating and testing the changes first, before uninstalling. 

Install a plugin
-------------------
Watch [our screencast showing these steps](https://vimeo.com/153819886){target=_blank}. To add and activate a new plugin for your Omeka installation, follow these steps: 

1.  [Download and unzip the compressed plugin file](https://omeka.org/classic/plugins/){target=_blank} on your computer.
1.  Open your FTP client and use your FTP login info to access your site. Or, if you are using cPanel File Manager, WebFTP, or another in-browser tool, log in there.
1.  Navigate to your Omeka folder (it should have the same name as your Omeka install), open it, then open the `/plugins` folder.
1.  Locate the plugin folder on your computer and upload it into your Omeka website's `/plugins` folder. 
    - Sometimes the plugin unzips into a folder of the same name, so make sure to go inside it and upload the folder that only contains the plugin name, not the version number. For example, you may have downloaded the `CSSEditor-1.1.zip` file and extracted it to a `CSSEditor-1.1` folder, which contains a `CSSEditor` folder. Upload the `CSSEditor` folder. 
    -- You may also be able, or required, to upload the zipped file and unzip it here, if your file client does not allow you to upload a folder. Remember to watch for an extra folder level in this case.
1.  In another browser window, log in to your Omeka admin panel (`https://youromekasite.org/admin`).
1.  Navigate to the Plugins tab in the upper navigation of the admin dashboard, and scroll down to find the plugin you uploaded. Plugins are listed alphabetically.
    - If the plugin is not visible, double-check that the folder is in the right location ('/plugins') and that the folder name is correct, including ensuring that the folder does not start with 'plugin-'.
1.  Click “Install” to the right of the plugin name to finish the process.
    - Click “Configure” if available/needed.
1. Read the documentation for the plugin to understand what configuration options are available.

If you are using a hosting provider that offers cPanel and online file management options, [Reclaim Hosting](../GettingStarted/Hosting_Suggestions.md) has [step-by-step instructions](http://docs.reclaimhosting.com/omeka/uploading-plugins-to-omeka){target=_blank} for uploading plugins with cPanel's browser-based FTP option.

!!! Note
    You can also use `git clone` or the Github interface to download the latest plugin code directly from Github into a folder in your `/plugins` folder. Be sure to watch for extra folder levels or incorrect folder names in this case, such as a folder starting with `plugin-` or ending with `-master`. Rename the folder to remove things like `plugin-` and/or `-master` from the folder name, as in `git clone https://github.com/omeka/plugin-Timeline.git Timeline`. 

Upgrade plugins
-----------------
When an active plugin is out of date, a notification will appear at the bottom of the plugin's entry on your Plugins page. The notification reads "A new version of this plugin is available. Get the new version." with a link. 

Clicking the phrase "Get the new version" will take you to a page where you can download the latest version of the plugin. 

![Entry for a plugin, displaying the out-of-date notification below the usual information for the plugin](../doc_files/plugin_updatenotice.png "Entry for a plugin, displaying the out-of-date notification below the usual information for the plugin")

You will upgrade by replacing the old plugin folder with the new one: 

1. Go to the admin dashboard of your Omeka site and navigate to the Plugins tab on the top navigation menu.
1. Click the "Deactivate" button to deactivate the plugin you would like to upgrade. **Warning**: Do not click the uninstall button, or you may delete data associated with the plugin.
1. Download the new version of the plugin, and unzip it on you computer. 
1. Open your FTP client and use your FTP login info to access your site, or use cPanel's file manager, or your WebFTP interface, etc.
1. Navigate to your Omeka folder online, then open the `/plugins` folder.
1. Delete the old plugin folder from your `/plugins` folder, or move it temporarily out of that location.
1. Upload the new version of the plugin to the `/plugins` folder. Be careful, as above, to ensure the folder name is correct. 
1. Go to the admin dashboard of your Omeka site and navigate to the Plugins tab on the top navigation menu.
1. Find your plugin in the list. You should be directed to upgrade the plugin - click the "Upgrade" button to complete the process.

If you have installed the plugin with `git clone` you may update the plugin using `git pull`. 

Plugin dependencies
----------------
Some plugins are designed to provide infrastructural functions for other plugins. Such plugins are required to be installed and active for other plugins that depend on them to work. If you upload a plugin to your site but cannot activate it due to a message like this, simply install the required plugin following the usual steps above.

![Example of a plugin which requires another plugin to be installed before it can be activated](../doc_files/pluginRequired.png "Example of a plugin which requires another plugin to be installed before it can be activated") 

Pre-packaged plugins
--------------------
The following plugins come pre-packaged with the download of Omeka Classic: 

-   [Coins](../Plugins/Coins.md) – Adds COinS metadata to items on the admin theme and in public themes.
-   [Simple Pages](../Plugins/SimplePages.md) – Publish static pages on your public site.
-   [Exhibit Builder](../Plugins/ExhibitBuilder.md) – Build narratives around your collections.
