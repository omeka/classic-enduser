Managing Security Settings 2.0
==============================

To manage Security Settings, select Settings in the top navigation bar.
In the Settings screen, choose Security. Only Super users may edit these
settings.

[![Securitynav2.png](https://omeka.org/c/images/d/df/Securitynav2.png)](https://omeka.org/codex/File:Securitynav2.png)


Security settings enable you to determine the file formats and html
markup allowed on your Omeka site and to set Captcha controls to protect
your site from automated spam.

Disable File Upload Validation
---------------------------------------------------------------------------------------------------

-   The Disable File Upload Validation box is unchecked by default. The
    unchecked box allows you to limit file uploads to specific
    extensions and MimeTypes.
-   Checking this box allows upload of any file type to the Omeka site.
-   Remember to click Save Changes in the right hand navigation column
    when you have finished.

Allowed File Extensions
-------------------------------------------------------------------------------------

[![Allowedfileext.png](https://omeka.org/c/images/e/e3/Allowedfileext.png)](https://omeka.org/codex/File:Allowedfileext.png)

-   The default list contains the most common file extensions. Only
    files with extensions included in this list may be uploaded to the
    Omeka site (unless the Disable File Upload Validation box
    is checked).
-   You may add or delete file extensions. Be sure that each file
    extension is separated by a comma.
-   You may restore the original listing of file extensions by clicking
    on the Restore Default File Extensions button. After you restore
    default listings, however, an Undo button allows you to reconsider
    and revert to your changes.
-   Remember to click Save Changes in the right hand navigation column
    when you have finished.

Allowed File Types
---------------------------------------------------------------------------

[![Allowedmime.png](https://omeka.org/c/images/9/9e/Allowedmime.png)](https://omeka.org/codex/File:Allowedmime.png)

-   This default list contains common Mime Types associated with
    different types of files. Only Mime Types included on this list may
    be uploaded to the Omeka site (unless the Disable File Upload
    Validation box is checked).
-   If a mime type is not allowed, an error message results, e.g. "file
    could not be ingested because it has a disallowed MIME type
    (application/download)." Copy the Mime Type, in this case,
    'application/download', and add it to the list of allowed File
    Types, separating each addition with a comma. Click Save Changes in
    the right hand navigation column.
-   You may restore the original listing of file types by clicking on
    the Restore Default File Mime Types button. After you restore
    default listings, however, an Undo button allows you to reconsider
    and revert to your changes.
-   Remember to click Save Changes in the right hand navigation column
    when you have finished.

Captcha
-----------------------------------------------------

[![Captcha.png](https://omeka.org/c/images/6/66/Captcha.png)](https://omeka.org/codex/File:Captcha.png)

-   If you are using a plugins requiring public forms on your Omeka site
    such as the Contribution plugin and Simple Contact, sign up for a
    [Captcha](http://www.google.com/recaptcha) key to reduce spam on
    your site. Captcha requires users who fill in public forms to repeat
    letters or digits in a distorted image in order to post content.
-   Add the generated output from Captcha in the Public Key and Private
    key fields in your Omeka site. Captcha forms will automatically
    appear with public forms on your site.
-   Remember to click Save Changes in the right hand navigation column
    when you have finished.

HTML Filtering
-------------------------------------------------------------------

You may choose whether to filter HTML elements and attributes utilized
as you fill in forms and metadata fields on your Omeka site.

By default, all HTML elements and attributes are allowed in Omeka when
the box Enable HTML Filtering is unchecked.



[![Securityenhtml.png](https://omeka.org/c/images/3/37/Securityenhtml.png)](https://omeka.org/codex/File:Securityenhtml.png)


-   If you would like to limit the use of html, place a check in
    that box. When you enable HTML filtering, only elements listed in
    the Allowed HTML Elements and the Allowed HTML Attributes fields
    will function on your site.

[![Securityallelements.png](https://omeka.org/c/images/b/be/Securityallelements.png)](https://omeka.org/codex/File:Securityallelements.png)

-   You may add or delete HTML elements and attributes. (In the image
    above, the paragraph element is deleted from the list of Allowed
    HTML Elements).
-   Selecting Restore default buttons returns your allowed elements or
    attributes to the original listing. To revert to your edited
    selections, click the Undo button.
-   Remember to click Save Changes in the right hand navigation column
    when you have finished.

