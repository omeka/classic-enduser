# Upgrading


!!! note "Upgrading from early versions"

	In order to upgrade from a pre-2.0 version of Omeka Classic, you must be running at least 1.2.1. If you are running an earlier version of Omeka Classic, please first upgrade to [1.2.1](https://github.com/omeka/Omeka/tree/1.2.1){target=_blank}. You can then upgrade directly to the latest version of Omeka Classic.

1.  Always **back up your database** in case something goes wrong during the upgrade. For instructions, see [Backing up an Omeka Database](../Technical/Backing_up_an_Omeka_Database.md).
1.  **Deactivate your plugins** in Settings &gt; Plugins of the administrative panel.
    - Be careful not to *uninstall* the plugins, because you may lose data. See the instructions for [upgrading plugins](../Admin/Adding_and_Managing_Plugins.md) for more information.
    - Check to make sure your plugins are compatible with the version of Omeka you're upgrading to. Especially when moving from 1.x to 2.x, you may need to use updated versions of plugins instead of the old ones.
1.  **Move your old Omeka Classic installation** out of the way. Either move the contents of the directory to somewhere else on your server, or transfer the files to your local computer.
1.  **Download and unzip** the latest version of Omeka into the empty directory where your previous install of Omeka was located.
     - If you download to your computer and then upload to the server, either see if you can unzip the folder on the server *or* make sure that hidden files are visible on your computer to ensure that all files are transferred.
1.  **Move or copy the following files and directories** from your old Omeka folder to the corresponding location in your new Omeka installation. If copying, make sure you keep all permissions the same as they were before:
    - `db.ini` (in version 0.9, this was located in `application/config/db.ini`; since version 0.10 this has been relocated to the root of your installation.)
    - `application/config/config.ini` if you have changed the language, the PHP path, or other settings
    - `files/` (for versions below 2.0, the folder is instead named `archive/`) 
    - If you are upgrading from 1.x to 2.x, rename `archive` to `files`, and rename the `files/files` in the directory you just renamed to `files/original`.
    - Any themes or plugins you had installed. The bundled themes (Thanks Roy, Berlin, Seasons) and plugins (COinS, Exhibit Builder, Simple Pages) will already have been updated with Omeka, so don't move them back over.
    - If you've modified any of Omeka's core files, you'll need to move those changes over too. Be careful with this and make your edits line by line, as the original file may have been changed in newer versions. 
1.  Finally, you may need to **upgrade your database**. Go to your Omeka site's administrative panel in your web browser.
    - To access your site's administrative panel after upgrading, go to `example.com/admin`. If a database upgrade is needed, you will not be able to access your site's dashboard from your site's home page, which will display the message, "Public site is unavailable until the upgrade completes."
    - If a database upgrade is needed, you'll automatically be redirected from your admin page to an upgrade page (`example.com/admin/upgrade`). Click "Upgrade" to update your database to reflect the new data model and finish the upgrade. 
    - For Omeka 1.2.1 and earlier only: Instead of redirecting, older Omeka versions will show an alert on your dashboard with a link to follow if the database needs to be upgraded.
    - If you weren't redirected when you went to your administrative panel, then no database changes were required, so you're done!

## Troubleshooting an upgrade
If you have problems upgrading, double-check to make sure that the `db.ini`, `config.ini` (in the `application/config` folder), and `.htaccess` files are present and have the correct information. 
