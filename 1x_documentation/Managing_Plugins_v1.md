---
title: Managing Plugins
---
*This documentation for Omeka versions up to 1.5 only*

Plugins are tools to extend the basic functionality of Omeka. A list of plugins available for download is on the Plugins Add-Ons
Directory, and documentation for specific plugins is linked from the [Plugins](../1x_documentation/Plugins_1.md) index page. 


-   **Install** – Runs the installer for the plugin and activates the plugin.
-   **Uninstall** – Runs the uninstaller for the plugin and deletes any information in your installation related to the plugin.
-   **Activate** – Activates plugin settings and allows you to configure a plugin when necessary.
-   **Deactivate** – Action merely "unplugs" the plugin but does not delete any data collected while plugin was active.

In some cases, plugins can delete data associated with the plugin from your database on uninstall. Check the plugin's documentation before uninstalling if you're unsure.

[Installing Plugins Screencast](../1x_documentation/1x_Screencasts/InstallingPlugins1.0.mov)

## Installing a Plugin

To add and activate a new plugin for your Omeka installation, follow these steps:

1. Download and unzip the file on your desktop.
2. Open your FTP client.
3. Use your FTP login info to access your site.
4. Navigate to your Omeka folder. It should have the same name as your Omeka install, and may be located in the public_html folder
5. Open the /plugins folder
6. Upload your new plugin folder into your Omeka website’s /plugins folder. Sometimes the unpacked plugin is inside a folder of the same name so make sure you are uploading the correct directory.
NB: your plugin must be inside the /plugins folder
7. Log in to your Omeka admin panel

8. Navigate to Plugins, and find the plugin you uploaded.
9. If the plugin is not visible, return to step 6 and double-check the folder's name. If the plugin is visible, click “Install” to finish the process.
10. Click “Configure” if available/needed.
11. Read documentation for plugin to understand configuration

## Configuring a Plugin
Some plugins will require additional configuration before they can work with Omeka. If this is the case, a "Configure" link will appear beside the plugin in the admin panel. Click on that link to configure the plugin as needed.

## Pre-Packaged Plugins
The following plugins come prepackaged with Omeka:
- [Coins](../1x_documentation/Plugins_1x/Coins.md) – Adds Coins metadata to items on the admin theme and in public themes.
- [ExhibitBuilder](../1x_documentation/Plugins_1x/ExhibitBuilder.1.html): Enables users to create exhibits with items in your Omeka archive.
- [SimplePages](../1x_documentation/Plugins_1x/SimplePages.html "Plugins/SimplePages”): Publish static pages on your public site.


