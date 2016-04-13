<div id="wrap">

[Skip Navigation](Theme_API.html#content)
<div id="header">

<div class="padding">

<span
id="logo">[![Omeka](http://omeka.org/ui/i/logo-horizontal-288px.gif)](../index.html)</span>
<div id="search-form">

</div>

-   <div id="nav-showcase">

    </div>

    [Showcase](../showcase.1.html)
-   <div id="nav-involved">

    </div>

    [Get Involved](../index.html%3Fp=124.html)
-   <div id="nav-addons">

    </div>

    [Add-Ons](../add-ons.1.html)
-   <div id="nav-forums">

    </div>

    [Forums](../forums/topic/mysqli-stmt.bind-result.html)
-   <div id="nav-documentation">

    </div>

    [Documentation](http://omeka.org/codex/)
-   <div id="nav-download">

    </div>

    [Download](../download.1.html)

</div>

</div>

<div id="content">

<div class="padding">

<div id="user-meta">

-   <div id="pt-login">

    </div>

    [Log
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Theme%20API)

</div>

Functions
=========

<div id="contentSub">

(Redirected from [Theme
API](http://omeka.org/c/index.php?title=Theme_API&redirect=no "Theme API"))

</div>

<div id="primary">

<div
style="background:gold; border:1px solid goldenrod; padding: 1em 1em 0 1em; margin-bottom: 1em;">

<span id="This_page_is_outdated" class="mw-headline">This page is outdated</span> {#this-page-is-outdated style="color:#404040; border-bottom: none"}
---------------------------------------------------------------------------------

The information on this page concerns an old or obsolete version of
Omeka. If you are using a more recent version, instead see [Omeka's
documentation at
readthedocs.org](http://omeka.readthedocs.org/en/stable-2.0/Reference/libraries/globals/index.html).

</div>

+--------------------------------------+--------------------------------------+
| General Helpers                      | -   [auto\_discovery\_link\_tag](Fun |
|                                      | ctions/auto_discovery_link_tag.html  |
|                                      | "Functions/auto discovery link tag") |
|                                      | -   [common](Functions/common.html " |
|                                      | Functions/common")                   |
|                                      | -   [css](Functions/css.html "Functi |
|                                      | ons/css")                            |
|                                      | -   [display\_css](Functions/display |
|                                      | _css.html "Functions/display css")   |
|                                      | -   [display\_js](Functions/display_ |
|                                      | js.html "Functions/display js")      |
|                                      | -   [foot](Functions/foot.html "Func |
|                                      | tions/foot")                         |
|                                      | -   [head](Functions/head.html "Func |
|                                      | tions/head")                         |
|                                      | -   [img](Functions/img.html "Functi |
|                                      | ons/img")                            |
|                                      | -   [js](Functions/js.html "Function |
|                                      | s/js")                               |
|                                      | -   [link\_to\_advanced\_search](Fun |
|                                      | ctions/link_to_advanced_search.html  |
|                                      | "Functions/link to advanced search") |
|                                      | -   [link\_to\_home\_page](Functions |
|                                      | /link_to_home_page.html "Functions/l |
|                                      | ink to home page")                   |
|                                      | -   [link\_to\_admin\_home\_page](Fu |
|                                      | nctions/link_to_admin_home_page.html |
|                                      |  "Functions/link to admin home page" |
|                                      | )                                    |
|                                      | -   [nav](Functions/nav.html "Functi |
|                                      | ons/nav")                            |
|                                      | -   [pagination\_links](Functions/pa |
|                                      | gination_links.html "Functions/pagin |
|                                      | ation links")                        |
|                                      | -   [public\_nav\_main](Functions/pu |
|                                      | blic_nav_main.html "Functions/public |
|                                      |  nav main")                          |
|                                      | -   [plugin\_header](Functions/plugi |
|                                      | n_header.html "Functions/plugin head |
|                                      | er")                                 |
|                                      | -   [plugin\_footer](Functions/plugi |
|                                      | n_footer.html "Functions/plugin foot |
|                                      | er")                                 |
|                                      | -   [queue\_css](Functions/queue_css |
|                                      | .html "Functions/queue css")         |
|                                      | -   [queue\_css\_string](Functions/q |
|                                      | ueue_css_string.html "Functions/queu |
|                                      | e css string")                       |
|                                      | -   [queue\_js](Functions/queue_js.h |
|                                      | tml "Functions/queue js")            |
|                                      | -   [queue\_js\_string](Functions/qu |
|                                      | eue_js_string.html "Functions/queue  |
|                                      | js string")                          |
|                                      | -   [settings](Functions/settings.ht |
|                                      | ml "Functions/settings")             |
|                                      | -   [simple\_search](Functions/simpl |
|                                      | e_search.html "Functions/simple sear |
|                                      | ch")                                 |
|                                      | -   [total\_collections](Functions/t |
|                                      | otal_collections.html "Functions/tot |
|                                      | al collections")                     |
|                                      | -   [total\_items](Functions/total_i |
|                                      | tems.html "Functions/total items")   |
|                                      | -   [total\_tags](Functions/total_ta |
|                                      | gs.html "Functions/total tags")      |
|                                      | -   [total\_types](Functions/total_t |
|                                      | ypes.html "Functions/total types")   |
|                                      | -   [total\_users](Functions/total_u |
|                                      | sers.html "Functions/total users")   |
|                                      | -   [uri](Functions/uri.html "Functi |
|                                      | ons/uri")                            |
+--------------------------------------+--------------------------------------+
| Items                                | -   [display\_random\_featured\_item |
|                                      | ](Functions/display_random_featured_ |
|                                      | item.html "Functions/display random  |
|                                      | featured item")                      |
|                                      | -   [get\_item\_by\_id](Functions/ge |
|                                      | t_item_by_id.html "Functions/get ite |
|                                      | m by id")                            |
|                                      | -   [get\_items](Functions/get_items |
|                                      | .html "Functions/get items")         |
|                                      | -   [item](Functions/item.html "Func |
|                                      | tions/item")                         |
|                                      | -   [item\_belongs\_to\_collection]( |
|                                      | Functions/item_belongs_to_collection |
|                                      | .html "Functions/item belongs to col |
|                                      | lection")                            |
|                                      | -   [item\_citation](Functions/item_ |
|                                      | citation.html "Functions/item citati |
|                                      | on")                                 |
|                                      | -   [item\_fullsize](Functions/item_ |
|                                      | fullsize.html "Functions/item fullsi |
|                                      | ze")                                 |
|                                      | -   [item\_has\_files](Functions/ite |
|                                      | m_has_files.html "Functions/item has |
|                                      |  files")                             |
|                                      | -   [item\_has\_tags](Functions/item |
|                                      | _has_tags.html "Functions/item has t |
|                                      | ags")                                |
|                                      | -   [item\_has\_thumbnail](Functions |
|                                      | /item_has_thumbnail.html "Functions/ |
|                                      | item has thumbnail")                 |
|                                      | -   [item\_has\_type](Functions/item |
|                                      | _has_type.html "Functions/item has t |
|                                      | ype")                                |
|                                      | -   [item\_square\_thumbnail](Functi |
|                                      | ons/item_square_thumbnail.html "Func |
|                                      | tions/item square thumbnail")        |
|                                      | -   [item\_thumbnail](Functions/item |
|                                      | _thumbnail.html "Functions/item thum |
|                                      | bnail")                              |
|                                      | -   [item\_type\_elements](Functions |
|                                      | /item_type_elements.html "Functions/ |
|                                      | item type elements")                 |
|                                      | -   [item\_uri](Functions/item_uri.h |
|                                      | tml "Functions/item uri")            |
|                                      | -   [link\_to\_item](Functions/link_ |
|                                      | to_item.html "Functions/link to item |
|                                      | ")                                   |
|                                      | -   [link\_to\_browse\_items](Functi |
|                                      | ons/link_to_browse_items.html "Funct |
|                                      | ions/link to browse items")          |
|                                      | -   [link\_to\_collection\_for\_item |
|                                      | ](Functions/link_to_collection_for_i |
|                                      | tem.html "Functions/link to collecti |
|                                      | on for item")                        |
|                                      | -   [link\_to\_items\_in\_collection |
|                                      | ](Functions/link_to_items_in_collect |
|                                      | ion.html "Functions/link to items in |
|                                      |  collection")                        |
|                                      | -   [loop\_items](Functions/loop_ite |
|                                      | ms.html "Functions/loop items")      |
|                                      | -   [random\_featured\_item](Functio |
|                                      | ns/random_featured_item.html "Functi |
|                                      | ons/random featured item")           |
|                                      | -   [random\_featured\_items](http:/ |
|                                      | /omeka.org/c/index.php?title=Functio |
|                                      | ns/random_featured_items&action=edit |
|                                      | &redlink=1 "Functions/random feature |
|                                      | d items (page does not exist)")      |
|                                      | -   [recent\_items](Functions/recent |
|                                      | _items.html "Functions/recent items" |
|                                      | )                                    |
|                                      | -   [set\_current\_item](Functions/s |
|                                      | et_current_item.html "Functions/set  |
|                                      | current item")                       |
|                                      | -   [set\_items\_for\_loop](Function |
|                                      | s/set_items_for_loop.html "Functions |
|                                      | /set items for loop")                |
|                                      | -   [show\_item\_metadata](Functions |
|                                      | /show_item_metadata.html "Functions/ |
|                                      | show item metadata")                 |
+--------------------------------------+--------------------------------------+
| Item Files                           | -   [display\_files\_for\_item](Func |
|                                      | tions/display_files_for_item.html "F |
|                                      | unctions/display files for item")    |
|                                      | -   [get\_current\_file](Functions/g |
|                                      | et_current_file.html "Functions/get  |
|                                      | current file")                       |
|                                      | -   [item\_file](Functions/item_file |
|                                      | .html "Functions/item file")         |
|                                      | -   [item\_has\_files](Functions/ite |
|                                      | m_has_files.html "Functions/item has |
|                                      |  files")                             |
|                                      | -   [loop\_files\_for\_item](Functio |
|                                      | ns/loop_files_for_item.html "Functio |
|                                      | ns/loop files for item")             |
|                                      | -   [show\_file\_metadata](Functions |
|                                      | /show_file_metadata.html "Functions/ |
|                                      | show file metadata")                 |
+--------------------------------------+--------------------------------------+
| Collections                          | -   [collection](Functions/collectio |
|                                      | n.html "Functions/collection")       |
|                                      | -   [get\_collections](Functions/get |
|                                      | _collections.html "Functions/get col |
|                                      | lections")                           |
|                                      | -   [collection\_has\_collectors](Fu |
|                                      | nctions/collection_has_collectors.ht |
|                                      | ml "Functions/collection has collect |
|                                      | ors")                                |
|                                      | -   [collection\_is\_featured](Funct |
|                                      | ions/collection_is_featured.html "Fu |
|                                      | nctions/collection is featured")     |
|                                      | -   [display\_random\_featured\_coll |
|                                      | ection](Functions/display_random_fea |
|                                      | tured_collection.html "Functions/dis |
|                                      | play random featured collection")    |
|                                      | -   [get\_collection\_by\_id](Functi |
|                                      | ons/get_collection_by_id.html "Funct |
|                                      | ions/get collection by id")          |
|                                      | -   [get\_collection\_for\_item](htt |
|                                      | p://omeka.org/codex/Functions/get_co |
|                                      | llection_for_item "Functions/get col |
|                                      | lection for item")                   |
|                                      | -   [has\_collections\_for\_loop](Fu |
|                                      | nctions/has_collections_for_loop.htm |
|                                      | l "Functions/has collections for loo |
|                                      | p")                                  |
|                                      | -   [loop\_collections](Functions/lo |
|                                      | op_collections.html "Functions/loop  |
|                                      | collections")                        |
|                                      | -   [random\_featured\_collection](F |
|                                      | unctions/random_featured_collection. |
|                                      | html "Functions/random featured coll |
|                                      | ection")                             |
|                                      | -   [set\_collections\_for\_loop](Fu |
|                                      | nctions/set_collections_for_loop.htm |
|                                      | l "Functions/set collections for loo |
|                                      | p")                                  |
|                                      | -   [set\_current\_collection](Funct |
|                                      | ions/set_current_collection.html "Fu |
|                                      | nctions/set current collection")     |
|                                      | -   [total\_items\_in\_collection](F |
|                                      | unctions/total_items_in_collection.h |
|                                      | tml "Functions/total items in collec |
|                                      | tion")                               |
+--------------------------------------+--------------------------------------+
| Tags                                 | -   [get\_tags](Functions/get_tags.h |
|                                      | tml "Functions/get tags")            |
|                                      | -   [item\_tags\_as\_cloud](Function |
|                                      | s/item_tags_as_cloud.html "Functions |
|                                      | /item tags as cloud")                |
|                                      | -   [item\_tags\_as\_string](Functio |
|                                      | ns/item_tags_as_string.html "Functio |
|                                      | ns/item tags as string")             |
|                                      | -   [recent\_tags](Functions/recent_ |
|                                      | tags.html "Functions/recent tags")   |
|                                      | -   [tag\_cloud](Functions/tag_cloud |
|                                      | .html "Functions/tag cloud")         |
|                                      | -   [tag\_string](Functions/tag_stri |
|                                      | ng.html "Functions/tag string")      |
+--------------------------------------+--------------------------------------+

<div class="printfooter">

Retrieved from "[http://omeka.org/codex/Functions](Functions.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Category](http://omeka.org/codex/Special:Categories "Special:Categories"):
<span dir="ltr">[Obsolete
pages](http://omeka.org/c/index.php?title=Category:Obsolete_pages&action=edit&redlink=1 "Category:Obsolete pages (page does not exist)")</span>

</div>

</div>

</div>

<div id="secondary">

<div class="portlet">

Documentation
-------------

-   [Home](http://omeka.org/codex/)
-   [Screencasts](http://omeka.org/codex/Screencasts)
-   [Themes](http://omeka.org/codex/Managing_Themes_2.0)
-   [Appearance](http://omeka.org/codex/Managing_Appearance_2.0)
-   [Plugins](http://omeka.org/codex/Plugins2.0)

</div>

<div class="portlet">

Page View
---------

-   <div id="nav-page">

    </div>

    [Page](Functions.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](Talk:Functions.html)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Functions&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Functions&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links here](Special:WhatLinksHere/Functions.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related changes](Special:RecentChangesLinked/Functions.html)
-   <div id="t-specialpages">

    </div>

    [Special pages](http://omeka.org/codex/Special:SpecialPages)

</div>

[![Creative Commons
License](https://i.creativecommons.org/l/by/3.0/us/88x31.png)](http://creativecommons.org/licenses/by/3.0/us/)\
Omeka Documentation is licensed under a [Creative Commons Attribution
3.0 United States
License](http://creativecommons.org/licenses/by/3.0/us/).

</div>

</div>

</div>

<div id="footer">

<div class="padding">

<div id="sitemap">

<div class="section">

### About

-   [Project](../index.html%3Fp=2.html)
-   [Staff](../index.html%3Fp=3.html)
-   [News](../blog.1.html)
-   [License](http://www.gnu.org/copyleft/gpl.html)

</div>

<div class="section">

### Help

-   [User Forums](../forums/topic/mysqli-stmt.bind-result.html)
-   [Documentation](http://omeka.org/codex/)
-   [Dev Listserv](http://groups.google.com/group/omeka-dev)
-   [Contact](http://omeka.org/contact/)

</div>

<div class="section">

### Downloads

-   [Download Omeka](../download.1.html)
-   [Plugins](../plugins.html)
-   [Themes](../download/themes/index.html)
-   [Packages](../index.html%3Fp=222.html)

</div>

</div>

<div id="chnm-meta">

<span id="chnm-logo">[![Roy Rosenzweig Center for History and New
Media](http://omeka.org/ui/i/rrchnm-logo-regular.gif)](http://chnm.gmu.edu)</span>
Omeka is a project of the [Roy Rosenzweig Center for History and New
Media](http://chnm.gmu.edu), [George Mason
University](http://www.gmu.edu). Copyright © 2007–2016 CHNM.

</div>

</div>

</div>

</div>
