Plugins/PageCaching
===================


[Plugins](../Plugins.1.html "Plugins")


The Page Caching plugin provides basic page caching for Omeka, allowing
your site's web pages to load faster from a cached version.

\

Installation 
-----------------------------------------------------------------

1.  Upload and install the Page Caching plugin (see
    [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin"))
2.  Configure the plugin in Omeka (see below)

Configuration 
-------------------------------------------------------------------

-   **Automatically Clear Page Cache After Record Change**: Check
    whether to automatically clear the page cache after any record, such
    as an item or collection, is saved. This means that the entire
    cache - not just the cache for a single page - will be cleared when
    just a single record is changed. So you should only check this
    option if your site is relatively static, and not updated
    that often. If you leave it unchecked, you will need to manually
    clear your cache with the Clear Cache button on your
    admin dashboard.

<!-- -->

-   **Cache Lifetime**: The amount of time (in seconds) to keep the
    cache before automatically expiring it.

<!-- -->

-   **Cache Backend Type**: The cache backend type. Normally, the cached
    pages are stored as files on filesystem; this is the
    "Filesystem" backend. For advanced users, the plugin also supports
    APC, Memcached, and XCache. To set these options, you will need to
    edit the cache\_settings.ini file.

<!-- -->

-   **Cache Directory Path**: The path to the cache directory on
    the filesystem. This directory must be readable and writeable. This
    setting only applies if you use the Filesystem cache backend type.

<!-- -->

-   **Cache Blacklist**: This is an advanced setting, used to prevent
    certain pages from being cached. For example, if you have a page
    that has randomly generated content, you probably should not
    cache it. To blacklist pages, on each line, specify a regular
    expression for any relative URIs you do NOT want cached. For
    example, if you want to blacklist all the items pages, you would put
    "/items" on a line by itself.

If you just wanted to blacklist the homepage, you could put "/\$" on a
line by itself.

-   **Enable Debugging**: This setting is an advanced setting to test if
    page caching is working. If enabled, a DEBUG message will appear on
    each page that is being cached. This is useful when tweaking the
    plugin settings to make sure it behaves correctly. You probably
    should not use it on a production site unless you are ok if your
    users see the debug message.

Manually Clearing The Cache
-----------------------------------------------------------------------------------------------

If you want to manually clear the cache on your site, goto the admin
dashboard (the main admin page), and look in the lower right region of
the page, where the Page Caching subsection is located, and then click
the "Clear Page Caching" button.

If you have made some changes to your site and expect to see new
content, but do not see it, it may be showing the cached content. To fix
this, just click the "Clear Page Caching" button, and it should clear
the cache. Alternatively, if you have a relatively static site, or if
you infrequently make changes to it, you could edit your Page Caching
plugin settings and check the 'Automatically Clear Page Cache After
Record Change' checkbox.
