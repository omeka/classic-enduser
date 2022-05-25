# Site Planning Tips

Before you start building an Omeka Classic site, it is useful to sketch out wireframes of your new site to help plan the content of your site, and to determine how you want your audiences to access and use that content on the website.

Planning for the content first will help you think about the ways that Omeka Classic can work best for you throughout different stages of the project. 

Questions to Ask While Planning
---------------------------------------------------------------
These questions will help with those planning steps.

**What are the primary goals of the website?**

**Who is the primary audience of this website? Secondary audiences?** 

What do you want these specific audiences to accomplish when they come to the site?

**What sections will this website include?** 

Typical top level navigation and sections for a typical Omeka Classic site include:  

  - [Items](../Content/Items.md): links to a browseable list of items, sortable by type of item and tags.
  - [Collections](../Content/Collections.md): groups of items, public can dig through collection to find items.
  - [Exhibits](../Plugins/ExhibitBuilder.md): Exhibits contain interpretative text and rely on items/sources/objects as their building blocks.
  - About: a [simple page](../Plugins/SimplePages.md) good for publishing project descriptions, credits, rights, etc.
  - [Search bar](../GettingStarted/Searching.md#basic-search): with an option to link to an [advanced search](../GettingStarted/Searching.md#advanced-search) page.

**What will I do with items in this website?**

The item is the building block of your site. 
First add the objects and materials you want to share. 
Add descriptions using some or all of the 20 standard [Dublin Core](../Content/Working_with_Dublin_Core.md) fields, plus additional item type-specific fields. 
Once you have items in the Omeka Classic database, then you can build an exhibit with them or display categories of items organized by collections or tags.

- Determine the types of items/sources/objects you plan to use in this site: Document, Still Image, Moving Image, Audio, the [other pre-defined item types in Omeka](../Content/Item_Types.md#pre-defined-item-types), or something custom to your collection.
- Do you want to modify any of the item types or the item-type-specific fields? See [Managing Item Types](../Content/Item_Types.md) to learn more.
- Do you need additional Dublin Core fields? Install the [Dublin Core Extended](../Plugins/DublinCoreExtended.md) plugin.
- It is wise to determine, before you start building your collection of items, what type of consistencies you desire in your metadata - this may be especially true for fields such as date, publisher, creator, etc. 
	* Do you want to use Library of Congress subject headings as a [controlled vocabulary](https://en.wikipedia.org/wiki/Controlled_vocabulary)? Install [Library of Congress Subject Headings](../Plugins/Library_of_Congress_Suggest.md) plugin. 
	* Would you like to establish your own controlled vocabularies for specific metadata fields, to make it easier for your team to enter consistent data? Install the [Simple Vocab](../Plugins/SimpleVocab.md) plugin.
- Do you want to establish a controlled tagging schema? You can [add tags](../Content/Tags.md) to individual items and exhibits. Before building your collections you may want to devise this schema to help control vocabularies and spelling. Tags can help you pull together different items, for purposes such as arranging them on a map, or allowing users to browse items with a specific tag.
- Do you have materials in other databases or repositories? You may be able to import them in bulk into your Omeka Classic site. 
	* Can items be exported in a Comma Separated Value format? Try the [CSV Import](../Plugins/CSV_Import.md) plugin.
	* Is there an OAI-PMH harvestable set? Try the [OAI-PMH Harvester](../Plugins/OaipmhHarvester.md) plugin.
	* Do you have hundreds of files, or large media files? Use the [Dropbox](../Plugins/Dropbox.md) plugin.
- Do you want to display items on a map? Install the [Geolocation](../Plugins/Geolocation.md) plugin, then add geolocation metadata to each item.
- Are you interested in collecting materials from your visitors through a web form, such as a story or textual reflection, photos, or videos? Install the [Contribution](../Plugins/Contribution.md) plugin to facilitate collecting.
- Do you want to build an exhibit with your items? Install the [Exhibit Builder](../Plugins/ExhibitBuilder.md) plugin.

**How do you want items to display?**

- Do you want to add social bookmarking icons to the bottom of items, to allow users to share links to that item with their social networks? Install the [Social Bookmarking](../Plugins/SocialBookmarking.md) plugin.
- Do you want to allow users to leave comments on items? Install the [Commenting](../Plugins/Commenting.md) plugin.
-   Do you want to create and print QR codes that link visitors in a physical place to individual items in your Omeka Classic site? Install the [Bar Code and Reports](../Plugins/Reports.md) plugin.
-   Do you have documents that you wish users to read on-screen rather than downloading them? Install the [DocsViewer](../Plugins/DocsViewer.md) plugin.

Plan an Exhibit 
------------------------------------------------------------

Exhibit Builder is not necessarily only for building museum-like exhibits. This function can be used to publish essays or teaching materials that draw upon the items in your archive.

Before you build an exhibit, sketch out a storyboard or outline that spells out the sections, pages, and items for each page.

Each exhibit can have multiple sections, which can contain multiple pages. Each page can contain a selection of items, and can be contextualized with some narrative text or captions.

Learn more in the instructions for using the [Exhibit Builder](../Plugins/ExhibitBuilder.md) plugin.

Create Simple Web Pages
---------------------

You can use the [Simple Pages](../Plugins/SimplePages.md) plugin to create web pages for publishing an essay, to add an About or Credits page, to share copyright or access statements, or to build a general web presence for your organization. Any of those pages can become part of the main navigation for your website.

A Simple Page does not require items or programming knowledge to build, but users can add HTML markup, PHP code, or embedded multimedia objects.

Try Omeka Classic Before Installing
---

If you would like to try Omeka Classic before installing on your own server, consider signing up for a free trial account at
[Omeka.net](http://www.omeka.net/){target=_blank}. [Sign up here](https://www.omeka.net/signup){target=_blank}.

[Omeka.net](http://www.omeka.net/){target=_blank} is our Omeka Classic hosting service that allows anyone with an account to create or collaborate on a website to display collections and build digital exhibitions. With a [free trial account](https://info.omeka.net/signup/){target=_blank}, you can experience Omeka Classic’s administrative dashboard and try out 8 of the most popular plugins, including Exhibit Builder and Simple Pages.

For a comparison of the features of a hosted account at [Omeka.net](http://www.omeka.net/){target=_blank} and an installation on your own servers, see the [Omeka.net About page](http://info.omeka.net/about/).
