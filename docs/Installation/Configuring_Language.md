# Configuring Language

Open the `config.ini` file found in the folder `{omeka-root}/application/config` in a text editor.

Look for the "Localization" section (at the top), and the line in it that reads: 

```
locale.name = "" 
```

Fill in the two- or four-letter code for the language you wish to use (see below). This information is case-sensitive and must match exactly. For example, to change the Omeka Classic interface language to Brazilian Portuguese, the line should appear:

```
locale.name = "pt_BR"
```

Omeka Classic is [translated](../Technical/Translate_Omeka.md) collaboratively using [Transifex](https://www.transifex.com){target=_blank}. You can see the progress of available languages by visiting the [Omeka project dashboard on Transifex](https://www.transifex.com/omeka/omeka/){target=_blank}; the list displays with the most complete languages at the top. Where a language string has not been translated, it will default back to English in the interface.

## Available languages and codes 
Below are the languages in which Omeka is available (for at least 5% of the interface), along with the two- or four-letter codes that you will need to configure Omeka to use your chosen language.

*Last updated: May 17th, 2022.*

Language | Code
---|---
Albanian (Albania) | `sq_AL` 
Arabic | `ar` 
Basque | `eu` 
Belarusian (Belarus) | `be_BY`
Bengali (Bangladesh) | `bn_BD` 
Bulgarian (Bulgaria) | `bg_BG` 
Catalan (Spain) | `ca_ES` 
Chinese (China) | `zh_CN` 
Chinese (Taiwan) | `zn_TW` 
Croatian | `hr` 
Czech | `cs` 
Danish (Denmark) | `da_DK`
Dutch (Belgium) | `nl_BE` 
Dutch (Netherlands) | `nl_NL`
Esperanto | `eo`
Estonian | `et` 
Finnish (Finland) | `fi_FI`
French | `fr` 
Galician | `gl` 
Georgian | `ka`
German (Germany) | `de_DE` 
Greek (Greece) | `el_GR`
Hebrew | `he` 
Hungarian (Hungary) | `hu_HU` 
Icelandic | `is` 
Indonesian | `id` 
Italian | `it` 
Japanese | `ja`
Korean (Korea) | `ko_KR`
Latvian (Latvia) | `lv_LV` 
Lithuanian | `lt`
Macedonian (Macedonia) | `mk_MK`
Malay (Malaysia) | `ms_MY` 
Mongolian | `mn` 
Norwegian Bokmål | `nb` 
Occitan (post 1500) | `oc` 
Polish | `pl`
Portuguese (Brazil) | `pt_BR` 
Portuguese (Portugal) | `pt_PT` 
Romanian | `ro` 
Russian | `ru`
Serbian (Serbia) | `sr_RS` 
Slovak | `sk`
Slovenian (Slovenia) | `sl_Sl` 
Spanish | `es` 
Spanish (Colombia) | `es_CO` 
Swedish (Sweden) | `sv_SE` 
Tamil | `ta` 
Thai | `th` 
Turkish (Turkey) | `tr_TR`
Ukrainian | `uk`
Vietnamese | `vi`
Welsh (United Kingdom) | `cy_GB` 
