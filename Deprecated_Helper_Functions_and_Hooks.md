Deprecated Helper Functions and Hooks
=====================================


The following helper functions and hooks have been deprecated in previous versions of Omeka:

Helper Functions deprecated in 0.10 
---------------------------------------------------------------------------------------------------------------

-   add\_controllers(\$dir='controllers')
-   add\_data\_feed(\$format, \$options=array())
-   add\_navigation(\$text, \$link, \$type='main', \$permissions=null)
-   add\_theme\_pages(\$dir, \$theme='both')
-   collections(array \$params = array())
-   define\_metafield(\$name, \$description, \$type=null)
-   display\_empty(\$val, \$alternative="\[Empty\]")
-   dublin\_core(\$type)
-   entities(array \$params = array())
-   generate\_url(\$options, \$name)
-   get\_base\_url(\$use\_relative\_uri=false)
-   get\_day(\$date)
-   get\_month(\$date)
-   get\_year(\$date)
-   has\_collection(\$item, \$name=null)
-   has\_collectors(\$collection)
-   has\_files(\$item)
-   has\_tags(\$item, array \$tags=array())
-   has\_thumbnail(\$item)
-   has\_type(\$item, \$name=null)
-   institutions(array \$params = array())
-   is\_current(\$link, \$req = null)
-   item\_metadata(\$item, \$field, \$escape=true)
-   item\_permalink\_url(\$item)
-   item\_types()
-   items(array \$params = array())
-   items\_rss\_header()
-   items\_rss\_uri(\$params=array())
-   link\_to\_archive\_image(\$item, \$props=array(), \$action='show',
    \$random=false, \$imageType = 'thumbnail')
-   link\_to\_fullsize(\$item, \$props=array(),
    \$action='show', \$random=false)
-   link\_to\_square\_thumbnail(\$item, \$props=array(),
    \$action='show', \$random=false)
-   link\_to\_thumbnail(\$item, \$props=array(),
    \$action='show', \$random=false)
-   metafields(array \$params = array())
-   metatext\_form(\$item, \$input="textarea",\$metafields=null)
-   people(array \$params = array())
-   type(\$id=null)
-   types(array \$params = array())
-   tags(array \$params = array())
-   users(array \$params = array())

Hooks deprecated in 0.10 
-----------------------------------------------------------------------------------------

-   theme\_header
    -   use targeted hooks for public/admin theme
        (public\_theme\_header, admin\_theme\_header)
-   theme\_footer
    -   see above
-   append\_to\_settings\_form
    -   use plugin configuration instead.
-   prepend\_to\_settings\_form
-   append\_to\_file\_path
-   append\_to\_file\_web\_path
-   append\_to\_item\_form\_tags
    -   use 'admin\_append\_to\_items\_form\_tags'
-   append\_to\_items\_browse
    -   use 'admin\_append\_to\_items\_browse\_primary'
-   append\_to\_item\_show
    -   use 'admin\_append\_to\_items\_show\_primary' or secondary
-   append\_to\_item\_form\_upload
    -   use 'admin\_append\_to\_items\_form\_files'
-   append\_to\_search\_form
    -   use targeted hooks ('public\_append\_to\_advanced\_search'
        or admin)
-   add\_routes
    -   use 'define\_routes' instead
-   load\_navigation
    -   was based on 0.9 implementation of plugin hooks for navigation.
-   show\_type
    -   use show\_itemtype instead.
-   browse\_entities
    -   these hooks no longer do anything (entities are being
        phased out).
-   show\_entity
-   after\_render\_page
    -   no longer exists in 0.10
-   before\_render\_page
    -   no longer exists in 0.10
