Managing Search Settings 2.0
============================

Overview 
---------------------------------------------------------

New to Omeka 2.0 is a Settings section dedicated to search
functionality. It's important to note that the new site-wide search
encompasses all record types in Omeka (items, files, collections, as
well as Simple Pages and Exhibit content), and can be constrained to
particular types.

### Query Types 

The search capability has expanded to include three options for admin
and public queries:

-   **Keyword**: similar to Google Search, a keyword search returns
    results ordered by relevance. Searching on "ancient warfare" will
    prioritize records that contain the full string "ancient warfare",
    but will also include records that contain the individual words
    "ancient" or "warfare".
-   **Boolean**: allows greater fine-tuning than keyword search but does
    not return results by relevance. Do this by using certain characters
    at the beginning or end of words in the search string. Some
    examples:
    -   +: a leading plus sign indicates that this word must be present
        in each row that is returned.
    -   -: a leading minus sign indicates that this word must not be
        present in any of the rows that are returned.
    -   \*: an appended asterisk serves as the truncation (or wildcard)
        operator. Words match if they begin with the word preceding
        the \* operator.
    -   ": a phrase that is enclosed within double quote characters
        matches only rows that contain the phrase literally, as it
        was typed.
    -   More special characters and further information about boolean
        search can be found [on the MySQL
        website](http://dev.mysql.com/doc/refman/5.5/en//fulltext-boolean.html).
-   **Exact match**: returns records that contain at least one match to
    the order of words entered, like "Civil War". Use this search type
    if you need to search short words, like "war", and the
    keyword/boolean searches do not produce results.

### Select Record Types

As an Omeka site Super administrator, you may choose which Omeka record
types you wish to be searchable: items, collections, files.
Additionally, if you installed the Simple Pages and Exhibit Builder
plugins you may make that content available as well. Other plugins may
make their content available for searching as well.

[![Searchsettings.png](https://omeka.org/c/images/thumb/e/e9/Searchsettings.png/500px-Searchsettings.png)](https://omeka.org/codex/File:Searchsettings.png)

Using the checkboxes found to the left of each record type, choose which
ones you want discoverable by the site-wide search. Please note that the
"Exhibit" record type includes exhibit descriptive information, and an
"Exhibit Page" is the actual content of the exhibit.

Click Save Changes.

Once records types are selected, searchers may choose from the options
you have provided them, in admin and public site-wide searches.

[![Searching.png](https://omeka.org/c/images/b/b8/Searching.png)](https://omeka.org/codex/File:Searching.png)

### Indexing 

Indexing means to collect, parse, and store data to facilitate fast and
accurate searches. Omeka will automatically index individual records as
they are created and saved. Re-indexing is necessary when updating from
an earlier version of Omeka or after you customize which records will be
searchable.

Click on the "Index Records" button to re-index your records.

Troubleshooting
-----------------------------------------------------------------------

If you are having trouble finding by search words you know are in your
install, the following may be part of the problem:

-   MySQL by default does not index any words shorter than 4
    letters long.
-   Exact match searches will look for the exact string given by the
    user, anywhere in the record. For example a search for 'poe' would
    also return 'poem'.
-   MySQL considers terms that appear in over 50% of indexed items to be
    so common that it excludes them from keyword searches. The easy way
    to tell if a term meets the the 50% threshold that's at fault is to
    choose the "boolean" search, as MySQL does not apply the 50%
    limitation to boolean searches

