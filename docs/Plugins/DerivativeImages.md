# Derivative Images

The [Derivative Images plugin](https://omeka.org/classic/plugins/DerivativeImages/){target=_blank} allows users to re-size fullsize, thumbnail, and square thumbnail images of selected file types for public and admin side displays. The Derivative Image plugin is particularly useful if image sizes of files already in Omeka must change when a new theme is selected, after an upgrade from an earlier Omeka Classic version, or after an upgrade of ImageMagick software.

Note that the Derivative Image plugin does not affect all file types. We highly recommended that you backup the archive directory before resizing images.

## Using the Derivative Image Plugin

After you have [installed](../Admin/Adding_and_Managing_Plugins.md) the plugin, Derivative Images is added to your left sidebar in the Admin view.

- Open the plugin in the Nav sidebar to configure the dimensions of fullsize, thumbnail, and square thumbnail images in Omeka.
- **Process type** allows you to decide whether to resize all files, files that only have derivative images, or files that have no derivative images.
- **Image Sizes** allows you to decide whether to reconfigure your fullsize, thumbnail, and/or square thumbnail images to correspond to the image sizes you designated when you configured your theme in Appearance settings. All image sizes are selected by default, or you may select any combination of images to resize through selecting multiple checkboxes.
- **Mime types** allows you to determine the kinds of files you resize. All file types are selected by default, or you may select any combination of MIME types to resize through selecting multiple checkboxes.
- When you have created your selections, select process files for re-sizing to take effect.

