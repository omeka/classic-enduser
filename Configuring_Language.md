Configuring Language
====================


Available languages and codes
---------------------------------------------------------------

Below are listed the languages in which Omeka is available, along with the two or four letter codes that you will need to configure Omeka to use your language.

### Omeka 2.3.1

A translation is considered "Complete" at 100%. Languages listed as "Nearly Complete" are between 90 and 99% translated.

The statuses listed in the table are for the core Omeka code; coverage varies for plugins. To help translate Omeka, sign up for an account at [Transifex](https://www.transifex.com) and join our project (an account is required to view progress or contribute).

Language | Code | Status
---|---|---
Albanian (Albania)| `sq_AL` |Partial
Arabic | `ar` | Partial
Bengali (Bangladesh)| `bn_BD` | Partial
Bulgarian (Bulgaria)| `bg_BG` | Complete
Catalan (Spain)| `ca_ES` | Complete
Chinese (China)| `zh_CN` | Nearly Complete
Chinese (Taiwan)| `zn_TW` |Nearly Complete
Croatian | `hr` | Nearly Complete
Czech | `cs` | Nearly Complete
Danish (Denmark) | `da_DK` | Partial
Dutch (Belgium) | `nl_BE` | Nearly Complete
Dutch (Netherlands) | `nl_NL` | Nearly Complete
Estonian | `et` | Complete
Finnish (Finland) | `fi_FI` | Complete
French | `fr` | Complete
Galician | `gl` | Partial
German (Germany) | `de_DE` | Complete
Greek (Greece) | `el_GR` | Nearly Complete
Hebrew | `he` | Nearly Complete
Hungarian (Hungary) | `hu_HU` | Partial
Icelandic | `is` | Partial
Indonesian | `id` | Partial
Inuktitut | `iu` | Partial
Italian | `it` | Partial
Japanese | `ja` | Partial
Korean (Korea) | `ko_KR` | Partial
Latvian (Latvia) | `lv_LV` | Partial
Lithuanian | `lt` | Partial
Macedonian (Macedonia) | `mk_MK` | Partial
Malay (Malaysia) | `ms_MY` | Partial
Norwegian Bokmal | `nb` | Nearly Complete
Polish | `pl` | Partial
Portuguese (Brazil) | `pt_BR` | Complete
Portuguese (Portugal) | `pt_PT` | Complete
Romanian | `ro` | Complete
Russian | `ru` | Nearly Complete
Serbian (Serbia) | `sr_RS` | Complete
Slovenian (Slovenia) | `sl_Sl` | Partial
Spanish | `es` | Complete
Spanish (Colombia) | `es_CO` | Nearly Complete
Swedish (Sweden) | `sv_SE` | Partial
Tamil | `ta` | Partial
Thai | `th` | Partial
Turkish (Turkey) | `tr_TR` | Nearly Complete
Ukrainian | uk | Partial
Uzbek (Latin) | `uz@Ltn` | Partial
Welsh (United Kingdom) | `cy_GB` | Nearly Complete


Installations of Omeka 1.5 or higher
----------------------------------------------------------
-   Open the config.ini file found in the folder '{omeka-root}/application/config' in a text editor
-   Look for the "Localization" section (it's right at the top), and the line in it that reads `locale = ""`
-   Fill in the two or four letter code for the language you wish to use (see the list above). It is case-sensitive and must match one of the codes *exactly*.

Omeka 1.4.x or lower 
---------------------------------------------------------------
The config files before Omeka 1.5 do not contain the "Localization" section discussed above. You will therefore need to either copy over the new config file shipped with Omeka 1.5 or, if you have made changes to your config.ini file, just copy-and-paste the section from the new config file to your current one.
