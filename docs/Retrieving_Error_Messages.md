---
title: Retrieving Error Messages
---

If Omeka doesn't seem to be behaving correctly, for whatever reason, there are steps you can take to get more descriptive error messages. These are turned off by default, but can be used during the production of an Omeka site for troubleshooting.

Display Error Messages
--------------------------------------------------------------

You can change some configuration settings in Omeka to display error messages directly on the screen.

After enabling error messages, return to the page in Omeka that is causing the error. Do your best to repeat whatever originally caused the error, then send us the error message that is displayed on your screen. Be sure to disable these settings again once the problem is resolved.

The error display settings are different between Omeka 2.0 and older versions of Omeka:

### Omeka 2.0 and newer 

1.  Open the `.htaccess` file in the root of your Omeka installation, find the following line, and uncomment it (that is, remove the `#` sign):  `#SetEnv APPLICATION_ENV development`
2.  (Optional) If you're trying to debug a 404 ("Not Found") or 403 ("Forbidden") error, open `application/config/config.ini`, and change the value of `debug.exceptions` to `true`.

### Omeka 1.5 and older 

1.  Open the .htaccess file in the root of your Omeka installation, and change the value of `php_value display_errors` to `1`.
2.  Open 'application/config/config.ini', and change the value of `debug.exceptions`  to `true`.

Activate Error Logging
--------------------------------------------------------------
If you'd prefer to not have your error messages publicly displayed on your site, you can instead activate error logging. Activating error logging will log any errors encountered by Omeka to a file in `application/log` directory of Omeka. You can then post to the forum or email directly to us.

1.  Change permissions on your installation so that the following file is writable by your server: `application/logs/errors.log`
2.  Edit your `application/config/config.ini` file and change the value of `log.errors` to `true`.
3.  Do your best to repeat whatever originally caused the error, then send us the relevant contents of the `errors.log` file.