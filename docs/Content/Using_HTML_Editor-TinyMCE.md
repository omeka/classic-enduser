---
title: Using the HTML Editor
----
Users working in the admin side of Omeka sites can use a HTML editor, powered by TinyMCE, to style and format text, to add links, and to embed multimedia.

Use the Editor
----------------------------------------------------------------

Enable the editor by clicking the check box below an element. When this is clicked, you will see a formatting toolbar at the top of the element input.

![Title element field with Use HTML checked. Above the input field are icons representing options to format the text.](/doc_files/Wysiwyg_item.jpg)

Use the buttons in the formatting tool bar to bold, italicize, underline, justify, and link words, or add bullet points. Please be aware that CSS formatting in specific exhibit theme may control the appearance of this text, so the editor may not always reflect how the final page looks.

If you want to write HTML code by hand, or embed web objects such as videos from YouTube or ArtBabble, click on the HTML button on the far right of editor options.

![The same image as above, with a red arrow pointing to a rather small button represented by small caps "HTML".](/doc_files/Wysiwyg_HTMLbutton.jpg)

This will open an HTML Source Editor window over the standard editing field. You may paste text that will embed videos (including YouTube embed codes) or other embed codes, or write your own HTML, in the Source Editor window. 

![Exhibit htmleditor.png](/doc_files/Exhibit_htmleditor.png)

In this window, you may paste text that will embed videos or other web-generated elements. 

If you try to paste in a string of code into the text window (first image above), the text will not be saved and the object you are trying to embed will not appear on your page. You may add other HTML tags (see below for more on what is allowed) through this interface.

Once you have finished coding the page, click Update.

Allowed Tags
----------------------------------------------------------------
Omeka uses the default rule set from TinyMCE. For a complete list see [default rule set from TinyMCE](http://tinymce.moxiecode.com/wiki.php/Configuration:valid_elements).

To change the allowed tags, go to your [security settings](../Admin/Settings/Security_Settings.md)
