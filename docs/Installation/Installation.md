---
title: Installation
---

Check System Requirements
----------------------------------------------------------------
Before installing, check to make sure your server meets the [system requirements](/System_Requirements)


## Preparing to Install
Before installing Omeka, make sure your web server meets our basic [system requirements](/System_Requirements.md). These are standard requirements that are available by most web hosting services. Once these system requirements are met, all you need to do is install the Omeka software:

### Upgrading Your System

If you need to upgrade your server to meet any of the Omeka system requirements, consult these resources:

-   [Upgrading Apache](http://httpd.apache.org/docs/2.0/upgrading.html)
-   [Upgrading PHP](http://www.php.net/manual/en/migration5.php)
-   [Upgrading MySQL](http://www.mysql.org/doc/refman/5.1/en/upgrade.html)
-   [Installing ImageMagick](http://www.imagemagick.org/script/install-source.php)

7 Easy Steps for Installing with LAMP server setup 
-----------
Note: If you are doing a One-Click install from Dreamhost, you must edit the `db.ini` file in the Omeka directory (see 3 below).

If you want to use Omeka in a language other than English, you will need to configure it in the `/application/config/config.ini` file. See [Configuring Language](/Configuring_Language) for details. The installation steps are localized, so you might want to do this before the rest of the installation steps below. It is fine to change this after your site is successfully installed.

1. **Create a MySQL database** on your web host, as well as a user with permissions to modify the database.
    - Make sure to take note of the database hostname, the database name, the database user's username, and the database user's password.
    - Make sure the collation of your database is set to 'utf8_unicode_ci' and that the charset is 'utf8'.

1. **Download the latest version of Omeka** and uncompress the .zip file.
    -   The .zip file will have a name similar to 'omeka.zip' that includes the version number.
    -   Save the .zip file somewhere you can find it again, such as your Download folder. Double-click the .zip file to extract the files in the .zip archive, and make sure to note where the files are extracted.
    -   If you are unable to extract the files, you might need to download an uncompression program such as WinZip or WinRAR (for Windows)or Stuffit Expander (for Mac).
    -   The extracted (uncompressed) directory will have a name similar to 'omeka' that includes the version number.
    -   Users familiar with git might want to clone the code from [our public GitHub repository](http://github.com/omeka/Omeka).

1. In the resulting directory, find and open your database configuration file, which is named `db.ini`. **Replace the 'XXXXX' values in the db.ini file** with your database host, username, password, and database name.
    -   You can edit the `db.ini` file with a text editor such as Notepad for Windows or TextEdit for Mac. Be sure to save the file as plain text and keep the name `db.ini`.
    -   You do not need to change values for `prefix` and `port` in the db.ini file.

4.  **Upload the directory** and all of its contents, including the
    updated `db.ini` file, to your server.
    -   If you have command-line access to your server, you can upload the Omeka .zip file and unzip it on the server.
    -   If you do not have command-line access to your server, you can use a file transfer program such as Filezilla or FireFTP to transfer the contents of the unzipped omeka directory to your server. This may take 20 minutes or more.
    -   Make sure to upload the `.htaccess` file that's in the top-level directory of the Omeka zip along with the rest of the files. This file is hidden by default in many file transfer programs; to see the `.htaccess` file, you may need to change the preferences in your file transfer program.
    -   You can rename the omeka directory either before or after you upload it to give it a URL that is relevant to your project.

5.  **Make Omeka's storage directory and its sub-directories writable by the web server.** For Omeka 1.5.3, the directory is `archive`. For Omeka 2.0+, the directory is `files`. You can change the permissions yourself with an FTP or other file transfer program, or with shell commands over SSH. If you're not sure what to do, ask your host for advice, or to change the permissions for you.
6.  Open your web browser and **visit the URL** where you uploaded the omeka directory. Click "Install".
    -   If you renamed the omeka directory 'project' and put it in the top-most directory of your site, for instance, the URL to visit would be `http://mydomain.org/project`.

7.  **Complete the installation form** by filling out the required fields, including the name of your Omeka site, email address, and username/password of the super user (the super user account controls the entire website).
    -   You can change these settings in [General Settings](../Admin/Settings/General_Settings) once the installation is complete.
    -   You can leave fields that are already filled in as they are; you do not need to change the values.

If the installation was **successful,** you'll see a screen with links to view the live site or to log in with the superuser's username and password to the administrative panel at `http://mydomain.org/admin`. Congratulations!

If your installation was **unsuccessful,** try these steps:

-   Make sure that both `.htaccess` files mentioned above (only the top-level one for Omeka 1.4 and higher) were successfully uploaded.
-   If both `.htaccess` files were successfully uploaded but your installation is still unsuccessful, make sure that the information in the 'db.ini' file on the server is correct.
-   If your installation is still unsuccessful, try deleting the entire omeka directory from your server and reuploading it. One or more files might have failed to upload.
-   If the installation is apparently successful, but you are unable to upload items through the admin interface, make sure that you correctly followed the instructions in Step 4 above. Your web server *must* have write access to the 'archive' directory for you to upload files.
-   If the installation is successful, but you are getting "File not found" errors when you navigate to addresses such as `http://mydomain.org/admin`, you probably have a conflict with another CMS such as WordPress on the same server. To fix this issue, you probably need to enable the "RewriteBase" line in your `.htaccess` file.
-   If you still have issues, please consult the [Troubleshooting Omeka](../Troubleshooting/Troubleshooting_Omeka) page or post your issue on the [forums](http://forum.omeka.org).
