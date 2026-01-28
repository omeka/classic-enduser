# Accessibility Statement

The Omeka team is committed to making Omeka Classic an accessible option for sharing collections and exhibits online. We are working to make Omeka Classic’s core code accessible, and will continue to make accessibility for persons with disabilities a priority. Omeka strives to adhere to [W3C web design standards](http://www.w3.org/standards/){target=_blank} and to be compliant with [Section 508](http://www.section508.gov/){target=_blank} of the Rehabilitation Act.

For more information, please review the following reports:

- Omeka Classic version 3.2 [Accessibility Conformance Report, using VPAT 2.5 Revised (PDF)](../doc_files/OmekaClassicVPATDecember2025-admin.pdf){target=_blank}, December 2025.
- Omeka Classic version 2.3.1 [Accessibility Conformance Report, using VPAT 1.3 (PDF)](../doc_files/VPAT_Omeka2015.pdf){target=_blank}, September 2015.

We have separate VPATs for Omeka.net available within the [Omeka.net Accessibility Statement](http://info.omeka.net/signup/accessibility/){target=_blank}.

The following statements apply to Omeka Classic versions 2.3 and higher:

Front End (Public view)
---------------------------------------------------------------
The public view of Omeka Classic has the following features to improve accessibility:

-   [ARIA](http://www.w3.org/WAI/intro/aria){target=_blank} (Accessible Rich Internet Applications) landmarks for tabbing through page content, when not using a mouse or using a screen reader;
-   Ability to skip the navigation menu (SkipNav) and go straight to the page content when using a keyboard or screen reader to navigate the site (in all Omeka-produced themes);
-   Semantic HTML5 markup.

These features are included in the core code as well as the plugins and themes that come bundled with Omeka Classic for download (plugins being Exhibit Builder, Coins, Simple Pages; themes being Thanks Roy, Berlin, Seasons).

There are also SkipNav and ARIA landmarks on [all Omeka Classic themes](https://omeka.org/classic/themes/){target=_blank} produced by the Omeka team that do not come bundled with the download of Omeka Classic from Omeka.org.

Please note that although the core code for Omeka Classic and its bundled themes and plugins conform to the above standards, sites built with Omeka Classic which have been customized or which are using non-Omeka themes and plugins may lack some or all of these options. While we encourage developers to consider accessibility, we cannot ensure that their code includes ARIA landmarks and SkipNav in the themes.

Back End (Administrative view)
----------------------------------------------------------
The administrative dashboard of Omeka Classic has the following features for accessibility:

-   Ability to skip navigation menu and go straight to content when using a keyboard or screen reader to navigate the site. If you do not SkipNav, the sequence is: settings (top navigation bar), plugins (left navigation bar), content;
-   ARIA landmarks for screen readers on the Admin Dashboard, designating the header, navigation, footer, and main body content;
-   Semantic HTML5 markup.

## Accessibility Issues

If you encounter an issue with accessiblity with the Omeka Classic core software or Omeka Team developed addons, please report your findings either via a [Forum post](https://forum.omeka.org/c/omeka-classic/accessibility/37) or by making an issue in the appropriate Github repository.
