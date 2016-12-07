---
title: Browse Within A Collection
---
AOrdine, 2011

Problem
---------------
There are many ways to sort and browse items in Omeka, but I wanted to be able to have users browse collection items by item type in when visiting each collections page.

Solution
---------------------------------------------------------

I created a sub-navigation on the collection show page.

### Functions Used

-   [nav()](../Functions/nav.html "Functions/nav")
-   [uri()](../Functions/uri.html "Functions/uri")
-   [collection()](../Functions/collection.html "Functions/collection")


``` {.de1}
<h3>Browse Collection Items by Type</h3>
<div class="collection-nav">
<?php 
echo nav(array('Images' => uri('items?collection='.collection('id').'&type=6'), 
'Documents' => uri('items?collection='.collection('id').'&type=1'),
'Audio' => uri('items?collection='.collection('id').'&type=4'), 
'Video' => uri('items?collection='.collection('id').'&type=2'))); 
?>
</div>
```


This creates a navigation where which links to an items browse page that displays items from the current page's collection, collection('id'), and according to the item type. Note: This does find the current collection, so it can only be used after a collection is set.

Variations
-------------------------------------------------------------
You could show browse results by many parameters, for example by tag:


``` {.de1}
<h3>Browse Collection Items by Tag</h3>
<div class="collection-nav">
<?php 
echo nav(array('Civil War' => uri('items?collection='.collection('id').'&tags=Civil War'), 
'Reconstruction' => uri('items?collection='.collection('id').'&tags=Reconstruction'),
'WWI' => uri('items?collection='.collection('id').'&tags=World War I'), 
'WWII' => uri('items?collection='.collection('id').'&tags=World War II')));
?>
</div>
```


If you would like to get ideas for a custom navigation you can do an advanced search. It outputs a long string, like this search for items with the date 1963:

```yoursite.org/items/browse?search=&advanced[0][element_id]=40&advanced[0][type]=contains&advanced[0][terms]=1963&range=&collection=&type=&user=&tags=&public=&featured=&submit_search=Search```

But you can eliminate the empty fields for your link and use something like this:

``` {.de1}
<?php
echo nav(array(
'1963' => uri('items?&advanced[0][element_id]=40&advanced[0][type]=contains&advanced[0][terms]=1963'),
'1964' => uri('items?&advanced[0][element_id]=40&advanced[0][type]=contains&advanced[0][terms]=1964')));
?>
```