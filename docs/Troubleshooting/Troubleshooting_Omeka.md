---
title: Troubleshooting Omeka
---

404 Errors
-------------------------------------------------------------

If you follow a link in Omeka and you get a 404 error or an error saying the URL is not valid, this is likely caused by a `mod_rewrite` problem on your server. There are two possibilities:

1.  You forgot to copy the `.htaccess` file when FTPing your install. Double check that it transferred properly.
2.  Your server may not have `mod_rewrite` installed. Create a PHP file with the following code: `<?php phpinfo(); ?>` and double check that it's currently enabled. (How? Where?) If not, contact your system administrator. `mod_rewrite` is currently a requirement for Omeka.

If installing `mod_rewrite` does not solve the problem, check that your Apache configuration allows `.htaccess` overrides. You will need the `AllowOverrides All` directive in the appropriate place in `httpd.conf`.

Getting Better Error Messages
---------------------------------------------------------------
A blank or white screen is often an indication that Omeka or PHP has encountered an error. Since error messages can often contain private or technical information, Omeka hides them by default. See [retrieving error messages](/Retrieving_Error_Messages.md) for instructions on how to show these messages. The content of error messages can be extremely useful for troubleshooting, so try these steps before seeking further help.

Further Help Troubleshooting
----------------------------------------------------------
If you continue to have problems, please post a description of your issue along with the version of Omeka and any plugins involved on the [Omeka Forums](http://forum.omeka.org). 
