Plugins/Geolocation
===================

[Plugins](../Plugins.1.html "Plugins")


Allows administrative users to save geolocation data for an individual
item. The plugin generates a Google map containing items with
geolocation data and a web page for displaying the map.

Installation
-----------------------------------------------------------------

If you are using Omeka.net, see [instructions for the plugin in the Help
section of
Omeka.net](http://info.omeka.net/build-a-website/manage-themes-and-plugins/geolocation/).

1.  Upload the Geolocation plugin folder into your plugins folder on the
    server; See: [Installing a Plugin](../Installing_a_Plugin.html).
2.  Activate it from the admin → Settings → Plugins page.
3.  Click the Configure link to add the following:
    -   The default location coordinates for your map (the location that
        displays at the center of the map.)
    -   The default zoom level for your map. Enter a number from 1-20,
        with 1 displaying a view of the Earth and 20 showing exact
        placement on a street.
    -   The size of the map that will be displayed on items/show pages.
        You can change the dimensions here to make the map fit into any
        theme without manually editing files. If left blank, the default
        width will be 100% and default height, 300 px. These values may
        effect how other data is displayed on the items/show page along
        with the map location, so you may want to test different sizes.
    -   You can also choose whether the Geolocation plugin should add a
        map to the
        [Contribution](Contribution.html "Plugins/Contribution")
        submission form.

**Note**: Version 1.3 configuration form also include the following:

-   Number of Locations Per page: this is the number of items loaded on
    the public map per page.
-   Add Link to Map in the Items/browse navigation: checking this box
    will add a link to the items page for browsing the map.

Using the Geolocation Plugin
-------------------------------------------------------------------------------------------------

### Adding Geolocation data to Items 

1.  When Adding or Editing an Item, click on the Map tab on the left of
    the page.
2.  In the "Find A Location For The Item" field, add in an address and
    click "Find by Address." Or, click on a location directly on the map
    (zoom and pan to find the location).
3.  Save changes for the item, and the location will be saved and
    displayed with that item.

### Admin Map

Once installed, admin and super users may browse all items geolocated on
the map by clicking the "Map" tab from the main admin
dashboard(admin/geolocation/map/browse). It is also possible to search
for items to display on this map.

### Browsing Items in the Public Map

The Geolocation plugin will create a page for browsing items via a
Google Map. Once your plugin is activated, you can access the page at
`http://example.com/geolocation/map/browse`, where example.com is the
path to your Omeka installation.

**Note:** For versions 1.2 and above, the plugin will automatically add
a link to the map on your items/browse page. The following instructions
only apply if you are using an older version or if you want the map to
be included in your site's main navigation.

To add a link to your map/browse page in your main navigation, edit your
theme's `header.php`, and add the following to your
[public\_nav\_main()](https://omeka.org/codex/Theme_API/public_nav_main "Theme API/public nav main")
function:

``` {.de1}
'Map' => uri('geolocation/map/browse')
```


### Showing a Map on the Item/Show page 

**Note:** For version 1.2 and above, the plugin will automatically show
a map on the items/show page. The following instructions only apply if
you are using an older version of the plugin, or if you want to
customize your map's appearance.

To show a map indicating where an item is located on the item/show page,
you need to use the geolocation\_map\_for\_item() function on
item/show.php. The geolocation\_map\_for\_item() function has three
arguments:


``` {.de1}
<?php echo geolocation_google_map_for_item($item,$width='200',$height='200'); ?>
```


The values for width and height of the map default to 200px. If you'd
like to change those values, simply put the desired values when using
the function on the show.php page. So, for example, if you want a map on
the item/show page that has a width of 400px and a height of 300px, you
would use the following code:


``` {.de1}
<?php echo geolocation_google_map_for_item($item,'400','300'); ?>
```


### Geolocation and Other Plugins 

Keep in mind that if you are activating other plugins that append the
items/show page for displaying content those elements may crowd the
page's public display.


