# System Requirements

Omeka Classic version 3.2 has the following system requirements:

-   Linux operating system
-   [Apache](http://www.apache.org/){target=_blank} HTTP server (with `mod_rewrite` enabled)
-   [MySQL](http://www.mysql.com/){target=_blank} version 5.5.5 or greater
-   [PHP](http://www.php.net/){target=_blank} scripting language version 7.1 or higher (with `mysqli` and `exif` extensions installed). Omeka Classic 3.2.1 supports PHP as high as 8.5.
-   [ImageMagick](http://www.imagemagick.org/script/index.php){target=_blank} image manipulation software (for resizing images).

## Upgrade your server

If you need to upgrade your server to meet any of the Omeka system requirements, consult these resources:

-   [Upgrading Apache](https://httpd.apache.org/docs/current/upgrading.html){target=_blank} (look for the migration guide appropriate to your version)
-   [Upgrading PHP](https://www.php.net/migration81){target=_blank} (look for the migration guide appropriate to your version)
-   [Upgrading MySQL to version 5.5.5 or higher](https://dev.mysql.com/doc/refman/8.0/en/upgrading.html){target=_blank} (look for the migration guide appropriate to your version)
-   [Installing ImageMagick](http://www.imagemagick.org/script/install-source.php){target=_blank}.

Some [plugins](https://omeka.org/classic/plugins/){target=_blank} may have other requirements, such as the [PDF Text plugin](../Plugins/PdfText.md), which requires your server to have [`poppler-utils`](https://pypi.org/project/poppler-utils/){target=_blank} installed for text extraction. Be sure to read the documentation on your desired plugins and features to understand all dependencies before you begin building your site, including the Github pages or other external sites, not just the Omeka user manual and plugins page. 

### Support by version

Omeka Classic adds support for newer PHP and MySQL versions with new releases, but also removes compatibility with earlier versions. Each Classic update has a minimum requirement and a maximum official support, although often you can upgrade PHP past our tested maximum with no issues. 

This information is most reliably found on the Github repository's [Releases](https://github.com/omeka/Omeka/releases){target=_blank} list. 

- Omeka Classic 3.2.1 adds support for PHP 8.5
- Omeka Classic 3.2 supports a minimum of PHP 7.1 and adds support for 8.4 
- Omeka Classic 3.1 supports a minimum of PHP 5.6 and adds support for 8.2
- Omeka Classic 2.8 adds support for PHP 8
- Omeka Classic 2.7.1 supports a minimum of PHP 5.4 and adds support for 7.4
- Omeka Classic 2.7 adds support for PHP 7.3
- Omeka Classic 2.6 adds support for PHP 7.2
- Omeka Classic 2.4 supports a minimum of PHP 5.3.2. 

Omeka Classic v3.2 and greater require a minimum of MySQL 5.5.5. Most earlier versions of Omeka Classic require a minimum of MySQL 5.0. 

### If your server does not meet these requirements

-   Earlier versions of Omeka Classic can be downloaded from the Github repository's [Releases](https://github.com/omeka/Omeka/releases){target=_blank} list. You may find an earlier version has requirements that match your server's capabilities. Note you will need to find the corresponding earlier versions of themes and plugins to match that release. Note also that earlier versions may have security vulnerabilities that are fixed in later versions. 
-   Try [Omeka.net](http://omeka.net){target=_blank} hosting
-   Look for a hosting provider that offers Omeka Classic through [Softaculous or Installatron apps managers](../GettingStarted/Hosting_Suggestions.md)
-   Try third-party hosting services - here are some [suggestions](../GettingStarted/Hosting_Suggestions.md).
