---
title: Geolocation
---
The Geolocation plugin allows you to assign a location to items in your Omeka site. The locations are displayed on maps on individual items page and on a browsable map of all geolocated items.

There is a [screencast for Geolocation (version 2.2.4) demonstrating its basic functionality.](https://vimeo.com/156298642)


Configuring
-------------------------------------------------------------
Once you have [installed](../Admin/Adding_and_Managing_Plugins) the Geolocation plugin, go to the Plugins tab in the top navigation of your admin dashboard. Scroll down to the listing for Geolocation and click *Configure* (if you do not see Configure you may need to click the *Install* or *Activate* buttons.

### General Settings
The first section for configuration are the general settings for the appearance of your map on the public and admin sides of your site.

- *API Key*: enter your GoogleMaps API key here. To get a key, click the "Get a Key" button on the [GoogleMaps APIs webpage](https://developers.google.com/maps/web/).
- *Default latitude*: set the center point of the map's latitude (North/South value), in degrees. Using numbers after the decimal point will pinpoint the location more precisely.
- *Default longitude*: set the center point of the map's longitude (East/West), in degrees. Using numbers after the decimal point will pinpoint the location more precisely.
Default latitude and longitude of the point on which your map will center.
- *Default Zoom Level*: Use a whole number of 0 of greater. 0 is the most zoomed out. A value of 15 will result in a map showing roughly one square mile
-   *Map Type*: Roadmap, Satellite, Hybrid (roadmap overlaid on satellite) or Terrain.

![General settings for geolocation](../doc_files/plugin_images/geolocation_genset.png)

### Browse Map Settings
These settings are for the map through which users can browse all geolocated items, and for the "Search by Address function" that Geolocation enables in advanced item search. 

-   *Number of Locations Per Page*: The browsable map has pagination; set the number of items per map page with a whole number.
-   *Auto-fit to Locations*: If checked, the browse map will ignore default location and zoom settings designated in General Settings and instead auto fit to the locations of the items displayed (on that page)
-   *Default Radius*: for the Search By Address function in the advanced items search.
-   A checkbox to *Use metric distances* for radius search, rather than miles.

![Browse map settings for geolocation](../doc_files/plugin_images/geolocation_brset.png)


### Item Map Settings
These settings are for the map display on an item/show page.

- *Width for Item Map*: set in percent, defaults to 100% if left blank.
- *Height for Item Map*: set in pixels defaults to 300px if left blank. 

![Item Map settings](../doc_files/plugin_images/geolocation_ItemMap.png)

### Map Integration
These settings are for integration of the geolocation map into the site menu and the [contribution](/Contribution) plugin's form. 

-   *Add link to map on Items/Browse navigation*: click to make active. 
- *Add map to contribution form*: click to make active. Note that this will only work if you have the Contribution plugin installed and active.

![Map Integration settings](../doc_files/plugin_images/geolocation_Mapint.png)

Getting Started
----------------------------------------------------------------
After you have activated and configured the Geolocation plugin, it is time to geolocate some items.

Geolocation adds a Map tab to the options for \ adding or editing an item (admin/item/edit and admin/item/add pages).  When adding metadata for an item, click on the Map tab to add a location.

![Arrow points to the Map tab](../doc_files/plugin_images/geolocation_set1.png)

On the tab there is a field for you to *find a location by address* and a map which you can drag to move around, zoom in and out with the plus and minus options (or the scroll wheel on a mouse), and toggle between road and satellite maps. 

Enter the address where you want the marker for the item to be placed. The plugin will automatically add a marker at that location. 

You can also click directly on the spot on the map where you want to place the marker. A marker automatically maps the selected site.

To change the location of an item, type in the new address or click on the new location. You'll be asked if you are sure you would like to change the item location. Select OK or Cancel.

To remove geolocation from an item, click directly on the marker. A dialog box will ask you to confirm that you want to delete the location assignment. 
Don't forget to save your changes.

Viewing Items on the Public Map 
----------------------------------------------------------------
Visitors to your Omeka site may use a map to browse through all of your geolocated items.

When configuring the plugin, if you selected "Add Link to Map on
Items/Browse Navigation," a "Browse Map" link will be added
automatically to the secondary navigation on the items/browse page.

![Public items map view in the Thanks Roy theme](../doc_files/plugin_images/geolocation_pubbr.png)

From this view, visitors may browse all mapped items, browse by tag, search for items and browse the map.

They may also locate a mapped item by clicking on the items listed in the right column of the map.

Browse and Search Items on Admin Map
----------------------------------------------------------------
A Map tab appears in the left navigation bar located on the left side of the Dashboard. Clicking on the Map tab takes you to a map that displays all items geolocated in your Omeka site--public and not public, and an advanced search form to locate specific items.

![Admin item browse map with search form](../doc_files/plugin_images/geolocation_adminbr.png)

From this view, you may also search mapped items using the item advanced search. Search results appear directly on the map.

Geolocation and Exhibit Builder
--------------------------------
If you have [Exhibit Builder](/ExhibitBuilder) (version 3.x) installed, Geolocation will add a Map block to the options when building pages. 

![Admin item browse map with search form](../doc_files/plugin_images/geolocation_ex1.png)

You can add items with geolocation markers to the map block. The exhibit will display a single map with the markers for those specific items. 

![Public view of exhibit map block](../doc_files/plugin_images/geolocation_ex2.png)

Shortcodes
-----------------
The geolocation [shortcode](/Plugin_Shortcodes) will create a map of items based on parameters it is given.

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