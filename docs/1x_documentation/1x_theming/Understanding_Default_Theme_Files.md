---
title: Understanding Default Theme Files
---
*This documentation for Omeka versions up to 1.5 only*


Many projects call for some amount of seasoning your public display to taste. Maybe you need to display an additional piece of metadata on the item browse pages, or you want to make a minor rearrangement to the content.

The natural first step is to start looking in your theme's files, where you might see a folder and directory structure like:

`    {your-theme}
    -items
    --show.php`

This corresponds to what you will see at /items/show/{item-id}.

Straightforward enough. But it comes as a surprise, then, that there seems to be no file that corresponds to /items/browse. One would have expected to see it at

    {your-theme}
    -items
    --browse.php

but it isn't there.

That is because if Omeka does not see the expected file, it falls back to default theme files. These can be found at

    {omeka-root}
    -application
    --views
    ---scripts

There, you will see subdirectories for items, collections, and more. Comparing the fallback code with the code in many of the themes for Omeka, you will see that we rely on the fallback mechanism extensively.

The upshot is that if you want to make an adjustment to a part of Omeka's public display, but it seems that the file you need is not present, you might need prevent the fallback behavior from happening.

To do that, you need only copy the fallback file from
`/application/views/scripts` into the corresponding directory in your theme. For example, if you want to customize the display for the browse collections page, you would create the collections directory in your theme if it does not exist, the copy `/application/views/scripts/collections/browse.php` into that directory, and start editing away!
