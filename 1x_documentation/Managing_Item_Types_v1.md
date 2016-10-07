---
title: Managing Item Types
---

Item types are user-defined type of object, with associated Omeka comes with pre-defined item types with fields, but you can easily edit these types, or add your own types.

Screencast Tutorial
----------------------------------------------------------------

Watch a screencast to learn [how to manage item types and fields](../1x_documentation/1x_Screencasts/ItemTypesandFields1.0.mov).

Existing Item Types
----------------------------------------------------------------
-   Document: A resource containing textual data. Note that facsimiles or images of texts are still of the genre text.
-   Moving Image: A series of visual representations that, when shown in succession, impart an impression of motion.
-   Oral History:A resource containing historical information obtained in interviews with persons having firsthand knowledge.
-   Sound: A resource whose content is primarily intended to be rendered as audio.
-   Still Image: A static visual representation. Examples of stil images are: paintings, drawings, graphic designs, plans and maps. Recommended best practice is to assign the type "text" to images of textual materials.
-   Website: A resource comprising of a web page or web pages and all related assets (such as images, sound and video files, etc.).
-   Event: A non-persistent, time-based occurrence. Metadata for an event provides descriptive information that is the basis for discovery of the purpose, location, duration, and responsible agents associated with an event. Examples include an exhibition, webcast, conference, workshop, open day, performance, battle, trial, wedding, tea party.
-   Email: A resource containing textual messages and binary attachments sent electronically from one person to another or one person to many people.
-   Lesson Plan: Instructional materials with fields that include     duration(length of time involved), standards, objectives, materials, and lesson plan text.
-   Hyperlink: Title, URL, Description or annotation.
-   Person: An individual, biographical data, birth and death, etc.
-   Interactive Resource: A resource requiring interaction from the user to be understood, executed, or experienced. Examples include forms on Web pages, applets, multimedia learning objects, chat services,  or virtual reality environments.

Modifying Existing Item Types
----------------------------------------------------------------
1.  Go to Item Types page in the admin panel and click on the type you want to modify.
2.  In the next screen, click the "edit" button. From here, you can edit or delete the current metafields for documents, et al, or add new ones.
3.  When finished, click "Save Changes"

Creating a new Item Type
----------------------------------------------------------------
1.  If you are interested in creating a new "item type", go to your /admin/ screen, click on the Types tab (/admin/item-types). On the right side, click the button to "Add an Item Type."
2.  From this screen you may create a new item type new fields that correspond with the type of data you want to associate.

Edit an Existing Item Type Element
----------------------------------------------------------------
1.  If you decide to change the name or description of an item type element, you will have to edit using PhPMyAdmin, or another tool that manages MySQL databases on your server.
2.  Once you have opened your database in PhPMyAdmin, or in a similar tool, find and open the omeka\_elements table. As you browse through this table, you will find every field available for your entire installation.
3.  Edit the element you would like to modify and save your changes.
4.  Please note, that if you delete an element in the /admin/item-types/edit/numberofitemtype you will also delete any information saved in the database.