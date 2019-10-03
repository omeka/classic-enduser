The PB Core plugin for Omeka Classic adds elements from the [PB Core Metadata standard](https://pbcore.org/) to your Omeka site. This metadata standard, developed for audiovisual content, can be used to describe items and files. It does not replace the Dublin Core metadata elements in your Omeka Classic site.

## Configuration

No additional configuration is required for this plugin.

## Adding an Item

For guidance on using the PB Core metadata standard, please see [the PB Core website](https://pbcore.org/tutorials).

Once the plugin is installed, PB Core elements are available in their own tab when a user is either Adding or Editing an Item (on the same level as Item Type, File, Tags, and other metadata tabs).

![Edit item with PB Core tab highlighted](../doc_files/plugin_images/pbCoreAdd.png)

Users can complete as much or as little of the PB core as they wish. However, please note that if you do not provide a title in the Dublin Core Title element, the item will show up as `[Untitled]` throughout your site, even if the title display field in PB Core is filled.

Each PB Core element has a description (from the standard) and an input field. Use the checkbox below the field to use HTML formatting in this field. For elements with multiple values, use the `Add Input` button on the left to create additional fields.  

One of the features of PBCore is the use of related sub-elements, such as `Contributor` and `Contributor Role`. If you have more than one value to add to an element that has a related sub-element, use the `Add Input` button to create a field for each value and be sure to enter the values in a consistent order so that they are properly associated. 

![Edit item with contributor and contributorRole files shown. The two fields under contributor read "Contributor 1" and "Contributor 2" while the two fields under contributorRole read "Role of Contributor 1" and "Role of Contributor2". ](../doc_files/plugin_images/pbCoreNestedElements.png)

The nested elements will be captured in the PBCore XML output from Omeka. However, in the web and admin interface, the sub-elements will be displayed as distinct.

![Generated XML from the PBCore metadata. Shows container element "Contributor" with sub-elements "contributor" and "contributorRole" containing the values "Contributor 1" and "Role of Contributor 1"](../doc_files/plugin_images/pbCoreNestedElementsXML.png)

### Adding Item File Metadata

In addition to the item metadata, PBCore offers additional instantiation metdata fields for the item files.

To access the instantiation fields, first add your file to the item and save. Once your file is attached to an item, you can edit the file metadata by clicking on "Files" from the top item menu and then "Edit" to the right of the desired file.

!["Files" view with the "Edit" button to the right of the image highlighted](../doc_files/plugin_images/pbCoreFile.png)

![Edit view for the file showing the PBCore Instantiation metadata fields](../doc_files/plugin_images/pbCoreFileEdit.png)

## Uninstalling

While you can uninstall PB Core just like any other plugin, doing so will not remove the PB Core elements from your Omeka site. 

**Proceed with caution:** only uninstall if you are sure that you no longer need the element sets and the associated data. 

You will need to remove the element sets manually to clear the data from the site. You will also need to delete the element sets prior to reinstalling the plugin.

To remove the element sets, go to Settings in the upper navigation of the admin dashboard (this area is only available to Super Users). Click on the Element Sets tab. You can then Delete the PB Core and the PB Core Instantiation Element Sets. 

![Element Sets view in "Settings" that shows installed metadata schemes, in this case Dublin Core, PBCore, and PBCore Instantiation.](../doc_files/plugin_images/pbCoreDelete.png)