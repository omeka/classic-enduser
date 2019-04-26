---
title: Using the HTML Editor
----
Users working in the admin side of Omeka Classic sites can use a HTML editor, powered by TinyMCE, to style and format text, to add links, and to embed multimedia.

Use the Editor
----------------------------------------------------------------
For some text boxes, such as [Exhibit Builder](/plugins/ExhibitBuilder) blocks, the editor will automatically load.

When editing items or collections, you enable the editor by clicking the check box below an element. When this is clicked, you will see a formatting toolbar at the top of the element input.

![Title element field with Use HTML checked. Above the input field are icons representing options to format the text.](/doc_files/Wysiwyg_item.png)

Use the buttons in the tool bar to format text, change text alignment, create links and lists, and add headers. Be aware that CSS formatting in specific exhibit theme may control the appearance of this text, so the editor may not always reflect how the final page looks.

If you want to write HTML code by hand, or embed web objects such as videos from YouTube or ArtBabble, click on the  code button, represented by `<>`, on the far right of editor options.

![The same image as above, with a red arrow pointing to a rather small button represented by the characters`<>`.](/doc_files/Wysiwyg_HTMLbutton.png)

This will open an HTML Source Editor window over the standard editing field. You may paste text that will embed videos (including YouTube embed codes) or other embed codes, or write your own HTML, in the Source Editor window. 

![An empty html box. There is a heading for "Source Code," a large text entry field, and a blue "ok" button at the bottom.](/doc_files/htmleditor.png)

In this window, you may paste text that will embed videos or other web-generated elements. 

![The same source editor as before, but with the embed code for the Vimeo video for the screencast of "Managing Collections in Omeka Classic" pasted into the text field](/doc_files/htmlembed.png)

If you try to paste in a string of code into the text window (first image above), the text will not be saved and the object you are trying to embed will not appear on your page. You may add other HTML tags (see below for more on what is allowed) through this interface.

Once you have finished coding the page, click Update.

Allowed Tags
----------------------------------------------------------------
Omeka uses the default rule set from TinyMCE. For a complete list see [default rule set from TinyMCE](http://tinymce.moxiecode.com/wiki.php/Configuration:valid_elements).

To change the allowed tags, go to your [security settings](../Admin/Settings/Security_Settings.md)
