Plugins/MediaRss for Cooliris
=============================

[Plugins](../Plugins.1.html "Plugins")


The **MediaRSS plugin for the Cooliris image viewer** adds a MediaRSS
feed to your Omeka website, making them visible to the [Cooliris Firefox extension](http://www.cooliris.com/) to zoom in and explore digital
images. The feed will display on the items browse page, as well as your
Omeka site's homepage. It will *not* display on items show pages in the
current version (1.0). Visitors will need the Cooliris Firefox extension
to see the feed.

Installation
-----------------------------------------------------------------

Upload and activate the MediaRss plugin (see [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin")).

Insert the following PHP code into the header.php file of your theme,
above the "auto\_discovery\_link()" function. This file is located in
the /common/ folder. Add the following code:



``` {.de1}
<?php echo media_rss_rssm(); ?>
```


Directly above the auto\_discovery\_link() function:



``` {.de1}
<?php echo auto_discovery_link_tag(); ?>
```


Disclaimer
-------------------------------------------------------------

[Cooliris](http://cooliris.com) is a registered trademark of Cooliris,
Inc.