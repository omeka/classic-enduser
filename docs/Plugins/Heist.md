# Heist

[Heist](https://omeka.org/classic/plugins/Heist/){target=_blank} is a plugin designed to work with installations of [Omeka Everywhere](http://omeka.org/everywhere/){target=_blank}. This plugin facilitates connections between multi-touch devices running the Omeka Everywhere Collection Viewer and mobile devices with the Omeka Everywhere Mobile App.

This plugin is only useful for organizations and individuals running Omeka Everywhere and Omeka Classic.

## Activation

Heist has no configuration options. Simply install and activate. You can install Heist before or after setting up your Omeka Everywhere Collection Viewer and/or Mobile App instances. 

## Using Heist
In order to use Heist, you must have a mobile device with the Omeka Everywhere app installed ([Android](https://play.google.com/store/apps/details?id=org.ideum.omeka&hl=en_US){target=_blank} and [iOS](https://itunes.apple.com/us/app/omeka-everywhere-mobile/id1313430701?mt=8){target=_blank}) and access to a touch-enabled device running Omeka Everywhere Collection Viewer. 

From the Collection Viewer, visitors click the Send to Mobile button on their dock. This will open up a side window with a QR code.

![Zoomed in on a Collection Viewer dock, we see the upper right corner of the dock and a button reading Send to Mobile](../doc_files/plugin_images/heist-sendmobile.png)

![The same dock as before, now with a new window to the right of it displaying a QR code](../doc_files/plugin_images/heist-sendmobile2.png)

Next, the visitor opens the app on their phone and clicks the gear in the upper right corner of the home screen to open the Settings. 

![A red arrow points to the gear icon above the Omeka logo in the mobile app home screen](../doc_files/plugin_images/heist-mobile1.png)

From there they select the Pair with Collection Viewer Table button.

![The settings screen of the mobile app, consisting of six white buttons on a gray background. The third button from the top has a red arrow pointing to it.](../doc_files/plugin_images/heist-mobile2.png)

At this point they may need to give the app permission to use the camera. The app will open a camera view through which they can scan the QR code on the table, which should complete the pairing.

Once paired, visitors can save items from the Collection Viewer to their app by dragging and dropping the item from the active area of the table to the pairing point in their dock on the table. 
