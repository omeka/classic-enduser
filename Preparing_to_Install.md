---
title: Preparing to Install
---

Before installing Omeka, make sure your web server meets our basic system requirements. These are standard requirements that are available by most web hosting services. Once these system requirements are met, all you need to do is install the Omeka software:

System Requirements
------------------------------------------------------------

-   Linux operating system
    -   [Server configuration](https://omeka.org/codex/Server_configuration.md) suggestions
-   [Apache](http://www.apache.org/) HTTP server (with `mod_rewrite` enabled)
-   [MySQL](http://www.mysql.com/) version 5.0 or greater
-   [PHP](http://www.php.net/) scripting language version 5.2.11 or greater (with mysqli and exif extensions installed)
    -   PHP version 5.3+ or the [Fileinfo extension](http://www.php.net/manual/en/fileinfo.installation.php) is highly recommended
-   [ImageMagick](http://www.imagemagick.org/script/index.php) image manipulation software (for resizing images)

### What if I Do Not Have Access to LAMP?
-   Try [Omeka.net](http://omeka.net) hosting
-   Try third-party hosting services, here are some [suggestions](http://omeka.org/codex/Hosting_Suggestions).
-   Set up a local installation or virtual machine See: Local and Virtual Machines

Preparing Your System
------------------------------------------------------

Instructions for preparing different Linux distributions to host your own deployment are included below:

-   [Install on Fedora](https://omeka.org/codex/Install_on_Fedora "Install on Fedora")
-   [Install on OpenSUSE](https://omeka.org/codex/Install_on_OpenSUSE "Install on OpenSUSE")

Upgrading Your System
-----------------------------------------------------------

If you need to upgrade your server to meet any of the Omeka system requirements, consult these resources:

-   [Upgrading Apache](http://httpd.apache.org/docs/2.0/upgrading.html)
-   [Upgrading PHP](http://www.php.net/manual/en/migration5.php)
-   [Upgrading MySQL](http://www.mysql.org/doc/refman/5.1/en/upgrade.html)
-   [Installing ImageMagick](http://www.imagemagick.org/script/install-source.php)

Local and Virtual Machines 
-------------------------------------------------------

There are a number of options available for creating a local
installation or running a virtual machine if you don't have a LAMP server available. Below are some suggestions. Please contact their support if you have difficulties.

-   [Jumpbox](http://www.jumpbox.com/app/omeka)
-   [AMPPS for Windows](http://www.ampps.com/apps/php/educational/Omeka)
-   [MAMP for Macs](http://mamp.info/en/index.html)
-   [Xampp for Windows](http://www.apachefriends.org/en/xampp-windows.html#641)
-   If you are interested in installing Omeka in a VMWare virtual machine running Ubuntu Linux on Mac (VMWare Fusion) and Windows (VMWare server and workstation) desktop platforms, [see these instructions (pdf).](http://sirls.arizona.edu/sites/sirls.arizona.edu/files/omeka.pdf)
