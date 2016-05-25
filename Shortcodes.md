---
title: Shortcodes
---

Starting with Omeka 2.2, some text fields (like the page content field in Simple Pages) support **shortcodes.**

*This page is a user's guide to shortcodes. For developer documentation, see [Working with Shortcodes](http://omeka.readthedocs.org/en/latest/Tutorials/shortcodes.html)
on Omeka's Read the Docs site.*

General
-----------------------------------------------------

Shortcodes can be added into Simple Page text fields. The general syntax is

   `[shortcode key=value]`

Values can be wrapped in single or double quotes, making the following variations valid as well.

    [shortcode key='value']

    [shortcode key="value"]

Built-in Shortcodes
----------------------------------------------------------

Omeka comes with a number of shortcodes available by default.

### Recent Items
The recent items shortcode returns a list of items most recently added to the database.

The shortcode is `[recent_items]`. Without any additional parameters, it will return five items.

#### Options

The following options are supported:

`num` 
:   Specify the number of items returned; default is '5'
:   For example, to return 10 items, the shortcode should read:  `[recent_items num='10’]`

### Featured Items

The featured items shortcode returns a set number of items marked in the admin as featured.

The shortcode is `[featured_items]`. Without any additional parameters, it will return one item at a time.

#### Options

The following options are supported:

`num` 
:   Specify the number of items returned; default is '1'

`has_image` 
:   Can be used to require the featured item to have or not have an image; default will return items both with and without images
:   Settings:
:           `true`: Return only items that have an image file associated with them
:          `false`: Return only items that do not have an image file associated with them
:   For example, to return 2 featured items, and only ones that do not contain an image: `[featured_items num=2 has_image=false]`

### Items

The items shortcode returns one or multiple items.

The shortcode is `[items]`. Without any additional parameters, it will return a list of the oldest 10 items in your archive.

#### Options

The following options are supported:

`num` 
:   Specify the maximum number of items to return; specifying 0 will return all items; default is 10
:   For example, to return five items: `[items num=5]`

`ids` 
:   Return an item or a list of items, based on item ID numbers. Multiple item IDs can be entered, separated by a comma, without any spaces; or a range separated by a hyphen.
:   For example: 
  - to return a single item that has an ID of 13: `[items ids=13]`
  - to return the items with IDs of 10, 76, and 432: `[items ids=10,76,432]`
- to return all of the items between item 30 and item 55: `[items ids=30-55]`

`is_featured` 
   Specify whether to return only items that are featured or not featured
   Options:
- `1`: Return only items that are featured
- `0`: Return only items that are not featured
   For example: `[items is_featured=1]`  

`collection` 
Return items only from a specific collection, using the collection ID number. Only one collection may be specified.
For example: `[items collection=7]`

`item_type` 
:   Return only items of a specific [item type](url needed)
:   For example: `[items item_type="still image”]`


`tags` 
:   Return only items from a specific tag. Multiple tags can be entered,separated by a comma, without any spaces.
:   For example: `[items tags=baseball,math]`

`user` 
:   Return only items added by a specific user, using the user ID number. Only one user may be specified.
:   For example:
:   `[items user=3]`

`has_image` 
:   Can be used to require the featured item to have or not have an image; omit to return items regardless of whether they have images
:   Options:
- `true`: Return only featured items that have an image file associated with them
- `false`: Return only featured items that do not have an image file associated with them

:   For example: `[items has_image=true]`

The items can also be sorted in different ways with the following options.

`sort` 
:   Specify the field that will be used to sort the items.
 - Elements: specify the element to sort the items by. The syntax is `"Element Set,Element"`

For example, to sort the items by their Dublin Core Titles: `[items sort="Dublin Core,Title”]`. NOTE: double quotes must be used in this instance to wrap the values, and there cannot be a space between the comma following the element set and the element.

- `added`: Sort items by date added. For example, to get the 10 most recent items: `[items num=10 sort=added order=d]`
- `modified`: Sort items by date modified
- `random`: Randomly choose from the set of returned items. This is often used to rotate a single item from a set of items, as the `featured_items` shortcode does. For example, if you wanted to show one randomly chosen item from the items of a specific collection: `[items num=1 collection=3 sort=random]`

`order` 
:   Specify the order of the sorting
:   Options:
- `a`: items will appear in acsending order
- `d`: items will appear in descending order
:   Note: order requires a sort value to have been specified.
:   For example, to get the 5 most recent items from a collection `[items num=5 collection=3 sort=added order=d]`

#### Examples

To return a single, random item from a set of items tagged “baseball”:
     [items num=1 tags=baseball sort=random]

To return a list of five most recent items added by the user with the id 3: 
     [items num=5 user=3 sort=added order=d]

To return all of the items tagged “baseball” from the collection with the id 5, sorted by title:
     [items num=0 collection=5 tags=baseball sort="Dublin Core,Title" order=a]

To return all of the featured items from the collection with the id 7, sorted by date modified, oldest first:
     [items num=0 collection=7 sort=modified order=a]

### Collections

The collections shortcode returns one or multiple collections.

The shortcode is `[collections]`. Without any additional parameters, it will return a list of the oldest 10 collections.

#### Options

The following options are supported:

num 
:   specify the number of collections to return; specifying '0' will return all collections; default is 10


`ids` 
:   *(Versions Omeka 2.2.2 and higher)*
:   Return an item or a list of items, based on item ID numbers. Multiple item IDs can be entered, separated by a comma, without any spaces; or a range separated by a hyphen. 
:   For example: to return a single item that has an ID of 13 `[items ids=13]`;
:  to return the items with IDs of 10, 76, and 432 `[items ids=10,76,432]`;
:      to return all of the items between item 30 and item 55 `[items ids=30-55]`

`is_featured` 
:   specify whether to return only collections that are either featured, or not featured.
- 1 - will return only collections that are featured
- 0 - will return only collections that are not featured

For example, to return all of the collections marked featured:
    [collections num=0 is_featured=1]

The collections can also be sorted in different ways with the following options.

`sort`
:   specifies the field that will be used to sort the collections.

`Elements`
 : specify the element to sort the items by. The syntax is "Element Set,Element"
: For example to sort the collections by their Dublin Core Titles
    [collections sort="Dublin Core,Title"]

*NOTE- double quotes must be used in this instance to wrap the values, and there cannot be a space between the comma following the element set and the element.*

`random` 
:   may be passed to sort to randomly choose from the set of returned collections. This is often used to rotate a single collection from a set of collections, as the `featured_collections` shortcode does.

`added` 
:   may be passed to sort collections by date added
:   For example, to get the 10 most recent collections
    [collections num=10 sort=added order=d]

modified 
:   may be passed to sort items by date modified

order 
:   specify the order of the collections
- a - collections will appear in acsending order
- d - collections will appear in descending order
:   *NOTE-order requires a sort value to have been specified.*

### Featured Collections
The featured collections shortcode returns a set number of collections marked in the admin as featured.

The shortcode is `[featured_collections]`. Without any additional parameters, it will return one collection at a time.

#### Options

The following options are supported:

`num`
: specify the number of collections to return; default is '1'
For example, to return two featured collections:
    `[featured_collections num=2]`

### Recent Collections 
The recent collections shortcode returns a list of the most recent collections created.

The shortcode is `[recent_collections]`. Without any additional
parameters, it will return five collections.

#### Options

The following options are supported:

num 
:   specify the number of collections to return; default is '5'

For example, to get to the three most recent collections created: `[recent_collections num=3]`

### File

The file shortcode will return a file of a specified ID.

The shortcode is `[file]`. It will not function if it is not provided a file ID.

#### Options

The following options are supported:

id (required)
:   specify the ID number of the file you wish to retrieve; see below for instructions on how to find the ID number

For example, to get the file with the ID of 362: `[file id=362]`

size 
:   specify the image size for image files
:   Options:
- `thumbnail` - thumbnail version of the image
- `square_thumbnail` - a squared and centered thumbnail of the image
- `fullsize` - the fullsize version of the image

`link_file` 
:   specify whether to link the file to it's file show page; default is '1'
:   Options:
- `1` or `true` - links to the original file
- `0` or `false` - removes all links to the file
- thumbnail - links to the thumbnail file
- `square_thumbnail` - links to the square thumbnail file
- `fullsize` - links to the fullsize file

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

At the top of the page is a header containing the file ID \# and file title; for example File \#752: "The File Title". The integer following the \# sign is the ID; in this instance it would be 752. To return this file, the shortcode would be `[file id=752]`

Plugin Shortcodes
--------------------------------------------------------

Several plugins also have shortcodes available.

*Note: the corresponding plugin must be installed and activated to utilize any of the following shortcodes.*

### Featured Exhibits

Requires the Exhibit Builder plugin to be installed and activated.

The featured exhibits shortcode will return one or multiple exhibits that have been marked as featured.

The shortcode is `[featured_exhibits]`. Without additional options, it will randomly return one exhibit from all of the ones marked as featured.

#### Options

num 
:   specify the number of exhibits to display
:   For example, to show three featured exhibits:

   `[featured_exhibits num=3]`

### Exhibits

Requires the Exhibit Builder plugin to be installed and activated.

The exhibits shortcode will return one or multiple exhibits.

The shortcode is `[exhibits]`. Without additional options, it will return ten exhibits, beginning with the oldest one.

#### Options

`num 
:   specify the number of exhibits to display
:   For example, to show three exhibits:

    `[exhibits num=3]`

`ids`
:   return an exhibit or a list of exhibits, based on item ID numbers. Multiple exhibit IDs can be entered, separated by a comma, without any spaces; or a range separated by a hyphen. Exhibit IDs can be found at the end of the Edit page url for an exhibit; eg yoursite/admin/exhibits/edit/11 -the exhibit ID is 11.

For example:
-   to return a single exhibit that has an ID of 13
    [exhibits ids=13]

-   to return the exhibits with IDs of 10, 12, and 32
    [exhibits ids=10,12,32]

-   to return all of the exhibits between exhibit 5 and exhibit 10
    [exhibits ids=5-10]

`is_featured` 
:   specify whether to return only exhibits that are featured or not featured
:   Options:
    -   1 - will return only items that are featured
    -   0 - will return only items that are not featured

The exhibits can also be sorted in different ways with the following options.

sort 
:   specifies the field that will be used to sort the exhibits.
-   title : sort exhibits by title
-   added : sort exhibits by date added
-   random - may be passed to sort to randomly choose from the set of returned items.

`order` 
:   specify the order of the exhibits
:   Options:
    -   a - exhibits will appear in acsending order
    -   d - exhibits will appear in descending order

:   **NOTE-order requires a sort value to have been specified.**

For example, to get the five most recent exhibits:
    `[exhibits num=5 sort=added order=d]`

### Geolocation

Requires the Geolocation plugin to be installed and activated.

The geolocation shortcode will create a map of items based on parameters it is given.

The shortcode is `[geolocation]`. Without any additional parameters, it will return a map of all items that contain geolocation data, limited by the records per page as set in the Geolocation plugin configuration.

#### Options

The following options are supported:

`fit` 
:   specify whether to allow google map to automatically center and zoom the map to fit all of the markers. This is on by default.

To manually specify the map/location zoom, use the following options. Note, to use these options, fit must be set to '0' or 'false'.

`lat` 
:   specify the latitude of the map's initial center point, in degrees.
:   Must be between -90 and 90.

`lon` 
:   specify the longitude of the map's initial center point, in degrees.
:   Must be between -180 and 180

`zoom` 
:   specify the initial zoom level of the map. 0 is the most zoomed out.

If any of lat, lon, or zoom are not specifically set, and 'fit' is set to 0 or false, the settings from the Geolocation plugin configuration page will be used.

`type` 
:   specify the type of google map that appears. Defaults to the setting from the Geolocation plugin configuration page.
- roadmap - displays the road map view
- satellite - displays Google Earth satellite images
- hybrid - displays a mixture of road map and satellite views
- terrain - displays a physical map based on terrain information

`collection` 
:   limits the map's items to those from a specific collection, using the collection ID number. Only one collection may be specified.
:   For example

    [geolocation collection=5]

`tags` 
:   limits the map's items to those from a specific tag. Multiple tags can be entered, separated by a comma, and without any spaces.
:   For example 

    [geolocation tags=baseball,math]

`height`
:   set the map height. Can be set in pixels or percentages, but requires specification with either px or %; defaults to 436px.
:   For example
    [geolocation height=300px]
or
    [geolocation height=50%]

`width` 
:   set the map width. Can be set in pixels or percentages, but requires specification with either px or %; defaults to 100%.
:   For example    [geolocation width=200px]

or

    [geolocation width=75%]

None, any, or all of the parameters may be set. None are required.

#### Examples

To print a map of all geotagged items, simply use:

    [geolocation]

For a map that gets all of the items from your first collection, that
are also tagged 'baseball'

    [geolocation collection=1 tags=baseball]

A shortcode that leveraged all of the possible parameters would look like

    [geolocation lat=42 lon=117 zoom=7 type=hybrid collection=4 tags=baseball,math,oakland height=500px width=500px]

### Shortcodes Carousel

Requires the [Shortcodes Carousel plugin](URL NEEDED).

The plugin adds a shortcode to create a carousel of items using
[jCarousel](http://sorgalla.com/jcarousel/)

The basic shortcode is \[carousel\].

\[recent\_carousel\] and \[featured\_carousel\] are shortcuts to
creating a carousel of recent and featured items, respectively.

#### Options

The same options available for the Items shortcode are available for the carousel, with the exception that `has_image` is always assumed to be true.

Additional options for the carousel are:

`speed` 
:   sets the speed for the scrolling animation. May be "fast", "slow", or a time in milliseconds. Default is 400.
:   For example: `[carousel speed=slow]` or  `carousel speed=500]`

`autoscroll` 
:   setting autoscroll=true will make the items automatically scroll interval 
:   when autoscroll is on, interval sets the interval between scrolling in milliseconds. Default is 3000.
:   For example: `[carousel autoscroll=true interval=700]`

