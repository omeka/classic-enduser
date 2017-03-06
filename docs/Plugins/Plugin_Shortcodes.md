---
title: Plugin Shortcodes
---
Several plugins also have [shortcodes](../Shortcodes.md) available.
*Note: the corresponding plugin must be installed and activated to utilize any of the following shortcodes.*

## General Short Code Options
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

## Plugin ShortCodes
Organized by the plugin with which they work.

### Exhibit Builder
These shortcodes require the [Exhibit Builder](../Plugins/ExhibitBuilder.md) plugin.

#### Exhibits
The exhibits shortcode will return one or multiple exhibits.

The shortcode is `[exhibits]`. Without additional options, it will return ten exhibits, beginning with the oldest one.

General Options
- `num`
- `ids` 
- `is_featured`
- `sort` by 
  - `title`
  - `random`
  - `added`
- `order` (with sort)

Exhibit IDs can be found at the end of the Edit page url for an exhibit; e.g. yoursite/admin/exhibits/edit/11 -the exhibit ID is 11.

#### Featured Exhibits 
The featured exhibits shortcode will return one or multiple exhibits that have been marked as featured.

The shortcode is `[featured_exhibits]`. Without additional options, it will randomly return one exhibit from all of the ones marked as featured.

General Options:
- `num`

### Geolocation
The [geolocation](../Plugins/Geolocation.md) shortcode will create a map of items based on parameters it is given.

The shortcode is `[geolocation]`. Without any additional parameters, it will return a map of all items that contain geolocation data, limited by the records per page as set in the Geolocation plugin configuration.

**Options**

`fit`
:   specify whether to allow google map to automatically center and zoom the map to fit all of the markers. This is on by default.

To manually specify the map/location zoom, use the following options. Note, to use these options, fit must be set to ‘0’ or ‘false’.

`lat` 
:   specify the latitude of the map’s initial center point, in degrees.
:   Must be between -90 and 90.

`lon` 
:   specify the longitude of the map’s initial center point, in degrees.
:   Must be between -180 and 180

`zoom` 
:   specify the initial zoom level of the map. 0 is the most zoomed out.

If any of `lat`, `lon`, or `zoom` are not specifically set, and ‘fit’ is set to `0` or `false`, the settings from the Geolocation plugin configuration page will be used.

`type` 
:   specify the type of google map that appears. Defaults to the setting from the Geolocation plugin configuration page.
- roadmap - displays the road map view
- satellite - displays Google Earth satellite images
- hybrid - displays a mixture of road map and satellite views
- terrain - displays a physical map based on terrain information

`collection` 
:   limits the map’s items to those from a specific collection, using the collection ID number. Only one collection may be specified.
:   For example: `[geolocation collection=5]`

`tags`
:   limits the map’s items to those from a specific tag. Multiple tags can be entered, separated by a comma, and without any spaces.
:   For example: `[geolocation tags=baseball,math]`

`height`
:   set the map height. Can be set in pixels or percentages, but requires specification with either px or %; defaults to 436px.
:   For example: `[geolocation height=300px]` or `[geolocation height=50%]`

`width` 
:   set the map width. Can be set in pixels or percentages, but requires specification with either px or %; defaults to 100%.
:   For example: `[geolocation width=200px]` or `[geolocation width=75%]`

#### Examples

To print a map of all geotagged items, simply use: 
:  `[geolocation]`

For a map that gets all of the items from your first collection, that are also tagged ‘baseball’
: `[geolocation collection=1 tags=baseball]`
 
A shortcode that leveraged all of the possible parameters would look like
:    `[geolocation lat=42 lon=117 zoom=7 type=hybrid collection=4 tags=baseball,math,oakland height=500px width=500px]`

### Shortcodes Carousel

Requires the [Shortcodes Carousel plugin](../Plugins/ShortcodeCarousel.md).

The plugin adds a shortcode to create a carousel of items using
[jCarousel](http://sorgalla.com/jcarousel/)

The basic shortcode is `[carousel]`.

`[recent_carousel]` and `[featured_carousel]` are shortcuts to
creating a carousel of recent and featured items, respectively.

The same options available for the [Items](url needed) shortcode are available for the carousel, with the exception that `has_image` is always assumed to be true.

**Options**

`speed` 
:   sets the speed for the scrolling animation. May be “fast”, “slow”, or a time in milliseconds. Default is 400.
:   For example: `[carousel speed=slow]` or  `carousel speed=500]`

`autoscroll` 
:   setting autoscroll=true will make the items automatically scroll interval 
:   when autoscroll is on, interval sets the interval between scrolling in milliseconds. Default is 3000.
:   For example: `[carousel autoscroll=true interval=700]`