Translate Omeka
===============

Beginning with the 1.5 release, Omeka added internationalization support. Among other things, Omeka allows users to select the language in which the site is displayed.

We need the community's help translating Omeka's English text into new languages, so users can have a variety of choices. You don't need to know how to write code to help translate Omeka, you just need to be fluent in English and another language.

Getting Started
--------------------------------------------------------

### <span id="Sign_up_on_Transifex.net" class="mw-headline"> Sign up on Transifex.net </span>

Omeka is using [Transifex.net](http://transifex.net) to manage
translations. To start helping to translate Omeka into other languages,
you will first need to [sign up for an
account](https://www.transifex.net/plans/). Transifex.net offers several
plans, but since Omeka is an open-source project, you can use the Free
plan.

### <span id="Join_or_start_a_language_team" class="mw-headline"> Join or start a language team </span>

Once you have registered for an account, visit the [Omeka project
page](https://www.transifex.net/projects/p/omeka) and click on the
"Teams" tab. This will show you the teams working on translations of
Omeka into different languages.

[![Transifex-teams.png](https://omeka.org/c/images/1/1f/Transifex-teams.png)](https://omeka.org/codex/File:Transifex-teams.png)

Here, you have two options. If you want to start work on a translation
into a language which is not already being worked on, click the "Request
a new team" button, and select the language that you want to work on.
Once that request is approved, you will be the coordinator for that
language.

On the other hand, if someone has already created a team for the
language you want to work on, click the name of the language, and on the
next screen click the "Join this Team" button. It will be up to the
coordinator to approve your request to be a member of the team.

Once a coordinator has approved you to the team, you can click on the
"Omeka → core" link and begin translating.

[![Transifex-teams2.png](https://omeka.org/c/images/5/5e/Transifex-teams2.png)](https://omeka.org/codex/File:Transifex-teams2.png)

If you want to check your translation or anything else you need to make
an mo file from your po file, you can do it with msgfmt from the [GNU
gettext package](http://www.gnu.org/software/gettext/).

<span id="Translation_Guidelines" class="mw-headline"> Translation Guidelines </span>
-------------------------------------------------------------------------------------

Most of the strings to be translated in Omeka are straightforward and
can be translated directly. However, there are a few special cases that
need to be treated with care.

### <span id="Placeholders" class="mw-headline"> Placeholders </span>

Some strings contain text that looks like `%s` or `%1$s`. These
odd-looking bits of text are called **placeholders**. Placeholders are
used to allow Omeka to insert some changing piece of information, like
the number of items in an Omeka site, into a translated string.

If a source string contains placeholders, you must include them in your
translation. You can move the placeholders around within the string, and
even change the order of numbered placeholders in the string, but all
the placeholders from the source string must appear in the translation.

### <span id="HTML_and_URLs" class="mw-headline"> HTML and URLs </span>

A few strings contain embedded HTML code or URLs. You can translate and
change the plain English text in these strings, but you should preserve
any HTML tags or URLs.