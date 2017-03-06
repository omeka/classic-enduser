---
title: Browsing Items Alphabetically
---
Patrick Murray-John, July 2012

Problem
-------------------------------------------------------
Instead of browsing items by the order of their id, I want to browse alphabetically by title.

Solution 1
-------------------------------------------------------------

This can be done by configuring your theme to use custom header
navigation, and adding a sort field to the items browse page.

Under Settings-Themes, hit the Configure button and look for the
Custom Header Navigation field.

This will override the default navigation, so you'll need to recreatethe navigation for collections, exhibits, and other stuff from plugins(e.g. Simple Pages). Then add something special for Browse Items.

Here's what I put into my custom header navigation:

``` {.de1}
Browse Items | items?sort_field=Dublin Core,Title
Browse Collections | collections
Browse Exhibits | exhibits
```

For collections and exhibits, this just recreates the URL as usual. For items, though, the additional part does the sorting. Change 'Title' to whatever for a different field.

Solution 2
-------------------------------------------------------------
Solution 1 is swell, but the pagination still goes numerically. I need an alphabetical index.

This calls for a little more trickery. We'll build a simple plugin that uses the hook into the item browse sql.

The basic plugin.php file will look like this:

``` {.de1}
<?php
add_plugin_hook('item_browse_sql', 'myplugin_item_browse_sql');
function myplugin_item_browse_sql()
{
//our code will go here.
}
?>
```

You'll also need the php.ini file to go along with the plugin. See [Plugin Writing Best Practices](../1x_documentation/Plugin_Writing_Best_Practices.md) for details

The function itself follows the pattern of Omeka's internal code thatmakes the above solution work, but adds the letter that the title shouldstart with as a third component. And so, we'll end upputting `?starts\_with=Dublin Core,Title,A` in the URL to get the titles beginning with A.

Here's the full code:

``` {.de1}
add_plugin_hook('item_browse_sql', 'myplugin_item_browse_sql');
 
function myplugin_item_browse_sql()
{
$sortDir = 'ASC';
$db = get_db();
if ($request = Zend_Controller_Front::getInstance()->getRequest()) {
  $startsWithString = $request->get('starts_with');
  if(!empty($startsWithString)) {
      $startsWithData = explode(',', $startsWithString);
  }            
}
 
if(!startsWithData) {
  $startsWithData = isset($params['starts_with']) ? explode(',', $params['starts_with']) : false;
}
if($startsWithData) {
  //ItemTable builds in a order by id, which we don't want
  $select->reset('order');
 
  //data like 'Element Set', 'Element', 'Character'
  if(count($startsWithData) == 3) {
      $startsWith = $startsWithData[2];
      $element = $db->getTable('Element')->findByElementSetNameAndElementName($startsWithData[0], $startsWithData[1]);
      if ($element) {
    $recordTypeId = $db->getTable('RecordType')->findIdFromName('Item');
    $select->joinLeft(array('et_sort' => $db->ElementText),
      "et_sort.record_id = i.id AND et_sort.record_type_id = {$recordTypeId} AND et_sort.element_id = {$element->id}",
      array())
      ->where("et_sort.text REGEXP '^$startsWith'")
      ->group('i.id')                                    
      ->order("et_sort.text $sortDir");
      }                
  } else {
      throw new Exception("Starts With data must be like 'Element Set', 'Element', 'Character' ");
  }
}
 
}
```


That lets us use a url like: items?starts\_with=Dublin Core,Title,A

Now we just need to add the alphabetical list of links to the theme's browse page. This is easily done by looping through the alphabet to build the links we need.



``` {.de1}
<?php $letters = array('A', 'B', 'C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z') ;?>
<ul class='pagination_list'>
<?php foreach($letters as $letter): ?>
<li class='pagination_range'>
    <a href='<?php echo uri("items?type=Commentator&starts_with=Dublin Core,Title,$letter"); ?>'><?php echo $letter?></a>
</li>
<?php endforeach; ?>
 
</ul>
```


Putting this at the top of your browse page will produce your index. Use the theme configuration from Solution 1 to make 'A' the page that the browse link goes to.

### A few notes

If you leave the pagination links in the browse page, then records will still be paginated by that letter. E.g., 50 items beginning with the letter 'A' will be broken up into 5 pages. You can change this behavior in the theme configuration by adjusting how many items to show on the browse page. Making that big enough that the pagination doesn't happen will work, but for a site with many items could cause problems.

This does nothing to group letters together, or skip letters that don't have records. The page for 'Q' will show an empty page if no items have a title beginning with 'Q'


### Functions Used

-   [uri()](../Functions/uri.html "Functions/uri")
-   [item\_browse\_sql()](../Hooks/item_browse_sql.html "Hooks/item browse sql")