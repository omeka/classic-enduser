Plugin API
==========



In Omeka, plugins have access to the
[functions](Functions.html "Functions") used by themes as well as the
core Omeka software and Zend Framework's functionality. Omeka also
provides two additional features for plugin developers:
[Hooks](Hooks.html "Hooks") and [Filters](Filters.html "Filters").

[Hooks](Hooks.html "Hooks")
-------------------------------------------------------------------------

Hooks are the primary ways your plugin can modify the behavior of Omeka.
The add\_plugin\_hook() function contains two arguments:

1.  The name of the hook, which will run at a predefined time during an
    Omeka process. See below for some often used hooks.
2.  The name of your custom function (called a callback) that will be
    run at the specified time. It is important to ensure that your
    callback function is named uniquely, so we recommend prefixing your
    plugin name to the callback name.


``` {.de1}
<?php add_plugin_hook('hook_name', 'plugin_name_callback_name'); ?>
```



``` {.de1}
<?php add_plugin_hook('install', 'myplugin_installer'); ?>
```

[Filters](Filters.html "Filters") 
---------------------------------------------------------------------------------

Filters are like hooks except they are used to modify existing data in
Omeka rather than add new behaviors.

An example of a filter:

``` {.de1}
add_filter('admin_navigation_main', 'my_plugin_admin_navigation');
function my_plugin_admin_navigation($tabs)
{
  $tabs['Foobar'] = uri('foobar');
  return $tabs;
}
```


Note a few things from this example: The data to be filtered is always
received as the first argument to the callback. That data must then be
returned by the function in order for the filter to work properly. In
this example, 'admin\_navigation\_main' is the name of the filter
corresponding to the top-level navigation for the admin theme, and
\$tabs is a predefined array of navigation elements. This example will
add a link to the admin navigation with the text 'Foobar', and the URI
that is generated will be something like /omeka-site/admin/foobar.

