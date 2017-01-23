---
title: Managing Security Settings
---
*This documentation for Omeka versions up to 1.5 only*

Disable File Upload Validation:
    -   By default this box is unchecked, giving site administrators the ability to limit file uploads to specific extensions and MimeTypes.
    -   If administrators have difficulty with the site recognizing files, he/she may check this and allow for any file to be uploaded into the Omeka site.

Allowed File Extensions:
    -   The default list contains the most common file extensions. It acts as a "white list," meaning that in order for a file to be uploaded into an Omeka site the file extension must be listed here. Administrators may add file extensions to this list.

Allowed File Types:
    -   This default list contains common Mime Types associated with different types of files. This also acts as a "white list," so that all Mime Types must be listed here in order for files to be uploaded.
    -   If a user gets an error, such "file could not be ingested because it has a disallowed MIME type (application/download)." Copy the Mime Type, which is this is 'application/download', and add it to this list. Save changes.

ReCaptcha Public and Private Keys:
    -   If you are using a public-facing form (Contribution plugin, Simple Contact), please sign up for a [ReCaptcha key](http://www.google.com/recaptcha) to reduce spam sent to the administrator's email.

