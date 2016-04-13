
Plugins/Dropbox 2.0
===================


[Plugins](../Plugins.1.html "Plugins")

Overview 
---------------------------------------------------------

The Dropbox allows Omeka users to batch upload a large quantity of files
at one time, and may allow you to circumvent file size restrictions
imposed by your server administrator. Once installed, you may create
unique items from each file, and you may associate numerous files with
pre-existing items.

**Please note that this plugin is not affiliated with the Dropbox service.**

Using the Dropbox plugin
-----------------------------------------------------------------------------------------

1.  Upload and install the Dropbox plugin (see [Installing a Plugin](../Managing_Plugins_2.0.html#Installing_a_Plugin "Managing Plugins 2.0"))
2.  Make 'files' folder located in the /Dropbox plugin directory
    writable to the Apache server. For most servers, you can use the
    follow command to make the file writable: chmod -r 775 files.
3.  Once activated, the Dropbox plugin creates a tab found on the left
    side menu under Dashboard in admin.
4.  FTP files you wish to upload to the /files folder located on the
    server (/plugins/Dropbox/files/). The list of files will appear in
    files tab when adding or editing items,and under the Dropbox tab
    available from the /admin screen (.../admin/dropbox).


[![Dropbox.jpg](https://omeka.org/c/images/e/e0/Dropbox.jpg)](https://omeka.org/codex/File:Dropbox.jpg)

Batch Adding Files As Items 
-----------------------------------------------------------------------------------------------

-   From the Dropbox box tab (.../admin/dropbox) you may select files to
    batch add as individual items (1 file creates 1 item). When
    selecting files, you may also add them to a collection and associate
    the same set of tags, make the items public or feature them.
-   Click "Upload Files as Items." Items are created from each file and
    titled with the file name. This can modified later if you wish to
    edit the item's title.

Adding Files to Items 
-----------------------------------------------------------------------------------

-   To add dropbox files to items, add or edit an item(.../items/add
    or .../items/edit) and click on the Files tab.
-   Check the box, or boxes, of the file(s) you wish to associate with
    that particular item. You may associate multiple files with
    that item. Click Add Item or Save Changes button to complete the
    file adding process.


[![Dropboxitem.png](https://omeka.org/c/images/thumb/e/ef/Dropboxitem.png/400px-Dropboxitem.png)](https://omeka.org/codex/File:Dropboxitem.png)


-   You may add files from the dropbox at any point during the adding or
    editing process.

Security Settings
---------------------------------------------------------------------------

It may be necessary to add specific mimetypes to the Allowed File Types
in the admin section. See [Managing Security Settings](../Managing_Security_Settings_2.0.html "Managing Security Settings 2.0")
for more information.

