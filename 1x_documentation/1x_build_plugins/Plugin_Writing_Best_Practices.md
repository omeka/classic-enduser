Plugin Writing Best Practices
=============================


The following is a guide for best coding practices when developing Omeka
plugins. Separated into two sections, it covers the proper [naming
conventions](Plugin_Writing_Best_Practices.html#Name_your_plugin) for
plugin development, and the [directory structure and
files](Plugin_Writing_Best_Practices.html#Plugin_Directory_Structure) in
your plugin. In addition to these best practices, the [Plugin
Development Use
Cases](Plugin_Development_Use_Cases.html "Plugin Development Use Cases")
page guides you through the process adding specific features to your
plugin.

Name your plugin
-------------------------------------------------------------------------

In this case, by "name" we mean the name of the directory where your
plugin files will go. It is important to name your plugin concisely yet
adequately, and with proper formatting. Follow these rules when naming
your plugin:

-   **Unique**: the name should not conflict with an existing
    plugin name.
-   **Simple**: the name should be concise and to-the-point.
-   **Descriptive**: the name should describe your plugin to a
    certain degree.
-   **CamelCased**: the name should contain no spaces and the first
    character of every word should be capitalized.

Naming your plugin appropriately is important because it is used
throughout the system as a unique identifier to your plugin. It is also
used in the naming scheme of controllers, models, and other components
in your plugin.

In the plugin.ini file you may name your plugin differently from above,
but that is not recommended unless the names are similar enough not to
be confused.

Plugin Directory Structure
---------------------------------------------------------------------------------------------

Every plugin may follow the directory structure outlined below:

-   **MyPlugin/** (folder)
    -   *plugin.ini*
    -   *plugin.php*
    -   **models/** (folder)
    -   **controllers/** (folder)
    -   **views/** (folder)
        -   **admin/** (folder)
        -   **public/** (folder)
        -   **shared/** (folder)

For those familiar with [Zend Framework](http://framework.zend.com), you
may recognize that Omeka plugins work as modules -- that is,
self-contained applications resting on top of the Omeka system. This is
an important detail that will become apparent the more complicated your
plugin becomes.

But for now, let's look at the directory components individually.

### MyPlugin/plugin.ini 

The plugin.ini file contains information about your plugin. It uses
PHP's configuration file format. All values should be in quotes:


``` {.de1}
[info]
; The plugin's name.
name = "My Plugin"
 
; The name of the plugin's author.
author = "My Name"
 
; A short description of the plugin.
description = "The plugin does this, that, and the other thing."
 
; The software license the plugin is released under.
license = "GPLv3"
 
; A URL for information or documentation about the plugin.
; This could be a page on the Omeka Codex, or some other page.
link = ""
 
; A URL where users should go to get support or report issues.
support_link = ""
 
; The version number of the plugin.
; Omeka uses this to determine when a user has upgraded a plugin.
version = "0.5"
 
; The minimum version of Omeka needed to run the plugin.
omeka_minimum_version = ""
 
; The latest version of Omeka that this plugin was tested or run against.
omeka_tested_up_to = ""
 
; The directory names of any other plugins that *must* be installed.
; (Separate mulitple plugin names with commas)
required_plugins = "SomePluginName, SomeOtherPluginName"
 
; The directory names of any other plugins that enable extra functionality.
; (Separate multiple plugin names with commas)
optional_plugins = "AnotherPluginName, YetAnotherPluginName"
```


Upcoming versions of Omeka will switch to using omeka\_target\_version
instead of omeka\_tested\_up\_to. These changes are part of the
mechanism to let you add our plugins to our listing at
omeka.org/add-ons/plugins.

### MyPlugin/plugin.php 

The plugin.php file is the main script of your plugin. It contains a set
of constants, plugin hooks, filters, helper functions, includes, and
other baseline code needed for your plugin.

The script should begin with a descriptive comment at the top that lets
others know what your plugin does. As with all code in Omeka, we
recommend that you comment and document your code using the
[phpDocumentor](http://www.phpdoc.org/) standard.

#### Constants 

Constants are always uppercase, separated by underscores, per Zend
coding standards.

``` {.de1}
<?php define('MYPLUGIN_CACHE_DIR', '/foo/bar/cache'); ?>
```

#### Naming conventions for Hooks and Filters 

For useful information on how to use plugin hooks and filters, see the
[Plugin\_API](Plugin_API.html "Plugin API") page.

Names for plugin hook callback functions should always be lowercased,
separated by underscores, and unique. To ensure uniqueness, try
prefixing your function names with the name of your plugin. For example:


``` {.de1}
<?php
add_plugin_hook('install', 'myplugin_install');
function myplugin_install()
{
  // Set version number, create database tables, other installation needs.
}
?>
```



Starting in Omeka 1.5, there is an Omeka\_Plugin\_Abstract class
available that can simplify things:



``` {.de1}
class MyPlugin extends Omeka_Plugin_Abstract
{
    protected $_hooks = array('install');
 
    public function hookInstall()
    {
       //do your install work here
    }
}
 
$myplugin = new MyPlugin();
$myplugin->setUp();
```


The hooks that you declare you are using in the \$\_hooks array must
have a corresponding public method of the form hook{Hookname} as above.

### MyPlugin/models 

In more complex plugins, the models/ directory may contain classes that
allow for simplified interaction with the database. These classes should
extend Omeka\_Record, which is a loose implementation of the
ActiveRecord pattern.

Each of these classes corresponds to a table in the Omeka database and,
like all classes, should be given a unique name to prevent potential
naming conflicts with other plugins.

#### Record class 

Your record will correspond to a table in the database that has the
pluralized, lowercase name of your record. For example, a User class
would correspond to a users table, a SimplePage class would correspond
to a simple\_pages table, etc. You can override this convention by
setting the name of the table in a Table class.

-   **File name**: `UniqueName.php`
-   **Class definition**: `UniqueName extends Omeka_Record {}`

#### Table class (optional)

This is not required in most cases. The two most important use cases are
if you need the name of your database table to be different from your
record class name as mentioned above, or if you need customized behavior
for your table class. If neither of these apply to you as a plugin
writer, skip this section for now.

-   **File name**: `UniqueNameTable.php` (Must be the same as the record
    class, with 'Table' appended)
-   **Class definition**: `UniqueNameTable extends Omeka_Db_Table {}`

### MyPlugin/controllers 

-   **File name**: `ControllerName.php`
-   **Class definition**:
    `PluginName_ControllerName extends Omeka_Controller_Action {}`
    -   For more information about how controllers operate within the
        Zend Framework, please see the
        [documentation](http://framework.zend.com/manual/en/zend.controller.html).

###  MyPlugin/views 

-   Contains the following subdirectories: admin/, public/ and shared/

Each of these directories contains [view
scripts](http://framework.zend.com/manual/en/zend.controller.html#zend.controller.quickstart.go.view)
that follow the convention:
views/admin/lowercased-controller-name/action-name.php. For example, if
you had a MyPlugin\_IndexController with a
[fooAction()](http://framework.zend.com/manual/en/zend.controller.html#zend.controller.quickstart.go.controller),
the view script for that action would be located at
omeka-site/plugins/MyPlugin/views/admin/index/foo.php.

