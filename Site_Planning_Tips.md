Site Planning Tips
==================

Before you start building an Omeka site, it is useful to sketch out wireframes of your new site to help to plan the content of your site, and to determine how you want your audiences to access and use that content in the website.

Planning for the content first will help you think about the ways that Omeka can work best for you throughout different stages of the project. 

Questions to Ask While Planning
---------------------------------------------------------------
These questions will help with those planning steps.

**What are the primary goals of the website?**

**Who is the primary audience of this website**? Secondary audiences? What do you want these specific audiences to accomplish when they come to the site?

**What sections will this website include**? 
Typical top level navigation and sections for a typical Omeka site include:
  - [Items](link): (renamed however you would like Archive/Sources/Objects) links to a browseable list of items, sortable by type of item and tags.
  - [Collections](link) (renamed however you would like): groups of items, public can dig through collection to find items.
  - [Exhibits](link) (renamed however you would like): Exhibits contain interpretative text and rely on items/sources/objects as their building blocks.
  - About: a [simple page](link) good for publishing project descriptions, credits, rights, et al
  - Keyword Search box –option to link to advanced search page

**What will I do with items in this website?**
The item is the building block of your site. First add the objects and materials you want to display in your site. Add [descriptions](https://omeka.org/codex/Describing_Items "Describing Items") using some or all of the 20 standard Dublin Core fields, plus additional item type-specific fields. Once you have items in the Omeka archive, then you can build an exhibit with them or display categories of items organized by collections or tags.
- Determine the types of items/sources/objects you plan to use in this site: (ie, Document, Still Image, Moving Image, Audio, et al),
- Do you want to modify any of the item type fields or types? See [Managing Item Types](link) for additional types and explanations.
- Do you need additional core fields? Install the [Dublin Core Extended](link) plugin.
- It is wise to determine before you start building the item archive what type of consistencies you desire in your metadata--this may be especially true for fields such as date, publisher, creator, et al.
- Would you like to establish your own Controlled Vocabulary for specific metadata fields, to make it easier for you team to enter consistent data? Install the [Simple Vocab](link) plugin.
- Do you need Library of Congress subject headings? Install [Library of Congress Subject Headings](link) plugin.
- Do you want to establish a controlled tagging schema? You may [add tags](Managing_Tags_2.0.md) to individual items and exhibits. Before building your archive you may want to devise this schema to help control vocab and spelling. Tags can help you pull together different items for the purpose of arranging them on a map or creating navigational links to browse items with a specific tag.
- Do you have materials in other databases or repositories? You may be able to batch add them into your Omeka site. Can items be exported in a Comma Separated Value format? Try the [CSV Import](Plugins/CSV_Import_2.0.md) plugin.
- Is there an OAI-PMH harvestable set? Try the [OAI-PMH Harvester](Plugins/OaipmhHarvester_2.0.md) plugin.
- Do you have hundreds of files, or large media files? Use the [Dropbox](Plugins/Dropbox_2.0.md) plugin.
- Do you want to display items on a map? Install the [Geolocation](Plugins/Geolocation_2.0.md) plugin, you must geolocate each item individually.
- Are you interested in collecting materials from your visitors through a web form, such as a story or textual reflection, photos, videos, et al. Install the [Contribution](Plugins/Contribution_2.0.md) plugin to facilitate collecting.
- Do you want to build an exhibit with your items? Install the [Exhibit Builder](Plugins/ExhibitBuilder_3.0.md) plugin.

**Decisions for Displaying Items**
- Do you want to add social bookmarking icons to the bottom of
items/show to allow users to share links to that item w/their social networks? Install the [Social Bookmarking](Plugins/SocialBookmarking_2.0.md) plugin.
- Do you want to open commenting on items (only available at item    level, and for all items or none)? Install the [Commenting](Plugins/Commenting_2.0.md) plugin.
-   Do you want to create and print QR Codes that link visitors in a physical place to individual items in your Omeka site? Install the [Bar Code and Reports](Plugins/Reports_2.0.md) plugin.
-   Do you have documents that you wish users to read through on the screen rather than downloading them? Install the [DocsViewer](Plugins/DocsViewer_2.0.md) plugin.

Plan an Exhibit 
------------------------------------------------------------

The exhibit builder is not necessarily only for building museum-like exhibits, as shown by the examples above. This function can be used to publish essays or teaching materials that draw upon the items in your archive.

Before you build an exhibit, it is easier to sketch out a storyboard or outline that spells out the sections, pages, and items for each page.

Each exhibit is comprised of sections that contains pages.

Each page can contain a selection of items and some narrative text, or captions.

Follow instructions for using the [Exhibit Builder](Plugins/ExhibitBuilder_3.0.md) plugin.

Create Simple Web Pages
---------------------

You may wish to use the [Simple Pages](Plugins/SimplePages_2.0.md) plugin to create simple web pages for publishing an essay or to create an About or Credits page, or use it to link out to Teacher Resources.

Any of those pages can become part of the main navigation for your website.

A Simple Page does not require items or require programming knowledge to build, but optionally allows users to add HTML markup, PHP code, or embeds from multimedia web objects.
