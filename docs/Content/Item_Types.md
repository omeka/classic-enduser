# Item Types

Item types are categories for your Omeka items based on their formats. Omeka offers you a specific set of associated metadata for each item type. Omeka comes by default with [Dublin Core item types](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#section-7){target=_blank}, but you can easily edit these or add your own.

You can view the following screencast to learn more about item types:

<div style="padding:50.67% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/102038884?h=d1c90306c7" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
<p><a href="https://vimeo.com/102038884">Omeka Classic: Modifying Item Types</a> from <a href="https://vimeo.com/omeka">Omeka</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

Pre-defined item types
---------------------------------------------------------

-   **Document**: A resource containing textual data. Note that facsimiles or images of texts are still of the genre text.
-   **Moving Image**: A series of visual representations that, when shown in succession, impart an impression of motion.
-   **Oral History**: A resource containing historical information obtained in interviews with persons having firsthand knowledge. This may be an audio or video recording, or a transcript of a conversation. 
-   **Sound**: A resource whose content is primarily intended to be rendered as audio.
-   **Still Image**: A static visual representation. Examples of still images are: paintings, drawings, graphic designs, plans, and maps. Recommended best practice is to assign the type "text" to images of textual materials.
-   **Website**: A resource comprising a web page or web pages and all related assets (such as images, sound and video files, etc.).
-   **Event**: A non-persistent, time-based occurrence. Metadata for an event provides descriptive information that is the basis for discovery of the purpose, location, duration, and responsible agents associated with an event. Examples include an performance, battle, exhibition, webcast, conference, workshop, trial, or wedding.
-   **Email**: A resource containing textual messages and binary attachments sent electronically from one person to another or one person to many people.
-   **Lesson Plan**: Instructional materials with fields that include duration (length of time involved), standards, objectives, materials, and lesson plan text.
-   **Hyperlink**: An item that allows you to provide a URL as the main attached information. You can also attach files. Notes that entries in the URL field of this item type will not automatically be rendered into a clickable link, but you can employ the HTML editing feature to do so.
-   **Person**: An individual. Elements include biographical data, birth and death, etc.
-   **Interactive Resource**: A resource requiring interaction from the user to be understood, executed, or experienced. Examples include forms on Web pages, applets, multimedia learning objects, chat services, or virtual reality environments.

![The item types browse view](../doc_files/itemTypeBrowse.png "The item types browse view")


### Default elements for item types

Omeka Classic creates a number of elements that are attached to its pre-defined item types. The default elements for each item type listed above are:

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
To create a new item type, click the green "Add an Item Type" button above the table.

![Add item type basic view](../doc_files/itemTypeAdd.png "Add item type basic view")

Each item Type must have a **Name**, which must be unique. You can also add a **Description** to help clarify the item type (for example, the descriptions in the list of item types above) and guide users who are adding and describing items.

## Create and add elements

Your item types provide [sets of elements for your items](../Admin/Settings/Item_Type_Elements.md) - specific metadata fields that allow you to describe your items according to their categories (formats, or other types that you design). Learn more on the [Item Type Elements](../Admin/Settings/Item_Type_Elements.md) page.

When adding elements to item types, there are two options: add an existing element or create a new one. You can do this to the default item types and any you create.

**Existing elements** are elements that have already been created for another item type, but might be applicable to yours. For example, if you were creating a “Letter” item type, you might add the existing “To” and “From” elements from the “Email” item type, and the “Text” element from the “Text” item type.

### Add an existing element to an item type

1. In the Add Element block, select the **Existing** option.
1. Click the green "Add Element" button.
![Add element block](../doc_files/itemTypeAddElm.png "Add element block")
1. In the element block which is created, select the desired element from the dropdown list. All available elements are displayed alphabetically.
![Element block with dropdown list opened](../doc_files/itemTypeExistElm.png "Element block with dropdown list opened")

**New elements** require you to enter in a unique element name, and can optionally include a description. This text should help guide users who are entering metadata into this field, and can include vocabulary, structure, or formatting instructions. You might need to create new elements for unique item types, for example “Cancellation Date” and “Cancellation Location” for a “Stamp” item type.

Note that an element can be created with a duplicate name, and the page can be saved, but that new element will disappear when the page is reloaded. 

### Add a new element to an item type

1. In the Add Element block, select the **New** option.
1. Click the green "Add Element" button.
1. In the element block which is created, enter an "Element Name" in the first field (toward the top of the block). Enter an "Element Description" in the larger text field. 
![New element block with no input](../doc_files/itemTypeNewElm.png "New element block with no input")

### Manage elements

You can delete elements from item types, by clicking the large "X" on the upper right corner of the element block. If it is a custom-created element, and it is no longer attached to any item types, it will still appear in the dropdown menu in the future. 

To delete these or existing elements from your Omeka install, go to the Settings tab, then the [Item Type Elements](../Admin/Settings/Item_Type_Elements.md) tab. You can edit element descriptions there, or delete elements from the database.

![New element block with no input](../doc_files/itemTypeElmTab.png "New element block with no input")

You can hide unused elements from the advanced search page, rather than deleting them from the database, by using the [Hide Elements](https://omeka.org/classic/plugins/HideElements/) plugin.