---
title: Omeka.wysiwyg in Omeka Classic 1.x
---

*This documentation for Omeka Classic versions up to 1.5 only*

Omeka.wysiwyg is a JavaScript function that allows you to add TinyMCE to textareas in the administrative panel.

Parameters
-------------------------------------------------------------

Omeka.wysiwyg has the following default parameters

-   convert\_urls: false,
-   mode: "textareas",
-   theme: "advanced",
-   theme\_advanced\_toolbar\_location: "top",
-   force\_br\_newlines: false,
-   forced\_root\_block: 'p',
-   remove\_linebreaks: true,
-   fix\_content\_duplication: false,
-   fix\_list\_elements: true,
-   valid\_child\_elements: "ul\[li\],ol\[li\]",
-   theme\_advanced\_buttons1:
    "bold,italic,underline,justifyleft,justifycenter,justifyright,bullist,numlist,link,formatselect,code",
-   theme\_advanced\_buttons2: "",
-   theme\_advanced\_buttons3: "",
-   theme\_advanced\_toolbar\_align: "left"

Any of these parameters can be changed by passing the new parameter and value to the Omeka.wysiwyg function:


``` {.de1}
Omeka.wysiwyg({
    mode: "specific_textareas",
    editor_selector: "html-editor",
    forced_root_block: ""
});
```

A complete list of parameters can be found on the [TinyMCE documentation wiki](http://tinymce.moxiecode.com/wiki.php).

