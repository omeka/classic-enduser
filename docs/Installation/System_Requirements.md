# System Requirements

Omeka Classic has the following system requirements:

-   Linux operating system
-   [Apache](http://www.apache.org/){target=_blank} HTTP server (with `mod_rewrite` enabled)
-   [MySQL](http://www.mysql.com/){target=_blank} version 5.0 or greater
-   [PHP](http://www.php.net/){target=_blank} scripting language version 5.4 or higher (with mysqli and exif extensions installed)
-   [ImageMagick](http://www.imagemagick.org/script/index.php){target=_blank} image manipulation software (for resizing images).

## Upgrading Your System

If you need to upgrade your server to meet any of the Omeka system requirements, consult these resources:

-   [Upgrading Apache](https://httpd.apache.org/docs/current/upgrading.html){target=_blank} (look for the migration guide appropriate to your version)
-   [Upgrading PHP to version 5.4 or higher](https://www.php.net/migration81){target=_blank} (look for the migration guide appropriate to your version)
-   [Upgrading MySQL to version 5.0 or higher](hhttps://dev.mysql.com/doc/refman/8.0/en/upgrading.html){target=_blank} (look for the migration guide appropriate to your version)
-   [Installing ImageMagick](http://www.imagemagick.org/script/install-source.php){target=_blank}

Some [plugins](https://omeka.org/classic/plugins/){target=_blank} may have other requirements, such as the [PDF Text plugin](../Plugins/PdfText.md), which requires your server to have [poppler-utils](https://pypi.org/project/poppler-utils/){target=_blank} installed for text extraction. Be sure to read the documentation on your desired plugins and features to understand all dependencies before you begin building your site, including the Github pages or other external sites, not just the Omeka user manual and plugins page. 

### If your server does not meet these requirements
-   Try [Omeka.net](http://omeka.net){target=_blank} hosting
- Look for a hosting provider that offers Omeka Classic through [Softaculous or Installatron apps managers](../GettingStarted/Hosting_Suggestions.md)
-   Try third-party hosting services - here are some [suggestions](../GettingStarted/Hosting_Suggestions.md).
