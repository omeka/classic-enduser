# Shortcode Carousel

The [Shortcode Carousel plugin](https://omeka.org/classic/plugins/ShortcodeCarousel/){target=_blank} adds a [shortcode](../Content/Shortcodes.md) to create a carousel of items using [jCarousel](http://sorgalla.com/jcarousel/){target=_blank}.

This plugin has no configuration and adds no entry to the left-hand sidebar.

The basic shortcode is `[carousel]`. Enter this wherever you wish the carousel to appear on your public pages. 

The shortcode `[recent_carousel]` and `[featured_carousel]` are shortcuts to creating a carousel of recent and featured items, respectively.

## Options

The `carousel` shortcode uses the same options as the [item](../Content/Shortcodes.md#items), with the exception that `has_image` is always assumed to be true.

Plugin-specific options:

**speed**: sets the speed for the scrolling animation. May be "fast", "slow", or a time in milliseconds. Default is 400. For example: `[carousel speed=slow]` or `[carousel speed=500]`.

**autoscroll**: setting `autoscroll=true` will make the items automatically scroll.

**interval**: when autoscroll is on, interval sets the interval between scrolling in milliseconds. Default is 3000. For example: `[carousel autoscroll=true interval=700]`.

**showtitles**: setting `showtitles=true` will display the item title in the carousel. For example `[carousel showtitles=true]`.
