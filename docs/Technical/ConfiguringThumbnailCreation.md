# Configuring Thumbnail Creation


## Choosing a Strategy

Omeka Classic uses the command-line tool `convert` from ImageMagick by default to create thumbnail images for uploaded files. Instead, you can choose to use the PECL ext/imagick extension (Omeka 2.2 and above) or the PHP GD extension (Omeka 2.3 and above).

The Imagick and GD options both avoid the need to call out to a command-line. PHP's GD extension is less advanced than ImageMagick but is more widely available.

To change how Omeka will generate thumbnails, set the option `fileDerivatives.strategy` in the application/config/config.ini file. Note: there may be a `fileDerivatives.strategy` line already in the config.ini file. If that line starts with a semicolon, it is a comment, not an actual setting. Either remove the semicolon and edit the line to use the desired strategy, or just add a new line.

To use the GD strategy, use the following line:

`fileDerivatives.strategy = "Omeka_File_Derivative_Strategy_GD"`

To use the IMagick strategy, use the following line:

`fileDerivatives.strategy = "Omeka_File_Derivative_Strategy_Imagick"`

The new strategy will only apply to files added to Omeka after the configuration is changed.

## Changing Options

In addition to the entire strategy used to create the thumbnails, more fine-grained options are also configurable in application/config/config.ini.

Options are set using lines starting with
`fileDerivatives.strategyOptions`.

### Gravity 

The `gravity` option lets administrators specify which region of an image to keep when creating a square thumbnail. The possible options are compass directions (north, south, east, west, northeast, northwest, southeast, and southwest), and the default, center.

Directions that contain "north" or "south" will use the topmost or bottom-most portion, respectively of portrait-oriented images. Directions containing "west" or "east" will use the leftmost or rightmost portion, respectively, of landscape-oriented images. A setting of "center" or no setting will use the center of the image.

For example, to always make square thumbnails using the topmost part of the uploaded image, set the following line:

`fileDerivatives.strategyOptions.gravity = "north"`

### Page

The default external ImageMagick strategy can switch which "page" of an image to use when creating a thumbnail. The "page" could correspond with actual pages for documents like PDFs, or to frames of an animation or video. The page numbers start at 0, so 0 is the first page, 1 is the second page, and so on. By default, Omeka uses page zero, the first page.

For example, to use the second page when creating thumbnails, set the following line:

`fileDerivatives.strategyOptions.page = 1`

### Version 

When using the default external ImageMagick strategy, you can optionally inform Omeka which version of ImageMagick is being used. If it is recent enough, Omeka can switch to creating square thumbnails in a way that is more efficient and produces better results, particularly for images that are much longer in one dimension than the other. Running the command `convert -version` will indicate the version of ImageMagick that is installed.

`fileDerivatives.strategyOptions.version = "6.9.0-0"`

### Auto-Orient

*Requires Omeka 2.3.1 or newer*

The default external ImageMagick strategy and the Imagick strategy both support a flag called `autoOrient`, which defaults to off. When turned on, Omeka will look for embedded orientation information in uploaded files, and rotate or transform the thumbnails it creates to account for that orientation.

A common use-case for this is images taken with mobile phone cameras, which often embed an orientation flag to allow computers to automatically rotate the image. Some image manipulation or preview software also will store rotations as only a change to the image's embedded rotation information. Turning `autoOrient` on allows Omeka to produce thumbnails in the expected orientation when these types of images are uploaded.

`fileDerivatives.strategyOptions.autoOrient = true`
