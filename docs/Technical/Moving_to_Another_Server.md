# Moving to Another Server

The most straightforward way to move an Omeka Classic project between servers is to set up a new install on the new server with matching plugins and use the [Omeka API Importer plugin](../Plugins/Omeka_API_Import.md) to transfer items, files, collections, simple pages, exhibits, etc.

If this is not an option (the original site is no longer online or is on an internal network), follow the legacy instructions below.

## Legacy Instructions

Before moving an existing Omeka project from one server to another, you should [upgrade](../Installation/Upgrading.md) your existing installation to the latest version.

To move an existing Omeka project, you need to move a) the information in the database, and b) the files. The basic procedure for transferring both is this:

1.  **Export your existing database** as a .sql file. [More info](Backing_up_an_Omeka_Database.md).
2.  **Import your old database into the new server** using the .sql file you created in the previous step. Again, you can use phpMyAdmin or the command line.
3.  **Upload a clean copy of the Omeka install files to the new server**. Fill out the db.ini file with the credentials for your new copy of the database that you just imported.
4.  **Download files and folders from the old server** to the hard drive of your computer. The files and folders you will need are these:
    -   In versions 2.0 and above:
        -   files/
        -   plugins/
        -   themes/
        -   any other files you have personally modified
    -   In versions 1.5 and below:
        -   archive/
        -   plugins/
        -   themes/
        -   any other files you have personally modified

5.  **Upload these files and folders to the new server,** overwriting the existing ones.
6.  **Reactivate your plugins and your theme.**
 You may have to reset the permissions for the files folder and its subfolders, and for any plugins that require directories to be writable. See [Setting Directory Permissions](../Installation/Setting_Directory_Permissions.md) for more details.

If you have trouble, submit your question to the
[forums](https://forum.omeka.org){target=_blank}.

