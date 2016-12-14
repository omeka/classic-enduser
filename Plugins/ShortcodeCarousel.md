---
title: Shortcodes Carousel
---
*Current version: 1.0.1*

The plugin adds a [shortcode](../Shortcodes.md) to create a carousel of items using [jCarousel](http://sorgalla.com/jcarousel/)

The basic shortcode is `[carousel]`.

The shortcakes `[recent_carousel]` and `[featured_carousel]` are shortcuts to creating a carousel of recent and featured items, respectively

General Options
---------
The `carousel` shortcode uses the same options as the `items`, with the exception that `has_image` is always assumed to be true.

| Option | Purpose | Settings | Example |
| --- | --- | --- | --- |
| `num` | Specify the number of items returned | Must be a whole number | `[recent_items num=10]` |
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
| `sort` option `order` | Specify the order of the sorting | Note: order requires a sort value to have been specified. `a`: ascending; `d`: descending | `[items num=5 sort=added order=d]` |

Plugin-specific options
------------------------
**speed**: sets the speed for the scrolling animation. May be "fast", "slow", or a time in milliseconds. Default is 400. For example: `[carousel speed=slow]` or `[carousel speed=500]`

**autoscroll**: setting `autoscroll=true` will make the items automatically scroll

**interval**: when autoscroll is on, interval sets the interval between scrolling in milliseconds. Default is 3000. For example: `[carousel autoscroll=true interval=700]`

**showtitles**: setting `showtitles=true` will display the item title in the carousel. For example `[carousel showtitles=true]`
