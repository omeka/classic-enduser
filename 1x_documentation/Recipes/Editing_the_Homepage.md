Editing the Homepage
====================

The home page for your Omeka installation is the first page users will
see when their visit your site. Omeka themes use the 'index.php' template file located at the root of your theme's folder for displaying
content on the home page. You can modify this template file to change
the display of content on your home page.

Structure of index.php 
-------------------------------------------------------------------------------------

In most of our publicly-available themes, we have taken lots of care to
add meaningful comments to template files to help you find where
specific content is generated. We've also used meaningful values for ID
and class attributes whenever possible.

Lets take a look at the index.php template file in the default theme:

``` {.de1}
<?php head(array('bodyid'=>'home')); ?>
 
<div id="primary">
 
    <!-- Featured Item -->
    <div id="featured-item">
        <?php echo display_random_featured_item(); ?>
    </div><!--end featured-item-->
 
    <!-- Featured Collection -->
    <div id="featured-collection">
        <?php echo display_random_featured_collection(); ?>
    </div><!-- end featured collection -->
 
    <!-- Recent Items -->     
    <div id="recent-items">
        <h2>Recently Added Items</h2>
 
            <?php set_items_for_loop(recent_items(10)); ?>
            <?php if (has_items_for_loop()): ?>
 
            <ul class="items-list">
                <?php while (loop_items()): ?>
 
                <li class="item">
                    <h3><?php echo link_to_item(); ?></h3>
 
                    <?php if($desc = item('Dublin Core', 'Description', array('snippet'=>150))): ?>
                        <div class="item-description"><?php echo $desc; ?></div>
                    <?php endif; ?>                       
                </li>
 
                <?php endwhile; ?>
            </ul>
 
            <?php else: ?>
                <p>No recent items available.</p>
 
            <?php endif; ?>
 
            <p class="view-items-link"><?php echo link_to_browse_items('View All Items'); ?></p>
 
    </div><!-- end recent-items -->
 
    <div id="recent-collections">
        <h2>Recent Collections</h2>
 
        <?php if (has_collections()): ?>
        <?php set_collections_for_loop(recent_collections(2)); ?>
 
        <ul class="collections-list">
            <?php while (loop_collections()): ?>
 
                <li class="collection">
                    <h3><?php echo link_to_collection(); ?></h3>
                    <p class="collection-description"><?php echo collection('Description', array('snippet'=>150)); ?></p>
                </li>
 
            <?php endwhile; ?>
        </ul>
 
        <?php else: ?>
 
        <p>No recent collections available.</p> 
 
        <?php endif; ?>
    </div><!-- end recent-collections -->
 
</div><!-- end primary -->
 
<?php foot(); ?>
```


This template file uses the [head](Theme_API/head.html "Theme API/head") helper function to prepend the contents of 'common/header.php' to the page, and [foot](Theme_API/foot.html "Theme API/foot") to append the contents of 'common/footer.php' to the page. These template files are used globally, throughout the rest of the theme.

Editing Structure of index.php
-----------------------------------------------------------------------------------------------------

Follow the directions below if you desire to edit or remove Featured Items, Collections, or Recently Added Items from the homepage.

### Adding an Image to the Homepage 

The best way to add an image to homepage is to add the img helper
function where you wish the image to appear in the index.php file of
your theme.

For more information, see [Theme\_API/img](Theme_API/img.html "Theme API/img")

### Featured Item 

The home page randomly displays any featured item you have marked in
your archive, or will return a sentence saying "No featured items are
available." The following markup is used to display the random featured
item; This uses the [display\_random\_featured\_item](Theme_API/display_random_featured_item.html "Theme API/display random featured item") theme helper.:

``` {.de1}
<!-- Featured Item -->
  <div id="featured-item">
    <?php echo display_random_featured_item(); ?>
  </div><!--end featured-item-->
```


Removing this entire block of code will get rid of the random featured
item.

To change the styles of this particular section of your homepage, find
any lines in your 'css/screen.css' file that use '\#featured-item' in
the property declaration.

### Featured Collection

The home page also randomly displays any featured collection you have
marked in your archive, or will return a sentence saying "No featured
collections are available." The following markup is used to display the
random featured collection; This uses the
[display\_random\_featured\_collection](Theme_API/display_random_featured_collection.html "Theme API/display random featured collection")
theme helper.:

``` {.de1}
<!-- Featured Collection -->
  <div id="featured-collection">
    <?php echo display_random_featured_collection(); ?>
  </div><!--end featured-collection-->
```

Removing this entire block of code will get rid of the random featured
collection.

To change the styles of your random featured collection, find any lines
in your 'css/screen.css' file that use '\#featured-collection' in the
property declaration.

### Recent Items and Collections

The home page also displays a list of the ten most recent items, and the two most recent collectons, added to your archive. The code that does this uses a number of Theme API helpers, all individually documented on our [Theme API](Theme_API.html "Theme API") codex page. If you take a look at the code used to generate recent collections, you'll notice that it uses very similar syntax to the recent items code explained here. You can also modify that code in similar ways. We'll just go over modifying recent items for simplicity.

The first part of the recent items section includes a heading for
'Recently Added Items', then uses [set\_items\_for\_loop](Theme_API/set_items_for_loop.html "Theme API/set items for loop")
and [recent\_items](Theme_API/recent_items.html "Theme API/recent items") to set the ten most recent items for a loop. It then checks to see if you in fact have recent items to display using the
[has\_items\_for\_loop](http://omeka.org/c/index.php?title=Theme_API/has_items_for_loop&action=edit&redlink=1 "Theme API/has items for loop (page does not exist)") helper:


``` {.de1}
<!-- Recent Items -->     
<div id="recent-items">
    <h2>Recently Added Items</h2>
    <?php set_items_for_loop(recent_items(10)); ?>
    <?php if (has_items_for_loop()): ?>
```


If you do have items to display, the home page lists those items in an
unordered list:


``` {.de1}
 
    <ul class="items-list">
    <?php while (loop_items()): ?>
        <li class="item">
            <h3><?php echo link_to_item(); ?></h3>
        <?php if($desc = item('Dublin Core', 'Description', array('snippet'=>150))): ?>
            <div class="item-description"><?php echo $desc; ?></div>
            <?php endif; ?>                       
    </li>
    <?php endwhile; ?>
    </ul>
```

You could easily use tags instead of an unordered list for displaying recent items, like so:

``` {.de1}
 
    <div class="items-list">
    <?php while (loop_items()): ?>
        <div class="item">
            <h3><?php echo link_to_item(); ?></h3>
        <?php if($desc = item('Dublin Core', 'Description', array('snippet'=>150))): ?>
            <div class="item-description"><?php echo $desc; ?></div>
            <?php endif; ?>                       
    </div>
    <?php endwhile; ?>
    </div>
```

If you don't have any recent items to display, the template will print
the statement 'No recent items available.' If you'd like to change the
message that is displayed if you have no recent items, edit the text
inside the paragraph near this bit of code:

``` {.de1}
    <?php else: ?>
    <p>No recent items available.</p>
    <?php endif; ?>
```

The list of recent items also includes a link to browse all the items at the bottom of the list, using this code:

``` {.de1}
    <p class="view-items-link"><?php echo link_to_browse_items('View All Items'); ?></p>
```

This will generate a link to the items/browse page, using the text 'View All Items' for the link. Changing the text inside the
[link\_to\_browse\_items](Theme_API/link_to_browse_items.html "Theme API/link to browse items") helper will change the text of the link.