# CSS Editor

The [CSS Editor plugin](https://omeka.org/classic/plugins/CSSEditor/){target=_blank} allows users to make changes to the CSS ("cascading stylesheets," code that controls appearance) of their Omeka Classic installation without going into the server-side files.

This plugin will be most helpful to people with experience using CSS and designing sites.

CSS Editor requires Omeka Classic 2.0 or higher. At this time, [there is an issue](https://github.com/omeka/plugin-CSSEditor/issues/4){target=_blank} with using CSS Editor to point to pseudo-classes, such as `:before` and `:after`, attributes, "nth" selectors, or wildcards.

## Configuration

Once you have [installed](../Admin/Adding_and_Managing_Plugins.md) the plugin, you can access it from from the Plugins menu in the top navigation bar of the Omeka Admin. Click the blue "Configure" button to go to the CSS Editor.

The CSS Editor configuration page contains a large text field in which you can write your custom CSS. Type your code as you would in a CSS document. Be sure to save your changes, then refresh the public page of your site to see your edits take effect. 

The easiest way to learn Omeka Classic page components for the sake of CSS editing is to use your browser's Inspect tool when looking at your chosen theme.

CSS Editor will strip out lines it does not recognize, including pseudo-classes. It will also remove the last semi-colon inside each designation; be careful to add semi-colons as needed when editing your entries. 

On your public page, your CSS Editor entries will appear inside the `<head>` tag, after Omeka's default CSS files are called, inside the following tag:

``` 
<style type="text/css" media="all"> 

</style>
```

This should ensure that your CSS code overrides the default CSS. There may be elements specified in the default CSS files that come with the property `!important`, which will take precedence over code that follows it. If you experience this issue, add `!important` to your own entry in the CSS Editor.

![CSS editor](../doc_files/plugin_images/CSSE.png)

The [W3C has an excellent CSS tutorial and reference](https://www.w3schools.com/css/){target=_blank} to help you find the individual elements you wish to customize on your site.
