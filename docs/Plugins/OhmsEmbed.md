# OHMS Embed

The [OHMS Embed plugin](https://omeka.org/classic/plugins/OhmsEmbed/){target=_blank} allows site administrators to add [Oral History Metadata Synchonizer](https://www.oralhistoryonline.org/){target=_blank} objects as files to Omeka Classic items.

This module will add an OHMS viewer to places where files can be embedded, allowing users to view indexes, transcripts, and/or translations of videos and audio as they are played. 

![A public display of an OHMS viewer in an Omeka page, with a small video above, a transcript on the left, and an index on the right.](modulesfiles/ohmsembed_public.png)

OHMS XML files can be uploaded to Omeka items as media. Without this module, they will appear as attached files available for download. With this module installed and activated, they will render as video/audio displays with transcripts, indexes, etc. 

The OHMS media player can appear on item and files pages, and can be placed on Omeka exhibit pages by adding the item to a selected page block.

Preparing your Omeka installation to receive OHMS files can take some work, and includes some optional steps to enhance the process. Read over the following steps thoroughly before taking any action, so that you can set up your installation correctly based on your specific needs. 

## Create OHMS files

To create OHMS packages with your interviews, you must use the OHMS application available on the [OHMS website](https://www.oralhistoryonline.org/){target=_blank}, which requires requesting a free account and working with the web-based application. 

The OHMS application will output XML files that contain all the information created within that tool. 

OHMS files include a link to the video or audio media that will be presented alongside the index and texts. They do **not** include the multimedia file itself. This must be hosted elsewhere. Your hosting options include Youtube, Vimeo, Soundcloud, and other audio/video hosting providers.

## Configuring the Plugin

When you activate the OHMS Embed Plugin, you will have two configuration options.

1. Embed Height: Set the height of the OHMS Embed in pixels.
2. Extract Metadata: Selecting this option will set "Oral History" as the item type for items that have OHMS XML files added to them. Then, this option will extract the metadata contained in the OHMS XML file and insert it into assigned Item Metadata and Item Type Metadata fields.  Extracted metadata will be mapped as follows:
    - Dublin Core, Title
    - Dublin Core, Description
    - Dublin Core, Identifier (from "accession' in the XML)
    - Dublin Core, Date
    - Dublin Core, Subject
    - Oral History Item Type Metadata, Interviewer
    - Oral History Item Type Metadata, Interviewee
    - Oral History Item Type Metadata, Duration


## Add OHMS files to Omeka

The OHMS Editor produces an XML file that carries the metadata, index, and transcript that accompany the oral history. The file must be added to an Omeka Classic item as media to cause the OHMS viewer to appear. 

Usually, XML is not among the allowed media types and file extensions in an Omeka S installation. You will have to enable this first. 

### Enable XML uploads

Go to your installation's Settings page, and navigate to the Security section. 

- Add `xml` to the **Allowed file extensions** list. 
- Add `text/xml` to the **Allowed file types** list.

![Security settings view for Allowed media types and Allowed file extensions with XML added to the lists.](../modules/modulesfiles/ohmsembed_xmlsettings.png)

When you are finished, click the "Save" button in the upper right hand corner of the screen.

### Upload XML files

You can upload your OHMS XML files individually to items from your computer, or you can batch-import OHMS files onto new or existing items using [CSV Import](csvimport.md). 

!!! note
	Omeka Classic will not be able to generate an item thumbnail from OHMS files. You may wish to add an image the item to generate a thumbnail before you add your XML file.

#### Bulk-import OHMS files

If you are interested in adding many OHMS objects to your Omeka S installation at once, it is possible to use [CSV Import](Csv_Import.md). You can also use the [Dropbox plugin](filesideload.md) to host the XML files for ingest if needed.

Upload the XML files to your hosting service or Dropbox directory. Then, create a spreadsheet that lists the URLs of the files and the metadata you wish to ingest. If you are planning to extract all metadata from the XML files, you can provide exclusively a column of file URLs.

## Embed the OHMS viewer

Having added your OHMS XML files to you Omeka Classic items, you are ready to display them on your sites. 

### OHMS viewer on item and file pages

The OHMS viewer will load on Item and File Pages

!!! note
	Themes that use the Lightbox gallery viewer for images does not currently display the OHMS viewer where an OHMS XML file is detected. Therefore you may wish to select a theme that does not use the Lightbox gallery viewer. 

### OHMS viewer on Exhibit pages

You can use the ["File with Text" or the "File"](https://omeka.org/classic/docs/Plugins/ExhibitBuilder/#content) block to place the OHMS viewer directly into Exhibit pages. Choose an item by clicking the large plus sign button titled _Add Item_ appearing in the Items area.

![Page editing showing the Media embed block with settings.](modulesfiles/ohmsembed_mediaEmbed.png)

You must select the XML file as the attached media - do not choose the image that you may have ingested to the same item to create a thumbnail. 

![Page view with Media Embed block with OHMS viewer in the first column and sample HTML in the second column](modulesfiles/ohmsembed_public_mediaembed.png)

#### Using the OHMS viewer

The Omeka Classi OHMS viewer has several public controls: a toggle between the index and the transcription and/or translation if those elements are available, an information icon that shows the media metadata, and an option to move to a fullscreen view.

![Omeka S OHMS viewer public interface controls showing an index/transcript/translations toggle, and "i" icon and fullscreen button](../modules/modulesfiles/ohmsembed_public_controllers.png)


