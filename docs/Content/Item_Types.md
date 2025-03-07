# Item Types

Item types are categories for your Omeka items, often based on their formats. Each item can be assigned to one type. Omeka allows you to add a specific set of associated metadata fields for each item type. Omeka comes by default with the [standardized Dublin Core item types](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#section-7){target=_blank}, but you can easily edit these or add your own.

You can view the following screencast to learn more about item types:

<div style="padding:50.67% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/102038884?h=d1c90306c7" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/102038884">Omeka Classic: Modifying Item Types</a> from <a href="https://vimeo.com/omeka">Omeka</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

Pre-defined item types
---------------------------------------------------------

Note that you can see [other definitions and comments about these types on the Dublin Core website](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#section-7){target=_blank}.

The following are the item types and descriptions included with every installation of Omeka Classic:

- **Text**: A resource consisting primarily of words for reading. Examples include books, letters, dissertations, poems, newspapers, articles, archives of mailing lists. Note that facsimiles or images of texts are still of the genre Text.
- **Moving Image**: A series of visual representations imparting an impression of motion when shown in succession. Examples include animations, movies, television programs, videos, zoetropes, or visual output from a simulation.
- **Oral History**: A resource containing historical information obtained in interviews with persons having firsthand knowledge.
- **Sound**: A resource primarily intended to be heard. Examples include a music playback file format, an audio compact disc, and recorded speech or sounds.
- **Still Image**: A static visual representation. Examples include paintings, drawings, graphic designs, plans and maps. Recommended best practice is to assign the type Text to images of textual materials.
- **Website**: A resource comprising of a web page or web pages and all related assets (such as images, sound and video files, etc.).
- **Event**: A non-persistent, time-based occurrence. Metadata for an event provides descriptive information that is the basis for discovery of the purpose, location, duration, and responsible agents associated with an event. Examples include an exhibition, webcast, conference, workshop, open day, performance, battle, trial, wedding, tea party, conflagration.
- **Email**: A resource containing textual messages and binary attachments sent electronically from one person to another or one person to many people.
- **Lesson Plan**: A resource that gives a detailed description of a course of instruction.
- **Hyperlink**: A link, or reference, to another resource on the Internet.
- **Person**: An individual.
- **Interactive Resource**: A resource requiring interaction from the user to be understood, executed, or experienced. Examples include forms on Web pages, applets, multimedia learning objects, chat services, or virtual reality environments.
- **Dataset**: Data encoded in a defined structure. Examples include lists, tables, and databases. A dataset may be useful for direct machine processing.
- **Physical Object**: An inanimate, three-dimensional object or substance. Note that digital representations of, or surrogates for, these objects should use Moving Image, Still Image, Text or one of the other types.
- **Service**: A system that provides one or more functions. Examples include a photocopying service, a banking service, an authentication service, interlibrary loans, a Z39.50 or Web server.
- **Software**: A computer program in source or compiled form. Examples include a C source file, MS-Windows .exe executable, or Perl script.

![The item types browse view](../doc_files/itemTypeBrowse.png "The item types browse view")

### Default elements for item types

Omeka Classic creates a number of [elements that are attached to its pre-defined item types](../Admin/Settings/Element_Sets.md). The default elements for each item type listed above are:

- Text:
    - Text
    - Original Format
- Moving Image:
    - Transcription
    - Original Format
    - Duration
    - Compression
    - Producer
    - Director
- Oral History:
    - Interviewer
    - Interviewee
    - Location
    - Transcription
    - Original Format
    - Duration
    - Bit Rate/Frequency
    - Time Summary
- Sound:
    - Transcription
    - Original Format
    - Duration
    - Bit Rate/Frequency
- Still Image:
    - Original Format
    - Physical Dimensions
- Website:
    - Local URL
- Event:
    - Event Type
    - Participants
    - Duration
- Email:
    - Email Body
    - Subject Line
    - From
    - To
    - CC
    - BCC
    - Number of Attachments
- Lesson Plan:
    - Standards
    - Objectives
    - Materials
    - Duration
    - Lesson Plan Text
- Hyperlink:
    - URL
- Person:
    - Birth Date
    - Birthplace
    - Death Date
    - Occupation
    - Biographical Text
    - Bibliography.

The item types Interactive Resource, Dataset, Physical Object, Service, and Software have no default elements.

All of these elements can be deleted, modified, or attached to new or existing item types. 

Edit an existing item type 
---------------------------------------------------------------
You can edit existing item types to modify their metadata fields.

1.  Go to the Item Types page in the admin panel and click on the type you want to modify.
2.  In the next screen, click the "Edit" button. From here, you can edit or delete the current metadata fields or add new ones.
3.  When finished, click "Save Changes".

![Editing the item type “Text”](../doc_files/itemTypeEdit.png "Editing the item type “Text”")

While it is possible to delete existing item types using the "Delete" button on the "Browse Item Types" page, we recommend that you do not delete the predefined item types; it may cause problems should you ever want to export data, or import from another Omeka install. Rather, you should create an alternate, more customized item type and use that in your installation instead.

Create a new item type
--------------------------------------------------------------
To create a new item type, click the green "Add an Item Type" button above the table. That will take you to the following screen.

![Add item type basic view](../doc_files/itemTypeAdd.png "Add item type basic view")

Each item Type must have a **Name**, which must be unique. You can also add a **Description** to help clarify the item type (for example, the descriptions in the list of item types above) and guide users who are adding and describing items.

## Create and add elements

Your item types provide [sets of elements for your items](../Admin/Settings/Item_Type_Elements.md) - specific metadata fields that allow you to describe your items according to their categories (formats, or other types that you design). Learn more on the [Item Type Elements](../Admin/Settings/Item_Type_Elements.md) page.

When adding elements to item types, there are two options: add an existing element or create a new one. You can do this to the default item types and to any that you create.

**Existing elements** are elements that have already been created for another item type, but might be applicable to yours. For example, if you were creating a “Letter” item type, you might add the existing “To” and “From” elements from the “Email” item type, and the “Text” element from the “Text” item type.

### Add an existing element to an item type

1. In the Add Element block, select the **Existing** option.
1. Click the "Add Element" button below. You will see a new block created above this block, with a "Select Below" dropdown menu. 
![Add element block](../doc_files/itemTypeAddElm.png "Add element block")
1. In the element block that is created, select the desired element from the dropdown list. All available elements are displayed alphabetically - not sorted by element set.
![Element block with dropdown list opened](../doc_files/itemTypeExistElm.png "Element block with dropdown list opened")

### Add a new element to an item type

**New elements** require you to enter in a unique element name, and can optionally include a description. This text should help guide users who are entering metadata into this field, and can include vocabulary, structure, or formatting instructions. You might need to create new elements for unique item types, for example “Cancellation Date” and “Cancellation Location” for a “Stamp” item type.

1. In the Add Element block, select the **New** option.
1. Click the "Add Element" button. You will see a new block created above this block, with two empty fields for "Element Name" and "Element Description".
1. In the element block that is created, enter a unique "Element Name" in the first field (toward the top of the block). Enter an "Element Description" in the larger text field. The name is required and the description is optional. 
![New element block with no input](../doc_files/itemTypeNewElm.png "New element block with no input")

Note that an element can be created with the same name as an existing element, and the page can be saved, but that new element will disappear when the page is reloaded. 

### Manage elements

You can delete elements from item types, by clicking the large "X" on the upper right corner of the element block. 

Note that this will not delete elements from your installation, only remove them from association with an item type. If it is a custom-created element, and it is no longer attached to any item types, it will still appear in the dropdown menu in the future. 

To delete these or other existing elements from your Omeka installation, go to the Settings tab, then the [Item Type Elements](../Admin/Settings/Item_Type_Elements.md) tab. You can edit element descriptions there, or delete elements from the database.

![New element block with no input](../doc_files/itemTypeElmTab.png "New element block with no input")

You can hide unused elements from the advanced search page, rather than deleting them from the database, by using the [Hide Elements](https://omeka.org/classic/plugins/HideElements/) plugin.