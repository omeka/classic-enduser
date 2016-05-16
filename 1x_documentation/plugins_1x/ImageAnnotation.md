Plugins/ImageAnnotation
=======================

[Plugins](../Plugins.1.html "Plugins")

The Image Annotation plugin allows users to annotate images associated
with items.

Features
---------------------------------------------------------

-   **Image Annotation Gallery**
    -   Permitted users can browse and annotate images on item pages.
        Admins can also can use the
        `image_annotation_display_annotated_image_gallery_for_item`
        helper function in their themes to display an image gallery for
        an item. (See [below](ImageAnnotation.html#Adding_the_Image_Annotation_Gallery_to_a_Public_Theme) for details).
-   **Image Annotation Admin Page**
    -   Permitted users can search, sort, and delete image annotations
        via an admin page.
-   **Configurable Permissions**
    -   Admins can specify which types of users can view, add, edit, or
        delete annotations. They can also specify whether users can edit
        or delete all annotations, or just the annotations they added.
        The plugin also works with the Guest Login plugin, so that
        self-registered users can annotate images.

Needed Features
-----------------------------------------------------------------------

-   Save relative coordinates, so annotations can display on
    resized images.

Adding the Image Annotation Gallery to a Public Theme
---------------------------------------------------------------------------------------------------------------------------------------------------

Out of the box, the Image Annotation plugin only automatically adds the
gallery that shows the annotations to the admin theme. To add the
gallery to a public theme, you need to add a little PHP code to your
theme.

### For Omeka versions 1.3 and above

If your theme does not contain an /items directory, you will need to the
following:

1.  Create a folder in the theme's directory named "items".
2.  Copy the "show.php" file found in application/views/scripts/items
    and move it into the newly-created items folder in your
    theme directory.
3.  Paste the following function in that page:


    ``` {.de1}
    <?php echo image_annotation_display_annotated_image_gallery_for_item();?>
    ```


4.  Save show.php and be sure it is located within the items folder. The
    directory path to that file should look like this:
    themename-&gt;items-&gt;show.php

### For Older Versions of Omeka

1.  Edit the items/show.php page in your public theme.
2.  Add the following code:


    ``` {.de1}
    <?php echo image_annotation_display_annotated_image_gallery_for_item();?>
    ```

### Image Annotation and other Plugins

Keep in mind that if you are activating other plugins that append the
items/show page for displaying content those elements may crowd the
page's public display. You may want to tweak your theme.

Working with Annotations
-----------------------------------------------------------------------------------------

### Adding an Annotation

1.  Go to an image annotation gallery (either on the admin item show
    page or a page in your public theme where you've added one).
2.  Click on the thumbnail of the image you want to view.
3.  Click on the Add Annotation button.
4.  A small annotation box will appear. Drag the annotation to the
    region of the image you want to annotate. You can also resize the
    box by clicking and dragging the borders of the box.
5.  Fill in the text of your annotation in the form.
6.  Click the Save button.

### Editing an Annotation 

1.  Click the annotation box you want to edit.
2.  Drag the annotation box over the part of the image you want
    to annotate. You can resize the box by clicking and dragging the
    borders of the box.
3.  Click the Save button.

### Deleting an Annotation 

1.  Click the annotation box you want to delete.
2.  Click the Delete button.

Uninstalling the Plugin
---------------------------------------------------------------------------------------

If you edited the items/show page in the public theme, you must also
delete that snippet of PHP after you uninstall Image Annotation from the
plugins page. If you do not go back and edit items/show, you will find
that most of the data does not display on public items/show pages.
