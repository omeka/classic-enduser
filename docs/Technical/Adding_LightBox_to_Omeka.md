# Adding Lightbox to Omeka

!!! note
	Omeka Classic now uses the lightGallery image viewer to display files. This is used on many pages across most of the Omeka-authored themes. Older versions did not use embedded image viewers, and users supplied gallery tools such as Lightbox using the instructions below. You can still use the following method to use Lightbox instead of lightGallery, or in older versions of Omeka, so these instructions are preserved for legacy use.

### Step One: Get the Lightbox package

The first step is to [download the latest Lightbox package](http://lokeshdhakar.com/projects/lightbox2){target=_blank}, where you will find a quick explanation of how it works and how to get started. (As of November 2024, the last tested version is [v2.11.5](https://github.com/lokesh/lightbox2/releases/tag/v2.11.5) from Oct 2024.)

### Step Two: Modify and move the Lightbox package

Once you have the package, unzip it so you can move the files into the correct places in your theme's directory. We will need to move the `images` folder, the `lightbox.js` file, and the `lightbox.css` file to the correct places in your theme's folder.

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

In your theme's configuration, make sure that the "Item File Gallery" option is checked.