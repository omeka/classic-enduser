# Adding Lightbox to Omeka

### Step One: Get the Lightbox Package

The first step is to [download the latest LightBox 2 package](http://lokeshdhakar.com/projects/lightbox2){target=_blank}, where you will find a quick explanation of how it works and how to get started. (The last tested version is [v2.11.5](https://github.com/lokesh/lightbox2/releases/tag/v2.11.5) from Oct 24.)

### Step Two: Modify and Move the LightBox Package

Once you have the package, unzip it so you can move the files into the correct places in your themes directory. We will need to move the `images` folder, the `lightbox.js` file, and the `lightbox.css` file to the correct places in your theme's folder.

The needed files are located in the `src/` folder. (eg. `src/js/lightbox.js`)

- **images:** Move the entire folder to your theme's top directory. *(Alternatively, you could upload the images to your theme's */images* directory, and modify the *lightbox.css* stylesheet to look for them there.)*

- **lightbox.js:**  Move the file to `yourtheme/javascripts/vendor/`.

- **lightbox.css:** Move the file to `yourtheme/css/`.

### Step Three: Modify your items/show.php file

In the `yourtheme/items/show.php` file, add the following as the first line (before the line that begins `<?php echo head(`

```php
<?php 
queue_js_file('lightbox-2.6.min', 'javascripts/vendor');
queue_css_file('lightbox');
?>
```

Look for the line that calls `item_image_gallery`, and modify it so it looks like this:

```php
<div class="element-text"><?php echo item_image_gallery(array('link'=>array('data-lightbox'=>'lightbox'))); ?></div>
```

In your theme's configuration, make sure that the Item File Gallery option is checked.
