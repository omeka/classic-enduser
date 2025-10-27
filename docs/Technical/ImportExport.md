# Importing and exporting

There are several methods for importing to, or exporting from, an Omeka Classic site. Third-party plugins may add more functionality; we are only documenting Omeka-team-supported methods here. 

## Connect to another Omeka site

You cannot currently export from an Omeka S installation to a Classic site. 

### Import from Classic to Classic

You can use the [Omeka API Import plugin](../Plugins/Omeka_API_Import.md) to import items & collections from a Classic site. This plugin imports some of the material accessible from the [API](../Admin/Settings/API_Settings.md): items and their metadata (including tags), attached files, collections, users, comments and contributions, Simple Pages, and Exhibit Builder content. 

If equivalent plugins are installed on both the source site and the target site, Omeka API Import can import plugin-specific metadata. For example, geolocation data facilitated by the [Geolocation plugin](../Plugins/Geolocation.md) will automatically be imported; [PDF Text](../Plugins/PdfText.md) elements can be imported.

An API key is required to access private installation data, such as users and their profiles, and private items and collections. 

This plugin will *not* import all possible data accessible by the API (see the next section). For example, some plugins may generate data accessible by the API as output but not be able to import that same data to your new installation. We recommend you generate a dataset using the API to capture all possible information.

The instructions on [how to move your Omeka Classic site from one server to another](Moving_to_Another_Server.md) may be of use. 

### Access data using the API

You can use your own Classic site's API to crawl data as required, or export a spreadsheet. You can [request different formats through the API](https://omeka.org/s/docs/developer/api/rest_api/#responses){target=_blank}, including `jsonld` and `rdfxml`. 

[For more information on the API, see the developer documentation section.](https://omeka.org/s/docs/developer/api/){target=_blank}.

There are example scripts for using the API to output information [in the developer documentation](https://omeka.readthedocs.io/en/latest/Reference/api/examples.html){target=_blank}.

The easiest way to confirm what can be exported is to go to your source installation and view the "API" tab in the Settings. Any content displayed in that table can be exported. Any content not displayed there cannot be accessed.

![The API table displaying all Omeka-team-authored plugin content available for access.](../doc_files/APItable.png)

Once you have exported from your original installation using the API, you can use the dataset to import information using the [CSV Import plugin](../Plugins/CSVImport.md).

### Access item data

Alongside the methods above, such as creating a dataset from the API, you can access datasets directly from the public site. Every Omeka Classic browse page, search result page, and item view page has links to output the data contained in the results set: see [this page about Output Formats](Output_Formats.md) for more information on how these formats can be used to export your collections. 

#### Copy over settings

You cannot directly import all installation settings and theme configuration, nor plugin information that can impact your installation, such as the CSS Editor. We recommend that after an import is performed, you compare both installations side-by-side to confirm that all settings match. 

#### Copy vocabularies

You cannot export or import [Simple Vocab](../Plugins/SimpleVocab.md) vocabularies at this time. 

#### Import or export plugin data

The [API](../Admin/Settings/API_Settings.md) offers data from the following (Omeka-team-authored) plugins: Simple Pages, Exhibits, Contribution, Geolocation, Comments, Item Relations, User Profiles. 

Note that this does not include Timelines, Collection Tree, Simple Vocab, the CSS Editor, Posters, and Reports, among others. 

The easiest way to confirm what can be exported is to go to your source installation and view the "API" tab in the Settings. Any content displayed in that table can be exported. Any content not displayed there cannot be accessed. 

Note that the Omeka API Import plugin does not import all content available from the API. 

![The API table displaying all Omeka-team-authored plugin content available for access.](../doc_files/APItable.png)

## Connect to non-Omeka platforms

### Omeka Classic connectors

Omeka Classic has plugins for connecting directly to:

- [Zotero](../Plugins/Zotero.md)
- any [OAI-PMH-formatted data](../Plugins/OaipmhHarvester.md).

### Import from a spreadsheet

Omeka Classic can take data in any spreadsheet (tabular) form, whether a CSV, an Excel file, or an ODS. Use the [CSV Import plugin](../Plugins/CSVImport.md) to add items and media to your Omeka Classic site from a spreadsheet. This includes data exported from many different databases and platforms. Export the data from your source platform into a spreadsheet. This may require some modification or cleanup of the data before importing into Omeka Classic. 

You cannot create collections en masse using CSV Import.  

## Back up your Omeka Classic site

### Back up your database

See the instructions on [backing up your database on this page](Backing_up_an_Omeka_Database.md).