
Managing Item Types 2.0
=======================
Item types are type of object, with associated metadata. Omeka comes with pre-defined item types with fields, but you can easily edit these types, or add your own types.

![Item types browse view](/doc_files/itemTypeBrowse.png)

Pre-defined Item Types
---------------------------------------------------------

-   Document: A resource containing textual data. Note that facsimiles or images of texts are still of the genre text.
-   Moving Image: A series of visual representations that, when shown in succession, impart an impression of motion.
-   Oral History:A resource containing historical information obtained in interviews with persons having firsthand knowledge.
-   Sound: A resource whose content is primarily intended to be rendered as audio.
-   Still Image: A static visual representation. Examples of still images are: paintings, drawings, graphic designs, plans and maps. Recommended best practice is to assign the type "text" to images of textual materials.
-   Website: A resource comprising of a web page or web pages and all related assets (such as images, sound and video files, etc.).
-   Event: A non-persistent, time-based occurrence. Metadata for an event provides descriptive information that is the basis for discovery of the purpose, location, duration, and responsible agents associated with an event. Examples include an exhibition, webcast, conference, workshop, open day, performance, battle, trial, wedding, tea party.
-   Email: A resource containing textual messages and binary attachments sent electronically from one person to another or one person to many people.
-   Lesson Plan: Instructional materials with fields that include duration(length of time involved), standards, objectives, materials, and lesson plan text.
-   Hyperlink: Title, URL, Description or annotation.
-   Person: An individual, biographical data, birth and death, etc.
-   Interactive Resource: A resource requiring interaction from the user to be understood, executed, or experienced. Examples include forms on Web pages, applets, multimedia learning objects, chat services, or virtual reality environments.

See [this detailed discussion of item types](/Item_Types.md) for more information.

Edit an Existing Item Type 
---------------------------------------------------------------
You can edit existing item types to modify their metadata fields.
1.  Go to Item Types page in the admin panel and click on the type you want to modify.
2.  In the next screen, click the "edit" button. From here, you can edit or delete the current metadata fields for documents or add new ones (see below, in creating a new item type, for more information)
3.  When finished, click "Save Changes"

![Editing the Item Type “Text”](/doc_files/itemTypeEdit.png)

While it is possible to delete existing item types using the “delete” button on the browse Item Types page, we recommend that you do not delete the predefined item types; should you ever want to export data, or import from another Omeka install, you may need those item types. Rather, you should create an alternate, more customized item type and 

Creating a new Item Type
--------------------------------------------------------------
To create a new Item Type, from the Item Types screen, click the green “Add an Item Type button above the table of Item Types.

![Add Item Type basic view](/doc_files/itemTypeAdd.png)

Each Item Type must have a *Name*, preferably not the same name as another existing item type. You can also add a *Description* to help clarify the item type (for example, the descriptions in the list of item types above).

When adding elements, there are two options: add an existing element or create a new one.

**Existing elements** are elements which have already been created for another item type, but might be applicable to yours. For example, if you were creating a “Letter” item type, you might use the “To” and “From” elements from the “Email” Item Type, and the “Text” element from the “Text” item type.

To add an existing element to your item type:
1. In the Add Element block, select the *Existing* radio button.
1. Click the green *Add Element* button.
![Add element block](/doc_files/itemTypeAddElm.png)
1. In the element block which is created, select the desired element from the dropdown list.
![Element block with dropdown list opened.](/doc_files/itemTypeExistElm.png)

**New elements** are created by you, both the element name and description. You might need to create these for unique item types, for example “Cancellation Date” and “Cancellation Location” for a “Stamp” item type.

To add a new item type:
1. In the Add Element block, select the *New* radio button.
1. Click the green *Add Element* button.
1. In the element block which is created, enter an *Element Name* in the first field (toward the top of the block). Enter an *Element Description* in the larger text field. Note that this description will show up when editing items, so make sure that it is clear.
![New element block with no input](/doc_files/itemTypeNewElm.png)

You can delete an existing element by clicking the large X on the upper right corner of the element block.
