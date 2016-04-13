Moving to Another Server
========================

Before moving an existing Omeka project from one server to another, you
should [upgrade](Upgrading.html "Upgrading") your existing installation
to the latest version.

To move an existing Omeka project, you need to move a) the information
in the database, and b) the files. The basic procedure for transferring
both is this:

1.  **Export your existing database** as a .sql file. There are pretty
    good instructions on how to do this using either phpMyAdmin or the
    command line, with screenshots, at
    <http://codex.wordpress.org/Backing_Up_Your_Database> (Omeka is very
    similar to WordPress).
2.  **Import your old database into the new server** using the .sql file
    you created in the previous step. Again, you can use phpMyAdmin or
    the command line.
3.  **Upload a clean copy of the Omeka install files to the new
    server**. Fill out the db.ini file with the credentials for your new
    copy of the database that you just imported.
4.  **Download files and folders from the old server** to the hard drive
    of your computer. The files and folders you will need are these:
    -   In versions 1.5 and below:
        -   archive/
        -   plugins/
        -   themes/
        -   any other files you have personally modified
    -   In versions 2.0 and above:
        -   files/
        -   plugins/
        -   themes/
        -   any other files you have personally modified

5.  **Upload these files and folders to the new server,** overwriting
    the existing ones.
6.  **Reactivate your plugins and your theme.**

You may have to reset the permissions for the files folder and its
subfolders, and for any plugins that require directories to be writable.
See [Setting Directory
Permissions](https://omeka.org/codex/Setting_Directory_Permissions "Setting Directory Permissions")
for more details.

If you have trouble, submit your question to the
[forums](../forums.1.html).

