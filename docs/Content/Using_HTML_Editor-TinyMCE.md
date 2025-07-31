# Using the HTML Editor

Users working in the administrative side of Omeka Classic sites can turn on the HTML editor, powered by TinyMCE, to style and format text, to add links, and to embed multimedia. This provides both a WYSIWYG editor (like a word processor) and a way to enter in HTML code directly (the Source Editor). 

Use the editor
----------------------------------------------------------------
For some text boxes, such as in [Exhibit Builder](../Plugins/ExhibitBuilder.md) blocks, the editor will automatically load.

When editing items or collections, you enable the editor by clicking the "use HTML" checkbox that displays below the text field. When this is clicked, you will see a formatting toolbar at the top of the element input. This allows you to style text visually, and the editor will insert the requisite HTML behind the scenes.

![Title element field with the "Use HTML" box checked. Above the input field are icons representing options to format the text.](../doc_files/Wysiwyg_item.png "Title element field with the "Use HTML" box checked. Above the input field are icons representing options to format the text.")

Use the buttons in the toolbar to format text, change text alignment, create links and lists, and add headers. Be aware that CSS formatting in site and exhibit themes may control the appearance of this text, so the editor may not always reflect how the final page looks.

You can insert shortcodes in either the plain-text editing box or the HTML editing box. 

If you want to write HTML code by hand, or embed web objects such as videos, click on the code button, represented by `<>`, on the far right of the editor options.

![The same image as above, with an arrow pointing to a small button represented by the characters <>.](../doc_files/Wysiwyg_HTMLbutton.png "The same image as above, with an arrow pointing to a small button represented by the characters <>.")

This will open an HTML Source Editor window over the standard editing field. You may paste code snippets from Youtube or elsewhere, or write your own HTML, in the Source Editor window. You can use this to manually embed an image from one of your Omeka items, by using its URL directly in an `<img>` tag.

![The HTML source editor with embedding code pasted into the text field](../doc_files/htmlembed.png "The HTML source editor with embedding code pasted into the text field")

If you try to paste in a string of code into the text styling window rather than the HTML source editor, the text will not be saved and the object you are trying to embed will not appear on your page. 

You can use shortcodes by simply inserting them into the HTML, for example `<p>[timeline title='My Timeline']</p>`.

Once you have finished coding the page, click the "Update" button.

Allowed HTML elements
----------------------------------------------------------------

Omeka installations load the default rules of allowable HTML tags from TinyMCE. You can customize your site's list of allowed or blocked tags. To do so, go to your [security settings](../Admin/Settings/Security_Settings.md#html-filtering) and add or remove HTML tags from the "Allowed HTML Elements" box. 
