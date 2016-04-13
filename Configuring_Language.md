Configuring Language
====================


Available languages and codes
--------------------------------------------------------------------------------------------------

Below are listed the languages in which Omeka is available, along with the two or four letter codes that you will need to configure Omeka to use your language.

### Omeka 2.3.1

A translation is considered "Complete" at 100%. Languages listed as "Nearly Complete" are between 90 and 99% translated.

The statuses listed in the table are for the core Omeka code; coverage varies for plugins. To help translate Omeka, sign up for an account at [Transifex](https://www.transifex.com) and join our project (an account is required to view progress or contribute).

Language
Code
Status
Albanian (Albania)
sq\_AL
Partial
Arabic
ar
Partial
Bengali (Bangladesh)
bn\_BD
Partial
Bulgarian (Bulgaria)
bg\_BG
Complete
Catalan (Spain)
ca\_ES
Complete
Chinese (China)
zh\_CN
Nearly Complete
Chinese (Taiwan)
zn\_TW
Nearly Complete
Croatian
hr
Nearly Complete
Czech
cs
Nearly Complete
Danish (Denmark)
da\_DK
Partial
Dutch (Belgium)
nl\_BE
Nearly Complete
Dutch (Netherlands)
nl\_NL
Nearly Complete
Estonian
et
Complete
Finnish (Finland)
fi\_FI
Complete
French
fr
Complete
Galician
gl
Partial
German (Germany)
de\_DE
Complete
Greek (Greece)
el\_GR
Nearly Complete
Hebrew
he
Nearly Complete
Hungarian (Hungary)
hu\_HU
Partial
Icelandic
is
Partial
Indonesian
id
Partial
Inuktitut
iu
Partial
Italian
it
Partial
Japanese
ja
Partial
Korean (Korea)
ko\_KR
Partial
Latvian (Latvia)
lv\_LV
Partial
Lithuanian
lt
Partial
Macedonian (Macedonia)
mk\_MK
Partial
Malay (Malaysia)
ms\_MY
Partial
Norwegian Bokmal
nb
Nearly Complete
Polish
pl
Partial
Portuguese (Brazil)
pt\_BR
Complete
Portuguese (Portugal)
pt\_PT
Complete
Romanian
ro
Complete
Russian
ru
Nearly Complete
Serbian (Serbia)
sr\_RS
Complete
Slovenian (Slovenia)
sl\_Sl
Partial
Spanish
es
Complete
Spanish (Colombia)
es\_CO
Nearly Complete
Swedish (Sweden)
sv\_SE
Partial
Tamil
ta
Partial
Thai
th
Partial
Turkish (Turkey)
tr\_TR
Nearly Complete
Ukrainian
uk
Partial
Uzbek (Latin)
uz@Ltn
Partial
Welsh (United Kingdom)
cy\_GB
Nearly Complete

New Installations of Omeka 1.5 or higher
-------------------------------------------------------------------------------------------------------------------------

-   Open the config.ini file found in the folder
    '{omeka-root}/application/config' in a text editor
-   Look for the "Localization" section (it's right at the top), and the
    line in it that reads:

``` {.de1}
locale = ""
```  

-   Fill in the two or four letter code for the language you wish to use (see the list above). It is case-sensitive and must match one of the codes *exactly*.

Upgrading from Omeka 1.4.x or lower 
---------------------------------------------------------------------------------------------------------------

The config files before Omeka 1.5 do not contain the "Localization" section discussed above. You will therefore need to either copy over the new config file shipped with Omeka 1.5 or, if you have made changes to your config.ini file, just copy-and-paste the section from the new config file to your current one.
