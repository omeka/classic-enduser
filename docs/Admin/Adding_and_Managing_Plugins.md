# Working with Plugins

Plugins are tools to extend the basic functionality of Omeka Classic. A list of plugins available for download is on the [Plugins Add-Ons Directory](http://omeka.org/classic/plugins) (Please note that not every plugin will work with every version of Omeka), and instructions are available on each plugin's documentation page.

![Plugins page](../doc_files/Plugins.png)  

Manage plugins from the Plugins page found at the top of your Dashboard. Plugins will be listed alphabetically.  Each plugin listed will have links to perform various actions:

-   **Install**: Runs the installer for the plugin and activates the plugin.
-   **Uninstall**: Runs the uninstaller for the plugin and deletes any information in your installation related to the plugin.
-   **Activate**: Activates plugin after it has been manually deactivated. All plugins will be activated once present in the Omeka /plugins directory on the server. 
-   **Deactivate**: Action merely "unplugs" the plugin but does not delete any data collected while plugin was active. 
-   **Configure**: Takes you to a page for customizing the plugin's unique settings.

In some cases, uninstalling plugins can delete data associated with the plugin from your database. Check the plugin's documentation before uninstalling if you're unsure. 

Installing a Plugin
-------------------
Watch [our screencast showing these steps](https://vimeo.com/153819886). To add and activate a new plugin for your Omeka installation, follow these steps: 

1.  Download and unzip the file on your computer.
2.  Open your FTP client.
3.  Use your FTP login info to access your site.
4.  Navigate to your Omeka folder. It should have the same name as your Omeka install. 
5. Open the Omeka folder
6.  Open the /plugins folder
7.  Upload your new plugin folder into your Omeka website's /plugins folder. 
    - Sometimes the unpacked plugin is inside a folder of the same name so make sure you are uploading the correct directory. 
    - NB: your plugin must be inside the /plugins folder.
    - You can also upload the zipped file and unzip it here, if your FTP client allows
7.  Rename the folder to remove the `plugin-` from the folder name. If you do not do this, the plugin will display as invalid on your Omeka dashboard.
7.  In a new browser window, log in to your Omeka admin panel (youromekasite.net/admin)
8.  Navigate to the Plugins tab in the upper navigation of the admin dashboard, and scroll down to find the plugin you uploaded (note: plugins are listed alphabetically)
    - If the plugin is not visible, return to step 6 and double-check
9.  Click the ”Install" to the right of the plugin name to finish the process.
    - Click “Configure” if available/needed.
10. Read documentation for plugin to understand configuration

If you are using [Reclaim Hosting](https://reclaimhosting.com/) they have [step-by-step instructions](http://docs.reclaimhosting.com/omeka/uploading-plugins-to-omeka) for uploading plugins with specific instructions for their browser based FTP option

Upgrading Plugins
-----------------
When your plugin is out of date, a notification will appear at the bottom of the plugin's entry on your Plugins page. The notification reads "A new version of this plugin is available. Get the new version." Clicking the phrase "get the new version" will take you to a page where you can download the latest version of the plugin. 

![Entry for the plugin COinS, display the out of date notification below the usual information for the plugin](../doc_files/plugin_updatenotice.png)

In order to upgrade a plugin, you will need to use your FTP client to replace the old plugin folder with the new one. 

The following are detailed instructions for upgrading a plugin. 

1. Go to the Admin dashboard of your Omeka site and navigate to the Plugins tab on the top navigation menu.
1. Click the "Deactivate button" to deactivate the plugin you would like to upgrade. *Warning:* Do not click the uninstall button, or you may delete any data created with the plugin.
1. Download the new version of the plugin, and unzip it on you computer. 
1. Open your FTP client. 
1. Use your FTP login info to access your site.
1. Navigate to your Omeka folder. It should have the same name as your Omeka install. 
1. Open the Omeka folder
1. Open the /plugins folder 
1. Remove the old plugin folder from your /plugins folder on your serve.
1. Upload the folder with the new version of the plugin to the /plugins folder. 
1. Go to the Admin dashboard of your Omeka site, navigate to the Plugins tab on the top navigation menu.
1. You may be directed to Upgrade your plugin - click the link to upgrade and then re-activate your plugin.

Required Plugins
----------------
Some plugins are designed to provide basic functionality that is useful for many other plugins. Such plugins are required to be installed and active for other plugins that depend on them to work. If you upload a plugin to your site but cannot activate it due to a message like this, simply install the required plugin following the usual steps above.

![Example of a plugin which requires another plugin to be installed before it can be activated](../doc_files/pluginRequired.png) 

Pre-packaged Plugins
--------------------
The following plugins come prepackaged with the download of Omeka Classic: 

-   [Coins](../Plugins/Coins.md) – Adds Coins metadata to items on the admin theme and in public themes.
-   [SimplePages](../Plugins/SimplePages.md) – Publish static pages on your public site.
-   [Exhibit Builder](../Plugins/ExhibitBuilder.md) – Build narratives around your collections.
