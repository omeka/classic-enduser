---
title: Shortcodes 
---

Starting with Omeka 2.2, some text fields (like the page content field in Simple Pages) support **shortcodes.**

*Note:* This page is a user’s guide to shortcodes. For developer documentation, see [Working with Shortcodes](http://omeka.readthedocs.org/en/latest/Tutorials/shortcodes.html) on Omeka’s Read the Docs site.*

For shortcodes for Plugins, see the [Plugin Shortcodes](../Plugins/Plugin_Shortcodes.md)

General
--------
Shortcodes can be added into Simple Page text fields. The general syntax is
   `[shortcode key=value]`

Values can be wrapped in single or double quotes, making the following variations valid as well: `[shortcode key=‘value’]` or `[shortcode key=“value”]`

### General Short Code Options
Most short codes have options which can modify the content they return. The following table explains some of the options which are shared across multiple short codes. 

Options specific to a short code can be found in its own section. 

| Option | Purpose | Settings | Example |
| --- | --- | --- | --- |
| `num` | Specify the number of items returned | Must be a whole number | `[recent_items num=10]` |
| `has_image` | Can be use to require that the called item have an image. | `True` (return items with images) or `False` (return only items without images) | `[featured_items has_image=false]` |
| `ids` | Return an item or a list of items, based on item ID numbers. | Multiple item IDs can be entered, separated by a comma without any spaces; or a range separated by a hyphen. | `[items ids=10,76,432]` `[items ids=30-55]` | 
| `is_featured` | Specify whether to return only items that are featured or not featured | `1`: Return only items that are featured; `0`: Return only items that are not featured | `[collections is_featured=1]` | 
| `collection` |Return items only from a specific collection, using the collection ID number. | Only one collection may be specified. | `[items collection=7]` |
| `item_type` | Return only items of a specific [item type](../Managing_Item_Type_Elements) | | `[items item_type=“still image”]`
| `tags` | Return only items from a specific tag. | Multiple tags can be entered,separated by a comma, without any spaces. | `[items tags=baseball,math]` |
| `user` | Return only items added by a specific user, using the user ID number. | Only one user may be specified. | `[items user=3]` |
| `sort` by Elements | Specify the element to sort the items by. Must use double quotes, no space after comma | The syntax is `”Element Set,Element”`| `[items sort=“Dublin Core,Title”]` |
| `sort=added` | Sort by date added | | `[items sort=added]`|
| `sort=modifed` | Sort by date modified | | `[items sort=modifed]`|
| `sort=random` | Randomly choose from the set of returned items, for example in conjunction with the `featured_items` shortcode | | `[items num=1 collection=3 sort=random]`|
| `sort` option `order` | Specify the orderr of the sorting | Note: order requires a sort value to have been specified. `a`: ascending; `d`: descending | `[items num=5 sort=added order=d]` |

Short Codes
--------
The following short codes are built in to Omeka versions 2.2 and higher. 

### Recent Items
The recent items shortcode returns a list of items most recently added to the database.

The shortcode is `[recent_items]`. Without any additional parameters, it will return five items.

General Options:
- `num`

### Featured Items
The featured items shortcode returns a set number of items marked in the admin as featured.

The shortcode is `[featured_items]`. Without any additional parameters, it will return one item at a time.

General Options:
- `num`
- `has_image`

### Items
The items shortcode returns one or multiple items.

The shortcode is `[items]`. Without any additional parameters, it will return a list of the oldest 10 items in your archive.

General Options:
- `num`
- `ids`
- `is_featured`
- `collection`
- `item_type`
- `tags`
- `user`
- `has_image`
- `sort` with all variations of sort

#### Examples
To return a single, random item from a set of items tagged “baseball”: `[items num=1 tags=baseball sort=random]`

To return a list of five most recent items added by the user with the id 3: `[items num=5 user=3 sort=added order=d]`

To return all of the items tagged baseball from the collection with the id 5, sorted by title (ascending): `[items num=0 collection=5 tags=baseball sort=“Dublin Core,Title” order=a]`

To return all of the featured items from the collection with the id 7, sorted by date modified, oldest first: `[items num=0 collection=7 sort=modified order=a]`

### Collections
The collections shortcode returns one or multiple collections.

The shortcode is `[collections]`. Without any additional parameters, it will return a list of the oldest 10 collections.

General Options:
- `num`
- `ids`
- `is_featured`
- `sort` all variations of sort

### Featured Collections
The featured collections shortcode returns a set number of collections marked in the admin as featured.

The shortcode is `[featured_collections]`. Without any additional parameters, it will return one collection at a time.

General Options:
- `num`

### Recent Collections

The recent collections shortcode returns a list of the most recent collections created.

The shortcode is `[recent_collections]`. Without any additional
parameters, it will return five collections.

General Options:
- `num`

### File
The file shortcode will return a file of a specified ID.

The shortcode is `[file]`. It will not function if it is not provided a file ID.

Options:

`id` (*required*)
: specify the ID number of the file you wish to retrieve; see below for instructions on how to find the ID number
: For example, to get the file with the ID of 362: `[file id=362]`

`size`
:   specify the image size for image files
:   *Options:*
:  `thumbnail` - thumbnail version of the image
:  `square_thumbnail` - a squared and centered thumbnail of the image
: `fullsize` - the fullsize version of the image

`link_file` 
:   specify whether to link the file to it’s file show page; default is ‘1’
:   *Options:*
: `1` or `true` - links to the original file 
: `0` or `false` - removes all links to the file 
: `thumbnail` - links to the thumbnail file
: `square_thumbnail` - links to the square thumbnail file
: `fullsize` - links to the fullsize file

`width` 
:   specify the pixel width of the audio or video player; available for most audio and video types; defaults vary.

`height` 
:   specify the pixel height of the audio or video player; available for most audio and video types; defaults vary.

####  Examples

To return a thumbnail of an image, that links to the original file, with the file ID of 5:

    [file id=5 size=thumbnail]

To return a square thumbnail of an image, that links to the fullsize image, with the file id of 12:

    [file id=12 size=square_thumbnail link_file=fullsize]

#### Find the File ID

To find the file id navigate to the admin page for the item it is attached to; for example http://youromekainstallation.com/admin/items/show/482.

At the top of the Item page is a list of the files associated with that item. Clicking on one will bring you to the file page; for example http://youromekainstallation/omeka/admin/files/show/752. 

At the top of the page is a header containing the file ID \# and file title; for example File \#752: “The File Title”. The integer following the \# sign is the ID; in this instance it would be 752. To return this file, the shortcode would be `[file id=752]`