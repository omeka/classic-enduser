Sorting Results
===============
Since version 1.3, Omeka has built-in support for sorting the results of browse and search actions. The most obvious place you can see this new functionality is on the admin-side items/browse page, where you can now sort the results by each column.

Sorting is available on the admin and public interfaces, and works with any Omeka object.

Sorting Parameters
-----------------------------------------------------------

Omeka's sorting functionality is activated and configured by two parameters: `sort_field` and `sort_dir`.

`sort_field` controls what field the results will be sorted by. If this parameter is omitted, no sorting will occur. For all Omeka objects, the available fields include every database column stored for that type of object. In addition, Items can also be sorted by their element texts.

`sort_dir` controls what direction the results will be sorted in. The available settings are "a" for ascending order, and "d" for descending order. If this parameter is omitted, the results will be sorted in ascending order.

URL-based Sorting
---------------------------------------------------------

All "browse" pages in Omeka (items/browse, collections/browse) will respond to the inclusion of the above parameters in the URL's query string.

The [uri](Functions/uri.md) helper and the other helpers that create links and URLs can build the query string for you.

For example, to sort items by Dublin Core Title on the items browse page, you want to set the `sort_field` parameter to `Dublin Core,Title`. To generate this link you could use the `link_to_browse` items helper:

```
<?php
    echo link_to_browse_items('Sorted by Title', array('sort_field' => 'Dublin Core,Title'));
?>
```

For views that present the results in a table (like the majority of the admin interface), Omeka includes a helper called `browse_headings` that can automatically create the appropriate links to enable sorting.

Backend Sorting
--------------------------------------------------------

Plugin or theme writers who are manually fetching items or other objects can also use the sorting functionality.

The `get_items` helper (as well as related helpers like
`get_collections`) also support the same parameters listed above when passed in the `$params` array.

As a technical matter, sorting is applied by the `findBy` method of a table object, so any helper functions that use `findBy` can provide sorted results.

Extending Sorting
--------------------------------------------------------

While all Omeka Record model objects can be directly sorted by their database columns, plugin developers may want to allow more complicated sorting. For any table object, you can override the `applySorting` function to enable custom sorting (or disable the default sorting).

The ItemTable class extends the default sorting in this way to allow items to be sorted by their element texts.