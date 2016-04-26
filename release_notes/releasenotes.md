Release Notes for 2.1.3
=======================
Omeka 2.1.3 is the third maintenance release in the 2.1 series. It was released on December 4, 2013.

Bugs Fixed
----------- 

-   Sessions table error when upgrading from pre-1.5 versions (*[\#611](https://github.com/omeka/Omeka/issues/611)*)
-   An internal error when browsing the API under PHP 5.2 (*[\#609](https://github.com/omeka/Omeka/issues/609)*)
-   A deprecation warning on edit forms under PHP 5.5 (*[\#607](https://github.com/omeka/Omeka/issues/607)*)
-   Notices emitted for the omeka-xml and omeka-json outputs for some records (*[\#610](https://github.com/omeka/Omeka/issues/610)*)
-   Translations were not applied for background processes (*[\#608](https://github.com/omeka/Omeka/issues/608)*)
-   The users API listed parameters that could not be used (*[\#606](https://github.com/omeka/Omeka/issues/606)*)
-   Insecure content warnings when using SSL (*[\#596](https://github.com/omeka/Omeka/issues/596), contributed by misilot)*

Enhancements
--------------

-   Miscellaneous improvements to and cleanup of the admin theme CSS

Localization
------------

-   Updated translations for Finnish (`fi_FI`), French (`fr`), Polish (`pl`), Brazilian Portuguese (`pt_BR`), Romanian (`ro`) and Serbian (`sr_RS`)
-   New translation for Slovenian (`sl_SI`)

Bundled Add-ons
---------------

### Plugins

-   COinS version 2.0.2. This version resolves an issue with case-sensitivity in embedded COinS metadata.

### Themes

-   Seasons version 2.1.6. This version resolves mixed content warnings under SSL and various compatibility problems with complex embedded HTML, like maps and videos.
-   Thanks, Roy version 2.1.1. This version resolves mixed content warnings under SSL.

