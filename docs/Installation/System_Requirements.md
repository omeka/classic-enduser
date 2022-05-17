# System Requirements

Omeka Classic has the following system requirements:

-   Linux operating system
-   [Apache](http://www.apache.org/) HTTP server (with `mod_rewrite` enabled)
-   [MySQL](http://www.mysql.com/) version 5.0 or greater
-   [PHP](http://www.php.net/) scripting language version 5.4 or higher (with mysqli and exif extensions installed)
-   [ImageMagick](http://www.imagemagick.org/script/index.php) image manipulation software (for resizing images).

## Upgrading Your System

If you need to upgrade your server to meet any of the Omeka system requirements, consult these resources:

-   [Upgrading Apache](https://httpd.apache.org/docs/current/upgrading.html) (look for the migration guide appropriate to your version)
-   [Upgrading PHP to version 5.4 or higher](https://www.php.net/migration81) (look for the migration guide appropriate to your version)
-   [Upgrading MySQL to version 5.0 or higher](hhttps://dev.mysql.com/doc/refman/8.0/en/upgrading.html) (look for the migration guide appropriate to your version)
-   [Installing ImageMagick](http://www.imagemagick.org/script/install-source.php)

Some [plugins](https://omeka.org/classic/plugins/) may have other requirements, such as the [PDF Text plugin](../Plugins/PdfText.md), which requires your server to have [poppler-utils](https://pypi.org/project/poppler-utils/) installed for text extraction. Be sure to read the documentation on your desired plugins and features to understand all dependencies before you begin building your site, including the Github pages or other external sites, not just the Omeka user manual and plugins page. 

### If your server does not meet these requirements
-   Try [Omeka.net](http://omeka.net) hosting
- Look for a hosting provider that offers Omeka Classic through [Softaculous or Installatron apps managers](../GettingStarted/Hosting_Suggestions.md)
-   Try third-party hosting services - here are some [suggestions](../GettingStarted/Hosting_Suggestions.md).
