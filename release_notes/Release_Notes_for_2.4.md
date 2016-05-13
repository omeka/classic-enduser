Omeka 2.4 was released on January 21, 2016.

PHP Requirements Changes
------------------------

-   ‘’’Omeka 2.4 requires PHP 5.3.2 or higher.’’’ Previous versions have worked with the PHP 5.2 series, so be sure to check what version you’re running before you upgrade.
-   Omeka 2.4 now supports PHP 7.

Audio and Video Support Changes
-------------------------------

To keep up with the changing browser support landscape, Omeka now uses HTML 5’s `audio` and `video` tags when embedding audio and video, instead of the `object` and `embed` tags used by previous versions.

This change means generally better support for newer formats on current desktop and mobile browsers (for example, fixing a bug where audio files would improperly auto-play on Chrome), but worse support for older video formats, particularly those that rely on browser plugins like Quicktime, Windows Media Player or VLC. Site visitors will still be able to download those older videos and view them locally, provided they have a video player installed that’s capable of playing them.

-   Added embedded audio support for .m4a and .opus
-   Added embedded video support for .m4v and .webm
-   Removed embedded audio support for .mid, .midi, .kar, .rmi and .wma
-   Removed embedded video support for .avi, .mpeg, .mpg, .mpe, .m1v, .m2v, .qt, and .wmv

For more information about HTML 5 media support in Omeka, see [Media Files](Media_Files "wikilink").

Bugs Fixed
----------

-   Installation could fail on servers running newer versions of MySQL (5.7+) ([\#678](https://github.com/omeka/Omeka/issues/678))
-   Counting tags could become extremely slow on installations with many tags and tagged records ([\#674](https://github.com/omeka/Omeka/issues/674))
-   New version detection could sometimes throw an uncaught exception when failing to connect
-   Items would not filter correctly using an Item Type object
-   Some old “cellspacing” and “cellpadding” attributes were used instead of their CSS counterparts
-   An exception within the Navigation component was not properly thrown, leading to an error
-   The default files/show view had a mismatched closing div tag

Localization
------------

-   Pluralized strings are now supported
-   New translation for Mongolian (mn)
-   Updates to many existing translations

External Libraries
------------------

Omeka 2.3 updates to the following versions of its external dependencies:

-   Zend Framework 1.12.17
-   getID3 1.9.11
-   HTML Purifier 4.7.0
-   jQuery 1.12.0
-   jQuery UI 1.11.4

Bundled Add-ons
---------------

### Plugins

-   Exhibit Builder 3.3
    -   Users can now manually select a “cover image” to serve as the thumbnail for an Exhibit
    -   Added a new File-only block layout that allows files to be centered on the page
    -   Fixed problems with dialog box placement
    -   Fixed an issue with API Import
    -   Improves compatibility with MySQL 5.7+
    -   Updated translations
-   Simple Pages 3.0.7
    -   Improved compatibility with MySQL 5.7+
    -   Updated translations

### Themes

-   Thanks, Roy 2.3.2
-   Seasons 2.3.1
-   Berlin 2.3.1

For Developers
--------------

For change information geared toward developers, see [What's New in Omeka 2.4](http://omeka.readthedocs.org/en/latest/whatsnew/2.4.html) on Omeka’s Read the Docs site.

Acknowledgements
----------------

The following members of the Omeka community contributed code, fixes, and improvements to Omeka 2.4:

-   Julian Maurice ([\#665](https://github.com/omeka/Omeka/pull/665))
-   Daniel Berthereau ([\#680](https://github.com/omeka/Omeka/pull/680))
-   Will Simpson and Ginger Tidwell ([Exhibit Builder \#80](https://github.com/omeka/plugin-ExhibitBuilder/pull/80))

