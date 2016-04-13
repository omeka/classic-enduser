Plugins/Geolocation 2.0
=======================


[Plugins](../Plugins.1.html "Plugins")


The Geolocation plugin allows you to pin items in your database to a
Google map. Items are geolocated individually with related metadata and
collectively on a central map.

Configuring
-------------------------------------------------------------

Once you have
[installed](../Managing_Plugins_2.0.html#Installing_a_Plugin "Managing Plugins 2.0")
the Geolocation plugin, select Plugins in the top navigation of your
admin. Scroll down to the Geolocation plugin and click the green
Activate button. The page will reload; scroll down again and click the
Configure button for the Geolocation plugin.

### General Settings


[![Geogen.png](https://omeka.org/c/images/3/3a/Geogen.png)](https://omeka.org/codex/File:Geogen.png)


-   Default latitude and longitude of the point on which your map
    will center.
    -   Latitude has a North/South value (sometimes noted with a N or S
        after the coordinates, longitude has an East/West value.
    -   Use a decimal point for the degree mark if you are trying for
        very specific points (so 51°80 would be 51.8)
-   Default Zoom Level. 0 is the most zoomed out, 20 is very zoomed in.
-   Map Type: Roadmap, Satellite, Hybrid (roadmap overlaid on satellite)
    or Terrain.

### Browse Map Settings


[![Brwsmap.png](https://omeka.org/c/images/d/d7/Brwsmap.png)](https://omeka.org/codex/File:Brwsmap.png)


-   Number of Locations Per Page. The Map browse has pagination.
-   Auto-fit to Locations. If checked, the browse map will ignore
    default location and zoom settings (from aobve) and instead auto fit
    to the locations of the items displayed.
-   Default Radius for the items advanced search.
-   Use metric distances for radius search.

### Item Map Settings


[![ItemMap.png](https://omeka.org/c/images/5/56/ItemMap.png)](https://omeka.org/codex/File:ItemMap.png)


You can set the width and height for the item map - if left blank, it
defaults to a width of 100% and a height of 300px.

### Map Integration


[![Mapint.png](https://omeka.org/c/images/c/cc/Mapint.png)](https://omeka.org/codex/File:Mapint.png)


-   Click the first checkbox to add a link to the items map on all
    items/browse pages.
-   Click the second checkbox to include an option for geolocating
    contribution items *Note* this will only work if you have the
    Contribution plugin installed and active.

Getting Started
---------------------------------------------------------------------

After you have activated and configured the Geolocation plugin, it is
time to geolocate some items.


[![Geolnav.png](https://omeka.org/c/images/c/c9/Geolnav.png)](https://omeka.org/codex/File:Geolnav.png)


When adding or editing an item (admin/item/edit and admin/item/add
pages), you will find a new Map tab. When adding metadata for an item,
click on the Map tab to add a location.

Enter the address of the item you wish to geolocate. A marker
automatically maps the selected address.

OR, Click directly on the map to place the item you wish to geolocate. A
marker automatically maps the selected site.


[![Geolchange.png](https://omeka.org/c/images/5/5d/Geolchange.png)](https://omeka.org/codex/File:Geolchange.png)


\

-   To change the location of an item, type in the new address. You'll
    be asked if you are sure you would like to change the item location.
    Select OK or Cancel.
-   Don't forget to save your changes.

Viewing Items on the Public Map 
-------------------------------------------------------------------------------------------------------

Visitors to your Omeka site may use a map to browse through all of your
geolocated items.

When configuring the plugin, if you selected "Add Link to Map on
Items/Browse Navigation," a "Browse Map" link will be added
automatically to the secondary navigation on the items/browse page.


[![Geolocmapnav.png](https://omeka.org/c/images/c/c5/Geolocmapnav.png)](https://omeka.org/codex/File:Geolocmapnav.png)


From this view, visitors may browse all mapped items, browse by tag,
search for items and browse the map.

They may also locate a mapped item by clicking on the items listed in
the right column of the map.

Browse and Search Items on Admin Map
----------------------------------------------------------------------------------------------------------------

A Map tab appears in the left navigation bar located on the left side of
the Dashboard. Clicking on the Map tab takes you to a map that displays
all items geolocated in your Omeka site--public and not public.


[![Geoladminbrowse.png](https://omeka.org/c/images/5/52/Geoladminbrowse.png)](https://omeka.org/codex/File:Geoladminbrowse.png)


-   From this view, you may also search mapped items using the item
    advanced search. Search results appear directly on the map.

