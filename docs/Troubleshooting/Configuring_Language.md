---
title: Configuring Language
---

Available languages and codes
---------------------------------------------------------------

Below are listed the languages in which Omeka is available, along with the two or four letter codes that you will need to configure Omeka to use your language.

### Omeka 2.4
A translation is considered "Complete" at 100%. Languages listed as "Nearly Complete" are between 90 and 99% translated. Languages listed as "Started" are less then 25% complete.

The statuses listed in the table are for the core Omeka code; coverage varies for plugins. To help [translate Omeka](/Translate_Omeka.md), sign up for an account at [Transifex](https://www.transifex.com) and join our project (an account is required to view progress or contribute).

Language | Code | Status
---|---|---
Albanian (Albania)| `sq_AL` | Partial
Arabic | `ar` | Partial
Basque | `eu` | Started
Belarusian (Belarus) | `be_BY` | Nearly Complete
Bengali (Bangladesh)| `bn_BD` | Started
Bulgarian (Bulgaria)| `bg_BG` | Nearly Complete
Catalan (Spain)| `ca_ES` | Complete
Chinese (China)| `zh_CN` | Nearly Complete
Chinese (Taiwan)| `zn_TW` |Nearly Complete
Croatian | `hr` | Nearly Complete
Czech | `cs` | Nearly Complete
Danish (Denmark) | `da_DK` | Partial
Dutch (Belgium) | `nl_BE` | Nearly Complete
Dutch (Netherlands) | `nl_NL` | Nearly Complete
Estonian | `et` | Nearly Complete
Finnish (Finland) | `fi_FI` | Nearly Complete
French | `fr` | Complete
Galician | `gl` | Partial
German (Germany) | `de_DE` | Complete
Greek (Greece) | `el_GR` | Nearly Complete
Hebrew | `he` | Nearly Complete
Hungarian (Hungary) | `hu_HU` | Partial
Icelandic | `is` | Partial
Indonesian | `id` | Nearly Complete
Inuktitut | `iu` | Started
Italian | `it` | Nearly Complete
Japanese | `ja` | Partial
Korean (Korea) | `ko_KR` | Nearly Complete
Latvian (Latvia) | `lv_LV` | Partial
Lithuanian | `lt` | Partial
Macedonian (Macedonia) | `mk_MK` | Partial
Malay (Malaysia) | `ms_MY` | Started
Mongolian | `mn` | Complete
Norwegian Bokmal | `nb` | Nearly Complete
Occitan (post 1500) | `oc` | Complete
Polish | `pl` | Nearly Complete
Portuguese (Brazil) | `pt_BR` | Complete
Portuguese (Portugal) | `pt_PT` | Complete
Romanian | `ro` | Nearly Complete
Russian | `ru` | Nearly Complete
Serbian (Serbia) | `sr_RS` | Complete
Slovenian (Slovenia) | `sl_Sl` | Started
Spanish | `es` | Complete
Spanish (Colombia) | `es_CO` | Nearly Complete
Swedish (Sweden) | `sv_SE` | Complete
Tamil | `ta` | Started
Thai | `th` | Partial
Turkish (Turkey) | `tr_TR` | Nearly Complete
Ukrainian | uk | Partial
Uzbek (Latin) | `uz@Ltn` | Started
Welsh (United Kingdom) | `cy_GB` | Nearly Complete


Installations of Omeka 1.5 or higher
----------------------------------------------------------
-   Open the config.ini file found in the folder '{omeka-root}/application/config' in a text editor
-   Look for the "Localization" section (it's right at the top), and the line in it that reads `locale = ""`
-   Fill in the two or four letter code for the language you wish to use (see the list above). It is case-sensitive and must match one of the codes *exactly*.

Omeka 1.4.x or lower 
---------------------------------------------------------------
The config files before Omeka 1.5 do not contain the "Localization" section discussed above. You will therefore need to either copy over the new config file shipped with Omeka 1.5 or, if you have made changes to your config.ini file, just copy-and-paste the section from the new config file to your current one.
