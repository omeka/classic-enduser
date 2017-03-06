---
title: MVC Pattern and URL Paths in Omeka Classic 1x
---
*This documentation for Omeka Classic versions up to 1.5 only*

Model-View-Controller pattern
----------------------------------------------------------------------

The Model-View-Controller pattern is designed to help manage the tasks of describing an object in the database (Model), managing the retrieval and manipulation of that data (Controller), and formatting it for display (View). Keeping these three areas separate makes it easier to understand, maintain, and develop your code. Not every plugin will need to make use of this architecture, but for complex tasks it is essential to understand.


![Diagram of MVC](../1x_documentation/1xdocs_images/MVC_Diagram.jpg) CC-BY BlueSky23 on Wikipedia


A Model usually corresponds to the data you are storing in the database for a particular kind of object. So, we have Models for Users, Items, Collections, etc., and plugins can define their own Models as needed. Think of the Model as just the core data representing the thing you are working with -- the stuff in the database.

Directing what happens with that data when a request is made to the site is the job of the Controller. Depending on the request, the Controller will handle retrieving the data from the database, manipulating it if necessary, and passing it on to the appropriate View for display.

In Omeka, Controllers have methods called action-methods. Each Action corresponds to a particular View, which handles the display to the user.

URL Paths 
-----------------------------------------------------------

### Basic Pattern 

If you have a controller at MyPlugin/controllers/IndexController.php:

- admin/my-plugin will perform the controller's indexAction(), and will be looking for a view at views/admin/index/browse.php (or
views/shared/index/browse.php).

There's special rules for the index controller and index action that allow you to omit parts of the URL, but in general the pattern for is:

`admin/my-plugin/controller-name/action-name`

for which the corresponding view is at

`MyPlugin/views/admin/controller-name/action-name.php`

Note: You need to have an action method (actionNameAction) implemented in your controller class for each "page" you want. This may have been the piece you were forgetting.

There are quite a few ways to vary from these patterns, but these are the basic mappings you get by default.

### Variations

#### Multiple Controllers 

Sometimes a plugin needs multiple controllers (e.g., when it works with
multiple Models). In that case, the url paths might look like:

-   controllers/
    -   ContributionController.php
    -   ContributorMetadataController.php
    -   ContributorsController.php
    -   IndexController.php
    -   SettingsController.php
    -   TypesController.php
-   views/
    -   admin/
        -   contributor-metadata/
        -   contributors/
        -   index/
        -   settings/
        -   types/
    -   public/
        -   contribution/

Notice that the controller names are all CamelCased corrolaries to directories under the views. If we go one level down, to the php files in those directories:

-   views/
    -   admin/
        -   contributors/
            -   browse.php
            -   show.php

The names of those files further correspond to names of Actions in the appropriate Controller: ContributorsController will have methods called browseAction() and showAction().

