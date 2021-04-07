# Setting the PHP Path

An invalid php path can cause a number of problems for your Omeka Classic installation. You need a valid php path to run plugins like CSV import and Neatline.

By default, Omeka Classic tries to autodetect the php path for your server. However, if you have turned on [error messages](../Troubleshooting/Retrieving_Error_Messages.md) and the message starts with a phrase such as `The configured PHP path (/bin/php) is invalid`, then you need to set the path manually.

To set your php path you will need access to the server where your Omeka site lives; you set the path by editing files in the Omeka site. You cannot set the php path from the admin dashboard.

To set the php path

- Contact your hosting company or sysadmin and ask them for the correct php path for your Omeka Classic installation.
	- NB: If you are using Reclaim Hosting, they [have instructions in their documentation](https://community.reclaimhosting.com/t/working-with-omeka-classic/194/2). 
- Navigate to the files for your Omeka site, either using your hosting company's File Manager, an FTP client, or ssh. 
- Open the directory `application`
- Open the file `config.ini` in `application/config`
- Find the lines which look like this: 
```
; If left blank, Omeka will try to autodetect the right path. Set this
; to override the autodetected PHP path.
background.php.path = ""
```
- Edit the file so that the line now reads `background.php.path = "<php path>"` where the `<php path>` is the path provided by your hosting company or sysadmin. 
- If you have downloaded the file in order to edit it, be sure to upload the changed version back to your Omeka installation.
