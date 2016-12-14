---
title: Default Item Thumbnail Images
---
*This documentation for Omeka versions up to 1.5 only*

Date written: 2011

I wanted to make a gallery of images for the browse page, but I had a number of items without images and wanted a uniform look.

Solution
---------------------------------------------------------

I changed the item links to show a default image if there wasn't a
thumbnail for the item. For variety, I assigned thumbnails for different
items by item type as well.

### Functions Used

-   [link\_to\_item()]()
-   [img()]()
-   [item\_has\_type()]

By default the items browse page (items/browse.php) displays the item thumbnail, title, description and tags.


``` {.de1}
<?php while (loop_items()): ?>
    <div class="item hentry">
        <div class="item-meta">
        <?php if (item_has_thumbnail()): ?>
            <div class="item-img">
                <?php echo link_to_item(item_square_thumbnail()); ?>              
            </div>
    <?php endif; ?>
 
            <h2><?php echo link_to_item(item('Dublin Core', 'Title'), array('class'=>'permalink')); ?></h2>
 
        <?php if ($text = item('Item Type Metadata', 'Text', array('snippet'=>250))): ?>
            <div class="item-description">
                <p><?php echo $text; ?></p>
            </div>
        <?php elseif ($description = item('Dublin Core', 'Description', array('snippet'=>250))): ?>
            <div class="item-description">
                <?php echo $description; ?>
            </div>
        <?php endif; ?>
 
        <?php if (item_has_tags()): ?>
            <div class="tags"><p><strong>Tags:</strong>
                <?php echo item_tags_as_string(); ?></p>
            </div>
        <?php endif; ?>
 
        <?php echo plugin_append_to_items_browse_each(); ?>
 
        </div><!-- end class="item-meta" -->
    </div><!-- end class="item hentry" -->            
<?php endwhile; ?>
```

I only want the thumbnail and title, so I removed everything else.

``` {.de1}
<?php while (loop_items()): ?>
    <div class="item hentry">
        <div class="item-meta">
        <?php if (item_has_thumbnail()): ?>
            <div class="item-img">
                <?php echo link_to_item(item_square_thumbnail()); ?>                      
            </div>
    <?php endif; ?>
 
            <h2><?php echo link_to_item(item('Dublin Core', 'Title'), array('class'=>'permalink')); ?></h2>
 
            <?php echo plugin_append_to_items_browse_each(); ?>
 
        </div><!-- end class="item-meta" -->
    </div><!-- end class="item hentry" -->            
<?php endwhile; ?>`
```


First I assigned a default image for any item without a thumbnail.

``` {.de1}
<div class="item-img">
<?php 
if (item_has_thumbnail()):
    echo link_to_item(item_square_thumbnail());
else:
    echo link_to_item('<img src="'.img('default_icon.jpg').'" />');
endif;
?>
</div>
```

This else statement changes the link text in the link\_to\_item() function.

If the item does not have a thumbnail, the item link 'text' is the image 'default\_icon.jpg'. The img() function uses files uploaded to my themes images folder. (MyOmekaInstall/themes/MyTheme/images)

The item\_square\_thumbnail()  function prints an img src tag for the thumbnail, but the img() function does not. So, I had to made a string for the img src. If you were using this often, you may want to make your own custom function for default images. 

Next, I added defaults for documents, videos, and audio.

``` {.de1}
<div class="item-img">
<?php
if (item_has_thumbnail()):
    echo link_to_item(item_square_thumbnail());   
elseif (item_has_type('Document')):
    echo link_to_item('<img src="'.img('document_icon.jpg').'" />');
elseif (item_has_type('Moving Image')):
    echo link_to_item('<img src="'.img('video_icon.jpg').'" />');
elseif (item_has_type('Sound')):
    echo link_to_item('<img src="'.img('audio_icon.jpg').'" />');
else:
    echo link_to_item('<img src="'.img('default_icon.jpg').'" />');
endif;
?>
</div>
```


Warning: If you do not have the files uploaded or do not have the right names for files when you use them in the img() function, you will receive an error in Omeka.

Also, item\_has\_type() uses items that are assigned an item type in the admin panel of Omeka,
it does not determine the item type by the uploaded file type.

