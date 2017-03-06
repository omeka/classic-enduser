---
title: Searching
---
Omeka (versions 2.0 and higher) has site-wide search on the public and admin sides.

The interface for search options and advanced (item-only) search look similar on the Admin and Public sides of the site, but the results returned may depend on the user role (if any) of the person performing the search. For example 

For information about configuring search settings, please see the [relevant documentation](/Managing_Search_Settings_2.md)

Basic Search
-----------------
A search bar appears on both public and admin sides. 

On the public side, the search bar will always be near the navigation; depending on the theme in use, it should be either in the top area of a page or a sidebar. When viewing the public side in mobile, the search bar should show up near the menu.

![public side menu view showing search bar](/doc_files/searchPubSide)

![mobile view with search bar highlighted](/doc_files/searchMobile.png)

![search bar in admin view](/doc_files/searchAdmin.png)

To perform a basic search, type your search terms into the bar and either hit enter on your keyboard or click the magnifying glass icon.

To access options for the basic search, click the ellipsis (`...`) button in the search bar. This should open a drop-down drawer which gives you three radio button options for query type and allows you to select which record type to search.

![Search options menu](/doc_files/searchOptions.png)

### Query Types 
The query types function as follows”

- **Keyword**: similar to Google Search, a keyword search returns results ordered by relevance. Searching on for “ancient warfare” will prioritize records that contain the full string “ancient warfare”, but will also include records that contain the individual words “ancient” or “warfare”.
- **Boolean**: allows greater fine-tuning than keyword search but does not return results by relevance. Do this by using certain characters at the beginning or end of words in the search string. Some examples
    -   `+` a leading plus sign indicates that this word must be present in each row that is returned.
    -   `-` a leading minus sign indicates that this word must not be present in any of the rows that are returned.
    -   \* an appended asterisk serves as the truncation (or wildcard) operator. Words match if they begin with the word preceding the \* operator.
    -   `”`: a phrase that is enclosed within double quote characters matches only rows that contain the phrase literally, as it was typed.
    -   More special characters and further information about boolean search can be found [on the MySQL website](http://dev.mysql.com/doc/refman/5.5/en//fulltext-boolean.html).
-   **Exact match**: returns records that contain at least one match to the order of words entered, like “Civil War”. Use this search type if you need to search short words, like “war”, and the keyword/boolean searches do not produce results.

Advanced Item Search
-------------------
At the bottom of the basic search options dialog is the option for advanced search - items only. You can also access it by going to `yoursite/admin/items/search` (on the admin side) or `yoursite/items/search` (on the public side). The options are the same on the public and admin side

![advanced search options](/doc_files/searchAdminAdv.png)

With advanced search for items, you can:
- **Search for Keywords** which you can limit by the options below
- **Narrow by Specific Fields** using two drop-down menus and a text field. 
     - From the first dropdown to select an element (Title, Description). 
     - From the second dropdown, choose one of the following options: contains, does not contain, is exactly, is not exactly, is empty, is not empty, starts with, ends with, matches, does not match.
     - Fill out the text input field with the text you want to search on.
     - *Example* To exclude any items with “Tea” in the Title, you would select “Title” from the first drop down, “does not contain” from the second, and type “tea” in the text field.
     - You can stack this search by clicking the *Add a Field* button - this will add a new set of dropdown and text field.
- **Search by a range of ID Numbers** use the id numbers of an item (found in the url when viewing the item). Ranges can be formatted as “1-4” as well as a list separated with commas: “1-5,7,13”.
- **Search by Collection** by selecting an existing collection from the drop-down menu.
- **Search by Type** by selecting an existing item type ( from the drop-down menu.
- **Search by User** finds all items created by the specified user (drop-down)
- **Search by Tags** by typing the tag text in the text field. 
     - You must type the tag precisely - simply typing “ghost” would not work if the tag was “ghost story”
- **Public or Non-Public**: select from the dropdown to restrict the search to either public or not public items. 
- **Featured or Non-Featured**: select from the dropdown to restrict the search to either featured or not featured items. 
- **Search by Exhibit** (if [ExhibitBuilder](/Plugins/ExhibitBuilder_3.0.md) is installed): restrict search to one of the exhibits in your site, chosen from a dropdown menu (remembering that this is an item-only search). 
