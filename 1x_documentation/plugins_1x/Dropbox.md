Plugins/Dropbox
===============

[Plugins](../Plugins.1.html "Plugins")



The [Dropbox plugin](../../plugins.html#dropbox) allows Omeka users to
'batch upload' a large quantity of files at one time, creating unique
items in the archive for each file. Additionally, it allows you to
associate numerous files with pre-existing items in edit mode.

Dropbox Plugin Installation
-----------------------------------------------------------------------------------------------

1.  Upload and Activate the dropbox plugin (see
    [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin"))
2.  Make 'files' folder located in the Dropbox plugin writable. For most
    servers, chmod -r 777 files will work.

Using the Dropbox plugin 
-----------------------------------------------------------------------------------------

Once activated, the dropbox plugin creates a primary tab on the admin
panel, named Dropbox. It allows you to create a batch of items at once,
rather than one at a time on the items add page. Using the Dropbox also
may allow you to circumvent file size restrictions imposed by your
server administrator.

1\. After following the instructions and properly making the /files/
folder writeable, FTP files to that folder.

2\. The list of files will appear in files tab when adding or editing
items,and under the Dropbox tab available from the /admin screen
(.../admin/dropbox).

3\. From the Admin Dropbox box section (.../admin/dropbox) you may select
files to batch add, apply collections-level metadata, and tags to all of
the selected items. You may also choose to make items public or to
feature them. Click 'upload files/items.' Items are named based upon the
names of files added, but can be modified through the items edit page.

4\. From the Add or Edit Items (.../items/add or .../items/edit) panel,
click on the Files tab and check the box of the file you wish to
associate with that particular item. You may associate multiple files
with that item. Click Add Item or Save Changes button to complete the
file adding process.

You may add files from the dropbox at any point during the adding or
editing process.

-   In version 0.6, files will be sorted alphabetically in the Dropbox
    tab and in the Files list when adding or editing an item.

Security Settings 
---------------------------------------------------------------------------

It may be necessary to add specific mimetypes to the **Allowed File
Types** in the admin section. To get there, select **Settings Security Settings**. For JPEG and PNG files, add:

     ,image/jpeg; charset=binary,image/png; charset=binary

to the end of the list and click on the **Save Changes** button.
