Hooks
=====

The information on this page concerns an old or obsolete version of
Omeka. If you are using a more recent version, instead see [*Hooks* on
Omeka's Read the Docs site](http://omeka.readthedocs.org/en/latest/Reference/hooks/).

The following plugin hooks are part of Omeka's [Plugin API](Plugin_API.html "Plugin API"):

General Hooks
-------------------------------------------------------------------

These general plugin hooks are used for basic plugin features,
installing, configuring, and controlling access.


-   [install](Hooks/install.html "Hooks/install")
-   [initialize](Hooks/initialize.html "Hooks/initialize")
-   [config\_form](Hooks/config_form.html "Hooks/config form")
-   [config](Hooks/config.html "Hooks/config")
-   [upgrade](Hooks/upgrade.html "Hooks/upgrade")
-   [uninstall](Hooks/uninstall.html "Hooks/uninstall")
-   [define\_acl](Hooks/define_acl.html "Hooks/define acl")
-   [define\_routes](Hooks/define_routes.html "Hooks/define routes")

Theme Hooks
---------------------------------------------------------------

Theme hooks allow plugins to add content to various sections of Omeka's
interface. A plugin using one of these hooks can output HTML directly
onto Omeka pages in a way that works across many different themes.

### Admin Theme

-   [admin\_theme\_header](Hooks/admin_theme_header.html "Hooks/admin theme header")
-   [admin\_theme\_footer](Hooks/admin_theme_footer.html "Hooks/admin theme footer")
-   [admin\_append\_to\_dashboard\_primary](Hooks/admin_append_to_dashboard_primary.html "Hooks/admin append to dashboard primary")
-   [admin\_append\_to\_dashboard\_secondary](Hooks/admin_append_to_dashboard_secondary.html "Hooks/admin append to dashboard secondary")
-   [admin\_append\_to\_item\_form](Hooks/admin_append_to_item_form.html "Hooks/admin append to item form")
-   [admin\_append\_to\_items\_show\_primary](Hooks/admin_append_to_items_show_primary.html "Hooks/admin append to items show primary")
-   [admin\_append\_to\_items\_show\_secondary](Hooks/admin_append_to_items_show_secondary.html "Hooks/admin append to items show secondary")
-   [admin\_append\_to\_items\_browse\_primary](Hooks/admin_append_to_items_browse_primary.html "Hooks/admin append to items browse primary")
-   [admin\_append\_to\_items\_browse\_detailed\_each](Hooks/admin_append_to_items_browse_detailed_each.html "Hooks/admin append to items browse detailed each")
-   [admin\_append\_to\_items\_form\_tags](Hooks/admin_append_to_items_form_tags.html "Hooks/admin append to items form tags")
-   [admin\_append\_to\_items\_form\_files](Hooks/admin_append_to_items_form_files.html "Hooks/admin append to items form files")
-   [admin\_append\_to\_items\_form\_collection](Hooks/admin_append_to_items_form_collection.html "Hooks/admin append to items form collection")
-   [admin\_append\_to\_users\_form](Hooks/admin_append_to_users_form.html "Hooks/admin append to users form")
-   [admin\_append\_to\_collections\_browse\_primary](Hooks/admin_append_to_collections_browse_primary.html "Hooks/admin append to collections browse primary")
-   [admin\_append\_to\_collections\_show\_primary](Hooks/admin_append_to_collections_show_primary.html "Hooks/admin append to collections show primary")
-   [admin\_append\_to\_collections\_form](Hooks/admin_append_to_collections_form.html "Hooks/admin append to collections form")
-   [admin\_append\_to\_item\_types\_browse\_primary](Hooks/admin_append_to_item_types_browse_primary.html "Hooks/admin append to item types browse primary")
-   [admin\_append\_to\_item\_types\_show\_primary](Hooks/admin_append_to_item_types_show_primary.html "Hooks/admin append to item types show primary")
-   [admin\_append\_to\_item\_types\_form](Hooks/admin_append_to_item_types_form.html "Hooks/admin append to item types form")
-   [admin\_append\_to\_advanced\_search](Hooks/admin_append_to_advanced_search.html "Hooks/admin append to advanced search")
-   [admin\_append\_to\_plugin\_uninstall\_message](Hooks/admin_append_to_plugin_uninstall_message.html "Hooks/admin append to plugin uninstall message")

### Public Theme

-   [public\_theme\_header](Hooks/public_theme_header.html "Hooks/public theme header")
-   [public\_theme\_footer](Hooks/public_theme_footer.html "Hooks/public theme footer")
-   [public\_theme\_page\_header](Hooks/public_theme_page_header.html "Hooks/public theme page header")
-   [public\_theme\_body](Hooks/public_theme_body.html "Hooks/public theme body")
-   [public\_theme\_page\_content](Hooks/public_theme_page_content.html "Hooks/public theme page content")
-   [public\_append\_to\_items\_browse\_each](Hooks/public_append_to_items_browse_each.html "Hooks/public append to items browse each")
-   [public\_append\_to\_items\_browse](Hooks/public_append_to_items_browse.html "Hooks/public append to items browse")
-   [public\_append\_to\_items\_show](Hooks/public_append_to_items_show.html "Hooks/public append to items show")
-   [public\_append\_to\_collections\_browse\_each](Hooks/public_append_to_collections_browse_each.html "Hooks/public append to collections browse each")
-   [public\_append\_to\_collections\_browse](Hooks/public_append_to_collections_browse.html "Hooks/public append to collections browse")
-   [public\_append\_to\_collections\_show](Hooks/public_append_to_collections_show.html "Hooks/public append to collections show")
-   [public\_append\_to\_advanced\_search](Hooks/public_append_to_advanced_search.html "Hooks/public append to advanced search")

Database Hooks 
---------------------------------------------------------------------


-   [make\_item\_public](Hooks/make_item_public.html "Hooks/make item public")
-   [make\_item\_not\_public](Hooks/make_item_not_public.html "Hooks/make item not public")
-   [make\_item\_featured](Hooks/make_item_featured.html "Hooks/make item featured")
-   [make\_item\_not\_featured](Hooks/make_item_not_featured.html "Hooks/make item not featured")
-   [add\_record\_tag](Hooks/add_record_tag.html "Hooks/add record tag")
-   [remove\_record\_tag](Hooks/remove_record_tag.html "Hooks/remove record tag")
-   [make\_collection\_public](Hooks/make_collection_public.html "Hooks/make collection public")
-   [make\_collection\_not\_public](Hooks/make_collection_not_public.html "Hooks/make collection not public")
-   [make\_collection\_featured](Hooks/make_collection_featured.html "Hooks/make collection featured")
-   [make\_collection\_not\_featured](Hooks/make_collection_not_featured.html "Hooks/make collection not featured")
-   [item\_browse\_sql](Hooks/item_browse_sql.html "Hooks/item browse sql")
-   [after\_upload\_file](Hooks/after_upload_file.html "Hooks/after upload file")


### Generic Record Hooks

The following hooks are fired after or before any model being used,
regardless of what model they are. For example, after\_save\_record hook
is fired when after both an item being saved, as well as a collection or
file.

-   [before\_save\_record](Hooks/before_save_record.html "Hooks/before save record")
-   [after\_save\_record](Hooks/after_save_record.html "Hooks/after save record")
-   [before\_save\_form\_record](Hooks/before_save_form_record.html "Hooks/before save form record")
-   [after\_save\_form\_record](Hooks/after_save_form_record.html "Hooks/after save form record")
-   [before\_delete\_record](Hooks/before_delete_record.html "Hooks/before delete record")
-   [after\_delete\_record](Hooks/after_delete_record.html "Hooks/after delete record")
-   [before\_insert\_record](Hooks/before_insert_record.html "Hooks/before insert record")
-   [after\_insert\_record](Hooks/after_insert_record.html "Hooks/after insert record")
-   [before\_update\_record](Hooks/before_update_record.html "Hooks/before update record")
-   [after\_update\_record](Hooks/after_update_record.html "Hooks/after update record")
-   [before\_validate\_record](Hooks/before_validate_record.html "Hooks/before validate record")
-   [after\_validate\_record](Hooks/after_validate_record.html "Hooks/after validate record")


### Specific Record Hooks

Database hooks that begin with "before\_" and "after\_" are implied and
exist for every model that is defined, including models defined by
plugins. Below are just a few of the available before/after hooks. The
available events are save, save\_form, delete, insert, update, and
validate.

#### Implied hook structure

\[before|after\]\_\[event\]\_\[record name\]

#### Example of implied hook in use

Pre- Omeka 1.5:

``` {.de1}
<?php add_plugin_hook('after_save_item', 'plugin_name_after_save_item'); ?>
```

Omeka 1.5 and later:

``` {.de1}
class MyPlugin extends Omeka_Plugin_Abstract
{
    protected _$hooks = array(
        'after_save_item'
    );
 
    public function afterSaveItem($item)
    {
        //do something with item 
 
    }
 
}
```

For example, below are all the possible implied hooks for Items. These
hooks will only fire when the corresponding action has occurred to an
Item record.

-   after\_save\_item
-   before\_save\_item
-   before\_save\_form\_item
-   after\_save\_form\_item
-   before\_delete\_item
-   after\_delete\_item
-   before\_insert\_item
-   after\_insert\_item
-   before\_update\_item
-   after\_update\_item
-   before\_validate\_item
-   after\_validate\_item

Miscellaneous Hooks
-------------------------------------------------------------------------------

### Browse/show hooks

Additional hooks exist for browse and show pages for many record types.
browse\_record hooks are passed an array of that record type.
show\_record hooks are passed the record.

Here are some examples:

-   show\_itemtype
-   browse\_itemtypes
-   browse\_items
-   browse\_tags
-   browse\_collections
-   browse\_users
-   show\_item
-   show\_user
-   show\_collection
