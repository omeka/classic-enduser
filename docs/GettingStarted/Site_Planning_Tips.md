# Site Planning Tips

Before you start building an Omeka Classic site, it is useful to view sites from our [showcase](https://omeka.org/classic/showcase/){target=_blank} and [site directory](https://omeka.org/classic/directory/){target=_blank}. Then think about the way Omeka manages [items](../Content/Items.md), [collections](../Content/Collections.md), and [files](../Content/Files.md) to help plan the content of your site, and to determine how you want your audiences to access and use that content.

Questions to ask while planning
---------------------------------------------------------------

**What are the goals of the website?**

**Who is the primary audience of this website? Secondary audiences?** 

What do you want these specific audiences to accomplish when they come to the site?

**What sections will this website include?** 

Typical top-level navigation menus for an Omeka Classic site might include:  

  - [Items](../Content/Items.md): links to a browseable list of items, and an option to browse by tags.
  - [Collections](../Content/Collections.md): groups of items; the public can browse your collections to discover related items.
  - [Exhibits](../Plugins/ExhibitBuilder.md): series of pages that contain interpretive text and rely on items/sources/objects as their building blocks.
  - About: a [simple page](../Plugins/SimplePages.md) sharing information about the project: description, credits, rights, etc.
  - [Search bar](../GettingStarted/Searching.md#basic-search): a quick tool for searching the site's content, with an option to link to an [advanced search](../GettingStarted/Searching.md#advanced-search) page.

Plugins that you install can automatically add further pages to your site's navigation menu (such as a "Contribute" page from the Contribution plugin, or a "Timeline" page from the Timeline plugin). You can also add custom links, such as to your organizational website. 

But the menu's options and suggestions are entirely up to you. You can add links directly to specific items, collection, or exhibits; you can add browsing access points such as links to each Item Type; you can write and include any number of pages. 

![A front page of an Omeka Classic installation, with a navigation bar that includes "Biographies", "Oral History Interviews", "Stories", "Archive", "About", and "Credits". The homepage displays a slideshow of images, with links to exhibits, and a paragraph of introductory text.](../doc_files/sitePlanning.png)

**What will I do with items in this website?**

The item is the building block of your site. Items can be photographs, videos, audio clips, newspaper issues (or titles, or articles, or pages), maps, books (or series, or pages), artifacts, quotes, people, events, locations, and other types of data - whatever you need to build your collection. One item can have many media files attached, or only one file, or no file at all. You can group items into a [collection](../Content/Collections.md); you can create a hierarchy of collections using [Collection Tree](../Plugins/CollectionTree.md).

- Determine the **types** of items/sources/objects you plan to use in this site: Document, Still Image, Moving Image, Audio, the [other pre-defined item types in Omeka](../Content/Item_Types.md#pre-defined-item-types), or something custom to your collection, such as people or places. An item can be anything that needs description through metadata fields, or anything you wish to attach media to.
- Do you want to modify any of the **item types** or the item-type-specific **metadata fields**? See [Managing Item Types](../Content/Item_Types.md) to learn more.
- Describe your objects using some or all of the 20 standard [Dublin Core](../Content/Working_with_Dublin_Core.md) fields, plus additional item-type-specific fields. 
- Do you need additional Dublin Core fields? Install the [Dublin Core Extended](../Plugins/DublinCoreExtended.md) plugin.
- Determine, before you start building your collection of items, what **consistencies** you need in your metadata - this may be true for fields such as date formatting, publisher or creator names, etc. 
	* Do you want to use Library of Congress subject headings as a [controlled vocabulary](https://en.wikipedia.org/wiki/Controlled_vocabulary){target=_blank}? Install the [Library of Congress Subject Headings](../Plugins/Library_of_Congress_Suggest.md) plugin. 
	* Would you like to establish your own **controlled vocabularies** for specific metadata fields, to make it easier for your team to enter consistent data? Install the [Simple Vocab](../Plugins/SimpleVocab.md) plugin.
- You can add **tags** to individual items and exhibits. Do you want to establish a controlled tagging schema? Before building your collections, devise this schema to help control vocabularies and spelling. [Tags](../Content/Tags.md) can help you pull together different items, for purposes such as arranging them on a **map** or displaying them on a **timeline**, or allowing users to browse items with a specific tag.
- Do you have all your metadata ready in a spreadsheet? Bulk-import all the items you need with the [CSV Import](../Plugins/CSV_Import.md) plugin.

Add the objects and materials you want to share. Once you have items in your Omeka Classic database, then you can build an exhibit with them or display categories of items organized by collections or tags.

- Do you have materials in other databases or repositories? You may be able to **import** them in bulk into your Omeka Classic site. 
	* Can items be exported in a Comma Separated Value format? Try the [CSV Import](../Plugins/CSV_Import.md) plugin.
	* Is there an [OAI-PMH](https://www.openarchives.org/pmh/){target=_blank} harvestable set online? Try the [OAI-PMH Harvester](../Plugins/OaipmhHarvester.md) plugin.
	* Do you have hundreds of files, or large media files? Use the [Dropbox](../Plugins/Dropbox.md) plugin to import files from another place online rather than uploading from your computer.
- Are you interested in **collecting materials from your visitors** through a web form, including stories, photos, or videos? Install the [Contribution](../Plugins/Contribution.md) plugin.

**How do you want items to display?**

- Do you want to add **social bookmarking** icons to the bottom of item pages, to make it easier for users to share items with their social networks? Install the [Social Bookmarking](../Plugins/SocialBookmarking.md) plugin.
- Do you want to display a **map** showing the location information of each item? Install the [Geolocation](../Plugins/Geolocation.md) plugin, then add geolocation metadata to each item.
- Do you want to allow users to leave **comments** on items? Install the [Commenting](../Plugins/Commenting.md) plugin.
- Do you have documents that you wish users to **read on-screen** rather than downloading them? Install the [DocsViewer](../Plugins/DocsViewer.md) plugin or the.

**How do you want site visitors to access your items?**

Omeka Classic is modular and customizable, which means you can use its tools and features in many useful combinations.

- Each item can have one type (often Image, Sound, Video, etc.) that allow visitors to browse through those access points. You can create your own item types to categorize and divide your items any way you want. You can add those types to your navigation menu (URLs in the form `yoursite/items/browse?type=123`) to allow easier access. 
- Each item can be in one collection. Collections can be created around any concept you want - a collection for each exhibit, chronological collections by a date range (1700-1800, 1800-1900, etc.), collections based around creators or donors. The "Browse Collections" page is automatically added to your site navigation, but you can also include direct links to each collection if you wish (URLs in the form `yoursite/collections/show/123`). 
	- Collections can also be arranged into a tree using the Collection Tree plugin. Then users can browse a top-level collection and see all of the items contained in its lower-level collections. This gives you organizational options past the limitation of one collection per item. 
- Items can have an infinite number of tags, which you can use to provide subject headings, date ranges, or other grouping tools. "Browse by tag" is a link that appears on the "Browse Items" page by default, but you can also add this to your navigation (`yoursite/items/tags`). Or you can share links to specific tags directly, in the text on your homepage or in exhibits (URLs in the form `yoursite/items/browse?tags=europe`).
- Items can often have the same metadata values (such as one person listed as the Creator for many items). 
	- Using the [Search by Metadata](../Plugins/SearchByMetadata.md) plugin, you can turn certain metadata fields (such as Creator or Publisher) into clickable links that will take users to a search-results page including all items that match that (for example, all the items with "Shakespeare, William" as the text value in the Creator field). This can provide another access point, incorporated into your descriptive metadata, alongside tags, classes, and collections. And you can use those URLs in your navigation bar or in your page text, too. 
	- If these values (such as people) require describing (such as with biographical information), you can use items for this purpose (items with a "Person" item type, for example). Install the [Item Relations](../Plugins/ItemRelations.md) plugin to fill out a field (such as Creator) with a link to another item (such as your "William Shakespeare" item).
- With the Timeline and Geolocation plugins, you can add interactive tools that allow browsing by item dates or coordinates. These require precise formatting of your metadata but are easy to set up. These plugins also add pages to your site menu automatically, which can be removed or modified in the Navigation options.
- Searching on your Omeka site brings up text results from the item and collection metadata you have provided, and can also include full-text-searching inside PDFs and other text documents attached as files. Consider installing the [PDF Text](../Plugins/PdfText.md) plugin and indexing the contents of your PDFs.
- With Simple Pages, you can manually create a page including links to any number of the options above. This can include a "Searching Tips" or "Research Guide" page with information about how you have structured your Omeka installation, and offer examples of how to browse and search the collection. 

Plan an exhibit 
------------------------------------------------------------

The [Exhibit Builder](../Plugins/ExhibitBuilder.md) plugin is not only for building museum-like exhibits. This function can be used to publish essays or teaching materials that draw upon the items in your archive. Note that the Exhibit Builder plugin comes packaged with the basic installation of Omeka Classic. 

Before you build an exhibit, sketch out a storyboard or outline that spells out the sections, pages, and items for each page.

Each exhibit can have multiple sections, which can contain multiple pages. Each page can contain a selection of items, and can be contextualized with some narrative text or captions.

Learn more in the instructions for using the [Exhibit Builder](../Plugins/ExhibitBuilder.md) plugin.

Digital exhibit publishing is a popular class assignment for students, or a way for users and volunteers to contribute to your institution. Learn more about [creating different users and giving them permissions](../Admin/Users.md) to build things on your Omeka Classic installation.

It's also common to create a digital companion exhibit to a physical exhibit in your space. Digital exhibits can expand upon and complement your displays of artifacts. Do you want to print QR codes that will link exhibit visitors to individual items in your Omeka Classic site? Install the [Reports](../Plugins/Reports.md) plugin.

Create webpages
---------------------

You can use the [Simple Pages](../Plugins/SimplePages.md) plugin to create web pages for publishing press releases, to add an About or Credits page, to share copyright or access statements, or to build a general web presence for your organization. Any of those pages can become part of the main navigation for your website. Note that the Simple Pages plugin comes packaged with the basic installation of Omeka Classic. 

A Simple Page does not require items or programming knowledge to build, but users can add HTML markup, PHP code, or embedded multimedia objects.

Try Omeka Classic before installing
---

If you would like to try Omeka Classic before installing on your own server, consider signing up for a free trial account at
[Omeka.net](http://www.omeka.net/){target=_blank}. [Sign up here](https://www.omeka.net/signup){target=_blank}.

[Omeka.net](http://www.omeka.net/){target=_blank} is our Omeka Classic hosting service that allows anyone with an account to create or collaborate on a website to display collections and build digital exhibitions. With a [free trial account](https://info.omeka.net/signup/){target=_blank}, you can experience Omeka Classic’s administrative dashboard and try out 8 of the most popular plugins, including Exhibit Builder and Simple Pages.

For a comparison of the features of a hosted account at [Omeka.net](http://www.omeka.net/){target=_blank} and an installation on your own servers, see the [Omeka.net About page](http://info.omeka.net/about/).