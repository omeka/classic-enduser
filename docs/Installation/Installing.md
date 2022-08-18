# Installation

## Preparing to Install
Before installing Omeka Classic, make sure your web server meets our basic [system requirements](System_Requirements.md). These are standard requirements that are available with many web hosting services. Once these requirements are met, all you need to do is install the Omeka software.

7 Easy Installation Steps
-----------

!!! note
	If you are doing a one-click install through [Installatron](../GettingStarted/Hosting_Suggestions.md), you may need to edit the `db.ini` file in the Omeka directory (see step 4 below). The one-click installation process through Softaculous may allow you to create a database and user at the same time, and will edit the `db.ini` file for you.

1. **Pick your language** (optional).
	- If you want to use Omeka Classic in a language other than English, you will need to configure it in the `/application/config/config.ini` file. See [Configuring Language](Configuring_Language.md) for details. The installation steps are localized, so you may want to do this before the rest of the installation steps below. You can also change this after your site is successfully installed.

1. **Create a MySQL database** on your web host, as well as a user with permissions to modify the database.

    - Make sure to take note of the database hostname, the database name, the database user's username, and the database user's password.
    - Make sure the collation of your database is set to `utf8_unicode_ci` and that the charset is `utf8`.

1. **Download the [latest version of Omeka](https://omeka.org/classic/download/){target=_blank}** and extract the .zip file.

    - The .zip file will have a name similar to `omeka-0.0.0.zip` that includes the version number.
    - Save the .zip file somewhere you can find it again, such as your Download folder. Double-click the .zip file to extract the files in the .zip archive, and make sure to note where the files are extracted.
    -   If you are unable to extract the files, you might need to download an extraction program such as [WinZip](https://www.winzip.com/){target=_blank} or [WinRAR](https://www.win-rar.com/){target=_blank} (for Windows) or [Stuffit Expander](https://stuffit.com/){target=_blank} (for Mac and Windows).
    -   The extracted (uncompressed) directory will have a name similar to `omeka-0.0.0` that includes the version number.
    -   Users familiar with Git might want to clone the latest code from [our public GitHub repository](http://github.com/omeka/Omeka){target=_blank}.

1. In the directory created by the extraction process, find and open your database configuration file, named `db.ini`. **Replace the 'XXXXX' values in the `db.ini` file** with your MySQL database host, database name, username, and password.

    -   You can edit the `db.ini` file with a text editor such as Notepad for Windows or TextEdit for Mac. Be sure to save the file as plain text and keep the name `db.ini`.
    -   Do not change the values for `prefix` and `port` in the `db.ini` file.
    -   See the [Database Configuration File page](../Technical/DatabaseConfigurationFile.md) for an explanation of each element in the `db.ini` file.

1.  **Upload the directory** and all of its contents, including the updated `db.ini` file, to your server.

    -   You can use a file transfer program such as Filezilla or FireFTP to transfer the contents of the directory to your server. This may take some time. Be sure to upload the directory with the edited file, not the original .zip file. 
    -   Make sure the `.htaccess` file that's in the top-level directory gets uploaded. This file is hidden by default in many file transfer programs; to see the `.htaccess` file, you may need to change the preferences in your file transfer program.
    -   If you have command-line access to your server, you can re-compress a directory with the updated file, upload it, and extract it on the server.
    -   Rename the directory before or after you upload it, to **give your Omeka installation a URL that is relevant to your project**.

1.  **Make Omeka's file-storage directory and its sub-directories writable by the web server.** 
	- For Omeka 1.5.3, the directory is called `archive`. 
	- For Omeka 2.0+, the directory is called `files`. 
	- Follow the directions on the [Setting Directory Permissions page](Setting_Directory_Permissions.md). You can set the permissions with your file transfer program, or with shell commands over SSH. If you're not sure what to do, ask your hosting provider for advice, or to change the permissions for you.

1.  Open your web browser and **visit the URL** where you uploaded the Omeka directory. Click "Install."

    -   If you renamed the Omeka directory `collections` and put it in the top-most directory of your site, for instance, the URL to visit would be `https://youromekadomain.org/collections`.

1.  **Complete the installation form** by filling out the required fields, including the name of your Omeka site, email address, and username/password of the super user (the super user account controls the entire website).

    -   You can change these settings in [General Settings](../Admin/Settings/index.md) once the installation is complete.
    -   You can leave fields that are already filled in as they are; you do not need to change the values.

If the installation was **successful**, you'll see a screen with links to view the live site or to log in with the superuser's username and password to the administrative panel at `https://youromekadomain.org/collections/admin`. Congratulations!

## Troubleshooting

If your installation was **unsuccessful**, try these steps:

-   Make sure that the `.htaccess` file mentioned above was successfully uploaded. (For Omeka 1.3.1 and earlier, there are two `.htaccess` files: one in the root directory and one in the "admin" directory.)
-   If the `.htaccess` file was successfully uploaded but your installation is still unsuccessful, make sure that the information in the `db.ini` file on the server is correct.
-   If your installation is still unsuccessful, try deleting the entire Omeka directory from your server and reuploading it. One or more files might have failed to upload.
-   If the installation is apparently successful, but you are unable to upload items through the administrative interface, make sure that you correctly followed the instructions in step 6 above. Your web server *must* have write access to the file-storage directory for you to upload files.
-   If the installation is successful, but you are getting "File not found" errors when you navigate to addresses such as `https://youromekadomain.org/collections/admin`, you probably have a conflict with another CMS such as WordPress on the same server. To fix this issue, you probably need to enable the "RewriteBase" line in your `.htaccess` file.
-   If you still have issues, please consult the [Troubleshooting Omeka](../Troubleshooting/index.md) page or post your issue on the [forum](https://forum.omeka.org/c/omeka-classic/7){target=_blank}.
