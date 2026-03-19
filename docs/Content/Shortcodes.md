# Shortcodes

A shortcode works like embedding a multimedia object: a shortcode can insert an image, a video, a set of items, a timeline, a form, or something interactive or dynamic. A shortcode can be included in any body of text. 

In Omeka, shortcodes work in basic text fields (not the HTML editor) on [Simple Pages](../Plugins/SimplePages.md), and on [Exhibit pages](../Plugins/ExhibitBuilder.md). 

Several shortcodes come built-in with an Omeka installation, and many more shortcodes can be added via plugins.

!!! Note 
    For programmers who need help with developing shortcode functionality through plugins, see [Working with Shortcodes](http://omeka.readthedocs.org/en/latest/Tutorials/shortcodes.html){target=_blank} on Omeka Classic’s Developer Documentation site.

General
--------
Shortcodes can be added into text fields on **pages**. You cannot put a shortcode into the "Footer Text" field or the "Homepage Text" field in your theme. The general syntax in a text field would look like this:

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
[shortcode key=value]
Ut enim ad minim veniam, quis nostrud exercitation.... 
```

Values can be wrapped in single or double quotes, making the following variations valid as well: `[shortcode key='value']` or `[shortcode key="value"]`. 

**Shortcodes will not work with smart/curly quotes** (“ and ”). When in doubt, replace double quotes with single quotes. 

When using shortcodes on a Simple Page, do not use the HTML editor. Put the shortcode in the basic text field:

![A Simple Page text field with lorem ipsum and a featured carousel shortcode](../doc_files/shortcodeSimplePage.png "A Simple Page text field with lorem ipsum and a featured carousel shortcode")

When using a shortcode in an Exhibit Builder block, place the code directly into the text editor:

![An exhibit page text block with a file shortcode plugin](../doc_files/shortcodeExhibitBlock.png "An exhibit page text block with a file shortcode plugin")

If the shortcode results in an image being displayed (from an item or file), the shortcode will display the filename or the file's Dublin Core title field as the `alt` text, and as the `title` (which appears when a user hovers their mouse over the image). You may wish to edit the file title with this in mind.

### To find an item or file ID

Many shortcodes call elements from items or files by their internal Omeka identifier number. 

To find an item ID, go to the Items page. You can hover over each item title in turn to view its URL at the bottom of your browser, or click on the link, and look at the number that appears at the end of the URL; for example `https://youromekainstallation.com/admin/items/show/482`.

To find a file ID, navigate to the admin page for the item where it is attached. At the top of the Item page is a thumbnail display of the files associated with that item. Clicking on one will bring you to the file page; for example `http://youromekainstallation/omeka/admin/files/show/752`. 

At the top of the page is a header containing the file ID number and file title; for example File \#752: "The File Title". The integer following the number sign is the ID; in this instance it would be 752. To return this file, the shortcode would be `[file id=752]`.

Built-in shortcodes
--------

The following shortcodes are included with every installation of Omeka versions 2.2 and higher. For more guidance on the options and parameters, [see the table below](#shortcode-options).

### Items
The items shortcode returns one or multiple items.

The shortcode is `[items]`. Without any parameters, it will return a list of the oldest 10 items in your archive.

Options:

- `num`
- `ids`
- `is_featured`
- `collection`
- `item_type`
- `tags`
- `user`
- `has_image`
- `sort`

Examples:

To return a single, random item from a set of items tagged "baseball": 

`[items num=1 tags=baseball sort=random]`

To return a list of five most recent items added by the user with the ID 3:

`[items num=5 user=3 sort=added order=d]`

To return all of the items tagged "baseball" from the collection with the ID 5, sorted by title (ascending): 

`[items num=0 collection=5 tags=baseball sort="Dublin Core,Title" order=a]`

### Recent items
The recent items shortcode returns a list of items most recently added to the database.

The shortcode is `[recent_items]`. Without any parameters, it will return five items.

Options:

- `num` to define a different number of items to display (default is 5).

### Featured items
The featured items shortcode returns a set number of items marked in the admin as featured.

The shortcode is `[featured_items]`. Without any parameters, it will return one item at a time.

Options:

- `num`
- `has_image`

### Collections
The collections shortcode returns one or multiple collections.

The shortcode is `[collections]`. Without any parameters, it will return a list of the oldest 10 collections.

Options:

- `num`
- `ids`
- `is_featured`
- `sort`

### Featured collections
The featured collections shortcode returns a number of collections marked as featured.

The shortcode is `[featured_collections]`. Without any parameters, it will return one collection at a time.

Options:

- `num`

### Recent collections

The recent collections shortcode returns a list of the most recent collections created.

The shortcode is `[recent_collections]`. Without parameters, it will return five collections.

Options:

- `num`

### File
The file shortcode will return a file of a specified ID.

The shortcode is `[file id=#]`. Nothing will display if it is not provided a file ID.

Options:

`id` (*required*): specify the ID number of the file you wish to retrieve. E.g. `[file id=362]`

`size`: specify the image size for image files. Values are:

- `thumbnail` - thumbnail version of the image
- `square_thumbnail` - a squared and centered thumbnail of the image
- `fullsize` - the fullsize version of the image

`link_file`: specify whether to link the file to its file show page; default is ‘1'. Values are:

- `1` or `true` - links to the original file 
- `0` or `false` - removes all links to the file 
- `thumbnail` - links to the thumbnail file
- `square_thumbnail` - links to the square thumbnail file
- `fullsize` - links to the fullsize file

`width`: specify the pixel width of the audio or video player; available for most audio and video types; defaults vary.

`height`: specify the pixel height of the audio or video player; available for most audio and video types; defaults vary.

Examples:

To return a thumbnail of an image, that links to the original file, with the file ID of 5:

`[file id=5 size=thumbnail]`

To return a square thumbnail of an image, that links to the fullsize image, with the file ID of 12:

`[file id=12 size=square_thumbnail link_file=fullsize]`

### Shortcode options

Most shortcodes have options that will modify the content they return. The following table explains some of the options which are shared across multiple shortcodes. 

| Option | Purpose | Settings | Example |
| --- | --- | --- | --- |
| `num` | Specify the number of items returned | Must be a whole number | `[recent_items num=10]` |
| `has_image` | Return items either with or without images | `true` (with) or `false` (without) | `[featured_items has_image=false]` |
| `ids` | Return an item or a list of items by IDs | Separated by comma, or a range with hyphen | `[items ids=10,76,432]`, `[items ids=30-55]` | 
| `is_featured` | Return items that are either featured or not featured | `1`: Featured; `0`: Not featured | `[collections is_featured=1]` | 
| `collection` | Return items only from one collection, by ID number | | `[items collection=7]` |
| `item_type` | Return items of a specific [item type](Item_Types.md) | Double quotes around type | `[items item_type="still image"]`
| `tags` | Return items from a specific tag | Multiple tags separated by comma (no spaces) | `[items tags=baseball,math]` |
| `user` | Return items added by a user, by ID number | | `[items user=3]` |
| `sort=random` | Randomly choose from returned items | | `[items num=1 collection=3 sort=random]`|
| `sort` by Elements | Sort by element, specified by "Element Set,Element" | Double quotes, separated by comma (no spaces) | `[items sort="Dublin Core,Title"]` |
| `sort=added` | Sort by date added | | `[items sort=added]`|
| `sort=modifed` | Sort by date modified | | `[items sort=modifed]`|
| `sort` option `order` | Specify the order of sorting | `a`: ascending; `d`: descending | `[items num=5 sort=added order=d]` |

## Plugin shortcodes

The following shortcodes are provided by plugins built by the Omeka team. Externally-supported plugins may add more shortcodes. 

For more information on how the shortcode options below work, see the table above. 

### Exhibit Builder
These shortcodes require the [Exhibit Builder](../Plugins/ExhibitBuilder.md) plugin.

#### Exhibits
The exhibits shortcode will return one or multiple exhibits.

The shortcode is `[exhibits]`. Without parameters, it will return ten exhibits, beginning with the oldest one.

Options:

- `num`
- `ids` 
- `is_featured`
- `sort` by 
  - `title`
  - `random`
  - `added`
- `order` (with sort)

Exhibit IDs can be found at the end of the Edit page URL for an exhibit. For example, for `yoursite/admin/exhibits/edit/11` the exhibit ID is 11.

#### Featured exhibits 
The featured exhibits shortcode will return one or multiple exhibits that have been marked as featured.

The shortcode is `[featured_exhibits]`. Without parameters, it will randomly return one exhibit from all of the ones marked as featured.

Options:

- `num`

### Geolocation
The [geolocation](../Plugins/Geolocation.md) shortcode will display a map of geotagged items.

The shortcode is `[geolocation]`. Without parameters, it will return a map of all items that have geolocation data, limited by the records per page as set in the Geolocation plugin configuration.

Options:

- `height`: set the map height. Can be set in pixels or percentages, requiring either `px` or `%`; defaults to 436px. For example: `[geolocation height=300px]` or `[geolocation height=50%]`.
- `width`: set the map width. Can be set in pixels or percentages, requiring either `px` or `%`; defaults to 100%. For example: `[geolocation width=200px]` or `[geolocation width=75%]`.
- `fit`: specify whether to allow the map to automatically center and zoom the map to fit all of the markers. This is on by default.

To manually specify the map/location zoom, use the following options. Note, to use these options, `fit` must be set to `0` or `false`.

- `lat`: specify the latitude of the map’s initial center point, in degrees. Must be between -90 and 90.
- `lon`: specify the longitude of the map’s initial center point, in degrees. Must be between -180 and 180.
- `zoom`: specify the initial zoom level of the map. 0 is the most zoomed out.

If any of `lat`, `lon`, or `zoom` are not specifically set, and ‘fit' is set to `0` or `false`, the settings from the Geolocation plugin configuration page will be used.

- `type`: specify the type of google map that appears. Defaults to the setting from the Geolocation plugin configuration page. Values are:
	- `roadmap`: displays the road map view
	- `satellite`: displays Google Earth satellite images
	- `hybrid`: displays a mixture of road map and satellite views
	- `terrain`: displays a physical map based on terrain information.

- `collection`: limits the map’s items to those from only one collection, by collection ID number. For example: `[geolocation collection=5]`.
- `tags`: limits the map’s items to those from a specific tag. Multiple tags can be entered, separated by a comma, with no spaces. For example: `[geolocation tags=baseball,math]`.

Examples:

To display a map of all geotagged items, simply use: `[geolocation]`.

For a map that gets all of the items in your first collection, that are also tagged "baseball": `[geolocation collection=1 tags=baseball]`.
 
A shortcode with all possible parameters would look like `[geolocation fit=0 lat=42 lon=117 zoom=7 type=hybrid collection=4 tags=baseball,math,oakland height=500px width=500px]`.

### Carousel

Requires the [Shortcode Carousel plugin](../Plugins/ShortcodeCarousel.md).

The plugin adds a shortcode to create a carousel of items using [jCarousel](http://sorgalla.com/jcarousel/){target=_blank}.

The basic shortcode is `[carousel]`.

`[recent_carousel]` and `[featured_carousel]` are shortcuts to creating a carousel of recent and featured items, respectively.

The same [options available for the Items shortcode](#items) are available for the carousel, with the exception that `has_image` is always assumed to be true.

Options:

- `speed` sets the speed for the scrolling animation that transitions between items. May be "fast", "slow", or a time in milliseconds. Default is 400. For example, `[carousel speed=slow]` or `[carousel speed=500]`.
- `autoscroll`: setting `autoscroll=true` will make the items automatically scroll at regular intervals. When autoscroll is on, `interval` sets the interval between scrolling in milliseconds. The default is 3000. For example, `[carousel autoscroll=true interval=700]`.

### Timeline

The [timeline](../Plugins/Timeline.md) shortcode will embed a timeline created using the Timeline plugin.

The shortcode is `[timeline title= '']`with the timeline title value inserted. If no valid title is supplied, nothing will display. 