# Setting the PHP path

An invalid PHP path can cause a number of problems for your Omeka Classic installation. You need a valid PHP path to run plugins such as [CSV Import](../Plugins/CSV_Import.md).

By default, Omeka Classic tries to autodetect the PHP path for your server. However, if you have turned on [error messages](../Troubleshooting/Retrieving_Error_Messages.md) and the message starts with a phrase such as "The configured PHP path (/bin/php) is invalid", then you need to set the path manually. 

You may also wish to manually select an earlier stable PHP version, rather than a new version that may be causing unexpected behavior in your Omeka site.

To set your PHP path you will need access to the server where your Omeka Classic site lives; you set the path by editing files in the Omeka site. You cannot set the PHP path from the admin dashboard.

To set the PHP path:

- Search the help documentation or knowledge base for your hosting company for the correct PHP path; this is a frequently asked question for a large variety of software installations. If you can't find anything, contact your hosting company or sysadmin and ask them.
	- If you are using Reclaim Hosting, they [have instructions in their documentation](https://community.reclaimhosting.com/t/working-with-omeka-classic/194/2){target=_blank}.
	- Other hosting services may require you to change the PHP version for your entire website or using special instructions. For example, see [Dreamhost's instructions](https://help.dreamhost.com/hc/en-us/articles/214895317-Change-the-PHP-version-of-a-site){target=_blank}.
- Navigate to the files for your Omeka site, either using your hosting company's File Manager, an FTP client, or ssh. 
- Open the directory `application`.
- Open the file `config.ini` in `application/config`.
- Find the lines that look like this: 
```
;;;;;;;;;;;;;;;;;;;;;;
; Background Scripts ;
;;;;;;;;;;;;;;;;;;;;;;

; background.php.path
; Path to PHP-CLI for running background processes.
; default: ""
;
; If left blank, Omeka will try to autodetect the right path. Set this
; to override the autodetected PHP path.
background.php.path = ""
```
- Edit the file so that the last line now reads `background.php.path = "<php path>"` where the `<php path>` is the path provided by your hosting company or sysadmin. 
	- This path commonly looks like `/usr/local/php80/bin/php`, `/usr/local/bin/php`, or `/usr/local/bin/ea-php74`.
- If you have downloaded the file in order to edit it, be sure to upload the changed version back to your Omeka installation.
