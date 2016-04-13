<div id="wrap">

[Skip Navigation](Updating_Plugins_For_2.0.html#content)
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
    In](http://omeka.org/c/index.php?title=Special:UserLogin&returnto=Updating%20Plugins%20For%202.0)

</div>

Updating Plugins For 2.0
========================

<div id="primary">

<div
style="background:gold; border:1px solid goldenrod; padding: 1em 1em 0 1em; margin-bottom: 1em;">

<span id="This_page_is_a_draft." class="mw-headline">This page is a draft.</span> {#this-page-is-a-draft. style="color:#404040; border-bottom: none"}
---------------------------------------------------------------------------------

The information on this page concerns an unreleased version of Omeka or
is subject to change for some other reason. Stay away, if you know
what's good for you.

</div>

Omeka 2.0 will include many changes that will affect how plugins are
designed and how they accomplish various tasks. This is a running list,
and will likely change greatly between now and the eventual release of
2.0 (no date is set for that yet).

<span id="Omeka_an_Archive.3F" class="mw-headline"> Omeka an Archive? </span>
-----------------------------------------------------------------------------

While archivists can (and many do) use Omeka as a presentation layer to
their digital holdings, Omeka is not archival management software. To
underscore this fact, we've removed all mention of the word "archive" in
the Omeka codebase and filesystem. **This will require at least two
additional steps when upgrading from earlier versions to 2.0:**

-   Rename the `archive/files/` directory to `/archive/original/`:

<!-- -->

     $ mv /path/to/omeka/archive/files/ to /path/to/omeka/archive/original/

-   Rename the `archive/` directory to `files/`:

<!-- -->

     $ mv /path/to/omeka/archive/ /path/to/omeka/files/

Some changes to the API were necessary for this change. They include:

-   Rename `ARCHIVE_DIR` to `FILES_DIR`
-   Rename `WEB_ARCHIVE` to `WEB_FILES`
-   Rename `File::$archive_filename` to `File::$filename`
-   Rename "archive" to "original" (when an argument that refers to path
    to files/original/)
-   Rename `Omeka_Filter_Filename::renameFileForArchive()` to
    `Omeka_Filter_Filename::renameFile()`
-   Rename `Omeka_View_Helper_Media::archive_image()` to
    `Omeka_View_Helper_Media::image_tag()`
-   Rename `Installer_Requirements::_checkArchiveStorageSetup()` to
    `Installer_Requirements::_checkFileStorageSetup()`

<span id="Abstract_Plugin_Class" class="mw-headline"> Abstract Plugin Class </span>
-----------------------------------------------------------------------------------

The `Omeka_Plugin_Abstract` class was introduced in Omeka 1.5 to assist
plugin authors in setting up their plugin's hooks, filters, and options.
**In 2.0 this has been renamed to `Omeka_Plugin_AbstractPlugin`**. We
highly recommend using this class because plugin.php may be deprecated
in future versions of Omeka in favor of loading the plugin directly from
this class. **Also starting in 2.0, Omeka does not require the
plugin.php file if a valid plugin class** exists following this pattern:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// In plugins/YourPlugin/YourPluginPlugin.php
class YourPluginPlugin extends Omeka_Plugin_AbstractPlugin
{}
```

</div>

</div>

One change introduced in Omeka 2.0 is arbitrary hook and filter callback
names. Before, all callback names followed a predetermined format. While
this format remains an option, now a corresponding key in `$_hooks` and
`$_filters` will be interpreted as the name of the callback method.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
array('admin_navigation_main', 
      'public_navigation_main', 
      'changeSomething' => 'display_setting_site_title', 
      'displayItemDublinCoreTitle' => array(
          'Display', 
          'Item', 
          'Dublin Core', 
          'Title', 
      ))
```

</div>

</div>

<span id="Controllers" class="mw-headline">Controllers</span>
-------------------------------------------------------------

**Your controllers should now extend
`Omeka_Controller_AbstractActionController`** instead of
`Omeka_Controller_Action`. This is for forward compatibility with Zend
Framework 2.0. For example:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
class YourController extends Omeka_Controller_AbstractActionController
{}
```

</div>

</div>

### <span id="modelClass_and_modelName" class="mw-headline"> modelClass and modelName </span>

Controllers used to have a \_modelClass property that refers to the
corresponding name of the model used by the controller. That changes to
use setDefaultModelName.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// 1.x
public function init() 
{
    $this->_modelClass = 'MyModel';
}
 
// 2.0
public function init() 
{
    $this->_helper->db->setDefaultModelName('MyModel');
}
```

</div>

</div>

### <span id="Db_wrappers_removed" class="mw-headline"> Db wrappers removed </span>

getDb, getTable, and findById are replaced by equivalent calls to
\_helper-&gt;db-&gt;{methodName}.

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$elementToRemove = $this->getDb()->getTable('Element')->find($elementId);
```

</div>

</div>

becomes

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$elementToRemove = $this->_helper->db->getTable('Element')->find($elementId);
```

</div>

</div>

<span id="Models" class="mw-headline">Models</span>
---------------------------------------------------

### <span id="Records" class="mw-headline"> Records </span>

**Your records should now extend `Omeka_Record_AbstractRecord`** instead
of `Omeka_Record`. This is for forward compatibility with Zend Framework
2.0. For example:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
class YourRecord extends Omeka_Record_AbstractRecord
{}
```

</div>

</div>

We've made some major changes to the record API. **The following
callbacks have been removed**:

-   beforeSaveForm
-   afterSaveForm
-   beforeInsert
-   afterInsert
-   beforeUpdate
-   afterUpdate
-   beforeValidate
-   afterValidate

As such, **the following plugin hooks have been removed**, where \* is
"record" or a specific record name (e.g. "item", "collection"):

-   before\_save\_form\_\*
-   after\_save\_form\_\*
-   before\_insert\_\*
-   after\_insert\_\*
-   before\_update\_\*
-   after\_update\_\*
-   before\_validate\_\*
-   after\_validate\_\*

By removing these callbacks we give you full control over the timing of
execution. Any logic that's currently in the SaveForm, Insert, Update
callbacks should be moved to beforeSave() and afterSave(). The Any logic
that's currently in the Validate callbacks should be moved to
`_validate()`. For example:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// Note the order of execution.
public function afterSave($args)
{
    if ($args['insert']) {
        // Do something after record insert. Equivalent to afterInsert.
    } else {
        // Do something after record update. Equivalent to afterUpdate.
    }
 
    // Do something after every record save.
 
    if ($args['post']) {
        // Do something with the POST data. Equivalent to afterSaveForm.
    }
}
```

</div>

</div>

Note that the signature of the beforeSave() and afterSave() in
Omeka\_Record\_AbstractRecord has changed to beforeSave(\$args) and
afterSave(\$args), with no type specified for \$args. To adhere to
strict standards, existing beforeSave and afterSave methods should
reflect that change.

\
 **Another change is that `saveForm()` has been merged into `save()`.**
Using `save()` to handle a form in your controller is done like this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
public function editAction()
{
    // Check if the form was submitted.
    if ($this->getRequest()->isPost()) {
        // Set the POST data to the record.
        $record->setPostData($_POST);
        // Save the record. Passing false prevents thrown exceptions.
        if ($record->save(false)) {
            $successMessage = $this->_getEditSuccessMessage($record);
            if ($successMessage) {
                $this->_helper->flashMessenger($successMessage, 'success');
            }
            $this->_redirectAfterEdit($record);
        // Flash an error if the record does not validate.
        } else {
            $this->_helper->flashMessenger($record->getErrors());
        }
    }
}
```

</div>

</div>

### <span id="Models_Directory" class="mw-headline"> Models Directory </span>

The models directory has been reorganized to only have models that
extend `Omeka_Record_AbstractRecord` at the root level. Classes that
extend `Omeka_Db_Table` were moved to the models/Table/ directory, and
renamed from `*Table` to `Table_*`. This change is transparent when
using `Omeka_Db::getTable()`, so you'll still pass the root name of the
table, like so:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// This gets the Table_Item object.
$itemTable = $db->getTable('Item');
```

</div>

</div>

When writing plugins we recommend following this directory pattern in
your models directory:

-   Classes that extend `Omeka_Record_AbstractRecord` should go directly
    in the models/ directory, as usual.
-   Classes that extend `Omeka_Db_Table` should go in the models/Table/
    directory, and their class names should be `Table_[record name]`.

For backwards compatibility we allow `Omeka_Db_Table` classes to follow
their old pattern, but this behavior is deprecated.

### <span id="Database_Aliases_in_Table_.2A_Classes" class="mw-headline"> Database Aliases in Table\_\* Classes </span>

Previously, when using the `getSelect()` method, select statements could
use a short alias for the database name, when adding clauses, for
example , "e" in this query:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$select->where("e.id = ?", $exhibitId);
```

</div>

</div>

when querying the exhibits table. Those should no longer be used. Use
the full name of the table instead (without the table prefix):

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$select->where("exhibits.id = ?", $exhibitId);
```

</div>

</div>

### <span id="User_Record" class="mw-headline"> User Record </span>

The `User` record no longer depends on an `Entity` to store some data
like name and email. The user's full name and email are directly part of
the `User` object now.

There are no longer separate fields for first, last, and middle name,
just one for full name.

### <span id="Entity_Record" class="mw-headline"> Entity Record </span>

The `Entity`, `EntitiesRelations`, and `EntityRelationships` records are
gone, as is the `Relatable` mixin.

Plugins that were relying on or referring to entities or entity ids
should usually directly refer to users instead.

Plugins that had records using `Relatable` should use the new
`Mixin_Owner` mixin instead for handling record ownership.

### <span id="Mixins" class="mw-headline"> Mixins </span>

The following mixins have been changed

  Old Mixin           New Mixin
  ------------------- -----------------------
  Ownable             Mixin\_Owner
  Taggable            Mixin\_Tag
  ActsAsElementText   Mixin\_ElementText
  PublicFeatured      Mixin\_PublicFeatured

The `Mixin_Timestamp` mixin has been added.

The `Mixing_Search` mixin has been added.

The `Orderable` mixin has been removed.

<span id="Acl" class="mw-headline"> Acl </span>
-----------------------------------------------

The `Omeka_Acl` object no longer exists. **References to `Omeka_Acl`
should be to `Zend_Acl` instead.**

`Omeka_Acl` provided several non-standard methods which are gone along
with it: `loadRoleList()`, `loadResourceList()`, and `loadAllowList()`.
All of these methods were shortcuts for passing arrays to the Acl
object.

Now, just directly make individual calls to `addRole()`,
`addResource()`, and `allow()`. You no longer need to use
`loadResourceList()` to define the privileges for each resource.

### <span id="checkUserPermission.28.29" class="mw-headline"> checkUserPermission() </span>

Pre-2.0:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$acl->checkUserPermission('ExhibitBuilder_Exhibits', 'showNotPublic');
```

</div>

</div>

Use `isAllowed()` instead:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$acl->isAllowed(current_user(), 'ExhibitBuilder_Exhibits', 'showNotPublic');
```

</div>

</div>

<span id="Helper_Functions" class="mw-headline"> Helper Functions </span>
-------------------------------------------------------------------------

Many helper functions are removed or replaced. The table below lists
previously used functions with their replacements

### <span id="Function_Replacements" class="mw-headline"> Function Replacements </span>

  Old Function                              New Function
  ----------------------------------------- ----------------------------------------------------------
  random\_featured\_item()                  random\_featured\_items(1)
  has\_tags()                               metadata(\$record, 'has tags')
  item\_has\_tags()                         metadata(\$item, 'has tags')
  item\_has\_files()                        metadata(\$item, 'has files')
  item\_has\_thumbnail()                    metadata(\$item, 'has thumbnail')
  item\_citation()                          metadata(\$item, 'citation')
  n/a                                       metadata(\$item, 'file count')
  item\_fullsize()                          item\_image('fullsize')
  item\_thumbnail()                         item\_image('thumbnail')
  item\_square\_thumbnail()                 item\_image('square\_thumbnail')
  setting()                                 option()
  display\_js()                             head\_js()
  display\_css()                            head\_css()
  css()                                     css\_src()
  js()                                      js\_tag()
  queue\_js()                               queue\_js\_file()
  queue\_css()                              queue\_css\_file()
  display\_random\_featured\_collection()   random\_featured\_collection()
  recent\_collections()                     get\_recent\_collections()
  random\_featured\_collection()            get\_random\_featured\_collection()
  get\_latest\_omeka\_version()             latest\_omeka\_version()
  display\_file()                           file\_markup()
  display\_files()                          file\_markup()
  recent\_files()                           get\_recent\_files()
  show\_file\_metadata()                    all\_element\_texts()
  \_tag\_attributes()                       tag\_attributes()
  simple\_search()                          simple\_search\_form()
  display\_form\_input\_for\_element()      element\_form()
  display\_element\_set\_form()             element\_set\_form()
  label\_options()                          label\_table\_options()
  display\_search\_filters()                search\_filters()
  current\_action\_contexts()               get\_current\_action\_contexts()
  \_\_v()                                   get\_view()
  display\_files\_for\_item()               files\_for\_item()
  display\_random\_featured\_item()         random\_featured\_item()
  display\_random\_featured\_items()        random\_featured\_items()
  recent\_items()                           get\_recent\_items()
  random\_featured\_items()                 get\_random\_featured\_items()
  random\_featured\_item()                  get\_random\_featured\_item()
  show\_item\_metadata()                    all\_element\_texts()
  link\_to\_advanced\_search()              link\_to\_item\_search()
  link\_to\_file\_metadata()                link\_to\_file\_show()
  link\_to\_next\_item()                    link\_to\_next\_item\_show()
  link\_to\_previous\_item()                link\_to\_previous\_item\_show()
  link\_to\_browse\_items()                 link\_to\_items\_browse()
  nls2p()                                   text\_to\_paragraphs()
  recent\_tags()                            get\_recent\_tags()
  item\_tags\_as\_string()                  tag\_string('item')
  item\_tags\_as\_cloud()                   tag\_cloud('item')
  has\_permission()                         is\_allowed()
  uri()                                     url()
  abs\_uri()                                absolute\_url()
  abs\_item\_uri()                          record\_url(\$item, 'show', true)
  record\_uri()                             record\_url()
  item\_uri()                               record\_url(\$item)
  current\_uri()                            current\_url()
  is\_current\_uri()                        is\_current\_url()
  items\_output\_uri()                      items\_output\_url()
  file\_display\_uri()                      file\_display\_url()
  public\_uri()                             public\_url()
  admin\_uri()                              admin\_url()
  set\_theme\_base\_uri()                   set\_theme\_base\_url()
  revert\_theme\_base\_uri()                revert\_theme\_base\_url
  loop\_records()                           loop()
  loop\_files()                             loop('files')
  loop\_collections()                       loop('collections')
  loop\_items()                             loop('items')
  loop\_item\_types()                       loop('item\_types')
  loop\_items\_in\_collection()             loop('items')
  loop\_files\_for\_item()                  loop('files')
  set\_current\_file()                      set\_current\_record('file', \$file)
  set\_current\_collection()                set\_current\_record('collection', \$collection)
  set\_current\_item()                      set\_current\_record('item', \$item)
  get\_current\_item()                      get\_current\_record('item')
  get\_current\_collection()                get\_current\_record('collection')
  get\_current\_file()                      get\_current\_record('file')
  get\_current\_item\_type()                get\_current\_record('item\_type')
  set\_current\_item\_type()                set\_current\_record('item\_type')
  set\_items\_for\_loop()                   set\_loop\_records('items', \$items)
  get\_items\_for\_loop()                   get\_loop\_records('items')
  has\_items\_for\_loop()                   has\_loop\_records('items')
  set\_collections\_for\_loop()             set\_loop\_records('collections', \$items)
  get\_collections\_for\_loop()             get\_loop\_records('collections')
  has\_collections\_for\_loop()             has\_loop\_records('collections')
  set\_files\_for\_loop()                   set\_loop\_records('files', \$items)
  get\_files\_for\_loop()                   get\_loop\_records('files')
  has\_files\_for\_loop()                   has\_loop\_records('files')
  set\_item\_types\_for\_loop()             set\_loop\_records('item\_types', \$itemTypes)
  get\_item\_types\_for\_loop()             get\_loop\_records('item\_types')
  has\_item\_types\_for\_loop()             has\_loop\_records('item\_types')
  get\_item\_by\_id()                       get\_record\_by\_id('item', \$id)
  get\_collection\_by\_id()                 get\_record\_by\_id('collection', \$id)
  get\_user\_by\_id()                       get\_record\_by\_id('user', \$id)
  \_select\_from\_table()                   get\_table\_options() with Zend's formSelect()
  is\_odd(\$num)                            n/a; use \$num & 1
  form\_error()                             n/a; Use Zend Form Validations
  collection\_is\_featured                  metadata('collection', 'featured')
  collection\_is\_public                    metadata('collection', 'public')
  button\_to                                n/a; use Zend's form helpers or hand-write HTML buttons.
  delete\_button                            link\_to(\$record, 'delete-confirm', 'Delete', ...)

### <span id="Return_Value" class="mw-headline"> Return Value </span>

All functions that previously echoed output will now return the same
output. For instance, instead of this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php head(); ?>
```

</div>

</div>

you must echo the return value in your script:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php echo head(); ?>
```

</div>

</div>

### <span id="Looping_Records" class="mw-headline"> Looping Records </span>

All functions that used `loop_records()` have been consolidated into one
function, `loop()`. This includes `loop_items()`, `loop_files()`,
`loop_collections()`, etc. The basic structure of a loop has changed as
well, so this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php while ($item = loop_items()): ?>
<!-- do something -->
<?php endwhile; ?>
```

</div>

</div>

should now be written like this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
<?php foreach (loop('items') as $item): ?>
<!-- do something -->
<?php endforeach; ?>
```

</div>

</div>

### <span id="Set.2FGet.2FHas_Records_for_Loop" class="mw-headline"> Set/Get/Has Records for Loop </span>

All functions that set, returned, or checked the existence of records
for loop have been consolidated into three functions:
`set_loop_records()`, `get_loop_records()`, and `has_loop_records()`.
So, for example, this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
set_items_for_loop($items);
if (has_items_for_loop()) {
    $items = get_items_for_loop();
}
```

</div>

</div>

becomes this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
set_loop_records('items', $items);
if (has_loop_records('items')) {
    $items = get_loop_records('items');
}
```

</div>

</div>

### <span id="Set.2FGet_Current_Record" class="mw-headline"> Set/Get Current Record </span>

All functions that set or returned the current record have been
consolidated into two functions: `set_current_record()` and
`get_current_record()`. So, for example, this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
set_current_item($item);
$item = get_current_item();
```

</div>

</div>

becomes this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
set_current_record('item', $item);
$item = get_current_record('item');
```

</div>

</div>

### <span id="Get_Record_by_ID" class="mw-headline"> Get Record by ID </span>

All functions that got a record by its ID have been consolidated into
one function: `get_record_by_id()`. So, for example, this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$item = get_item_by_id($id);
```

</div>

</div>

becomes this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$item = get_record_by_id('item', $id);
```

</div>

</div>

### <span id="Form_Functions" class="mw-headline">Form Functions</span>

In addition to the above functions, the form functions like text(),
label(), select(), radio(), etc. have been removed in Omeka 2.0.
Instead, use the corresponding [Zend Form
Helpers](http://framework.zend.com/manual/en/zend.view.helpers.html).
So, for example, this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
echo text(array('name'=>'title', 'class'=>'textinput', 'id'=>'title'), 'default title', 'Title');
```

</div>

</div>

becomes this:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
echo $this->formLabel('title', 'Title');
echo $this->formText('title', 'default title', array('class'=>'textinput'));
```

</div>

</div>

Or, of course, it might be easier to just write the HTML yourself.

<span id="Omeka_Context" class="mw-headline">Omeka\_Context</span>
------------------------------------------------------------------

We no longer use `Omeka_Context`. Instead get the resource via
`Zend_Registry`. So, for example,

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$acl = Omeka_Context::getInstance()->acl;
```

</div>

</div>

becomes

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
$acl = Zend_Registry::get('bootstrap')->getResource('Acl');
```

</div>

</div>

<span id="Jobs" class="mw-headline">Jobs</span>
-----------------------------------------------

**We highly recommend that all processes that may run longer than a
typical web process are sent to a job**. The job will mediate the
process, reducing the chance of timeout and memory usage errors that can
happen even with the best written code. To run a job just write a class
that contains the code to run, like so:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
class YourJob extends Omeka_Job_AbstractJob
{
    public function perform()
    {
        // code to run
    }
}
```

</div>

</div>

You have two options on how to run the code: default and long-running.
The default way is intended to run processes that, though are more
processor-intensive than the typical web process, are usually not in
danger of timing out. You can run these processes like so,

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
Zend_Registry::get('bootstrap')->getResource('jobs')->send('YourJob');
```

</div>

</div>

Your other option is intended for processes that will most likely result
in a timeout error if run as a normal web script. Processes that import
thousands of records or convert hundreds of images are examples of such
processes. You can run these processes like so,

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
Zend_Registry::get('bootstrap')->getResource('jobs')->sendLongRunning('YourJob');
```

</div>

</div>

It's important to note that nothing that uses the job system should
assume or require synchronicity with the web process. If your process
*has to* be synchronous, it shouldn't be a job.

### <span id="Phased_Loading" class="mw-headline">Phased Loading</span>

In previous versions, long running processes were fired directly through
a background process via `ProcessDispatcher::startProcess()`, which
loaded resources (e.g. Db, Option, Pluginbroker) in phases. **Phased
loading is now removed in favor of loading resources when needed.**

When using the background process adapter for your jobs (typically used
for long running jobs), the following resources are pre-loaded for you:
Autoloader, Config, Db, Options, Pluginbroker, Plugins, Jobs, Storage,
Mail. If you need other resources, load them like so in your job:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
Zend_Registry::get('bootstrap')->bootstrap('Db');
```

</div>

</div>

<span id="Hooks_and_Filters" class="mw-headline"> Hooks and Filters </span>
---------------------------------------------------------------------------

### <span id="New_Hooks" class="mw-headline"> New Hooks </span>

-   navigation\_form
-   `search_sql`
-   public\_append\_to\_home

### <span id="Renamed_Hooks" class="mw-headline"> Renamed Hooks </span>

primary and secondary renamed content and sidebar for item and form show
pages

after\_upload\_file no after\_ingest\_file

### <span id="Removed_Hooks" class="mw-headline"> Removed Hooks </span>

insert, update, save\_form, and validate hooks have been removed (this
supercedes what might be listed below)

\
 In previous versions of Omeka, hook and filter callbacks accepted any
number of arguments that could be useful during implementation. **Now,
in 2.0, we've consolidated these arguments into one array.** Because of
this change, writing your callbacks will be easier and self-documenting:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// Add a hook.
add_plugin_hook('after_save_item', 'my_hook_callback');
 
// Define the hook callback. Note the single $args array instead of
// the list of function arguments used in previous versions.
function my_hook_callback($args)
{
    // Extract the arguments only as needed.
    $item = $args['record'];
 
    // Do something.
}
 
// Add a filter.
add_filter(array('Display', 'Item', 'Dublin Core', 'Title'),
           'my_filter_callback');
 
// Define the filter callback. Note the single $args array instead 
// of the list of function arguments used in previous versions.
function my_filter_callback($title, $args)
{
    // Extract the arguments only as needed.
    $itemRecord = $args['record'];
    $titleElementTextRecord = $args['element_text'];
 
    // Filter the value and return it...
    return $title;
}
```

</div>

</div>

The following hooks have been modified to accommodate the above changes.
Hook names are followed by their available arguments (accessed via the
\$args keys).

Hooks that previously received a request object should now obtain that
object within the callback itself like so:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
    $request = Zend_Controller_Front::getInstance()->getRequest();
```

</div>

</div>

\

\

-   admin\_append\_to\_users\_form: form, user
-   general\_settings\_form: form
-   browse\_tags: tags, for
-   \*\_browse\_sql: select, params
-   define\_routes: router
-   html\_purifier\_form\_submission: purifier
-   browse\_\*: records
-   show\_\*: record
-   after\_upload\_file: file, item
-   after\_ingest\_file: file, item
-   admin\_theme\_footer
-   admin\_theme\_header
-   public\_theme\_footer
-   public\_theme\_header
-   public\_theme\_body
-   public\_theme\_page\_header
-   public\_theme\_page\_content
-   before\_upload\_files: item
-   add\_\*\_tag: record, added
-   remove\_\*\_tag: record, removed
-   make\_\*\_public: record
-   make\_\*\_not\_public: record
-   make\_\*\_featured: record
-   make\_\*\_not\_featured: record
-   items\_batch\_edit\_custom: item, custom
-   admin\_append\_to\_collections\_form: collection
-   admin\_append\_to\_collections\_browse\_primary: collections
-   admin\_append\_to\_collections\_show\_primary: collection
-   admin\_append\_to\_items\_form\_files: item
-   append\_to\_item\_form: item
-   admin\_append\_to\_items\_browse\_primary: items
-   admin\_append\_to\_items\_batch\_edit\_form
-   admin\_append\_to\_items\_show\_secondary: item
-   admin\_append\_to\_items\_show\_secondary: item
-   admin\_append\_to\_items\_form\_tags: item
-   admin\_append\_to\_items\_form\_collection: item
-   admin\_append\_to\_files\_form: file
-   admin\_append\_to\_files\_show\_primary: file
-   admin\_append\_to\_files\_show\_secondary: file
-   admin\_append\_to\_item\_types\_form: item\_type
-   admin\_append\_to\_item\_types\_browse\_primary: item\_types
-   admin\_append\_to\_item\_types\_show\_primary: item\_type
-   config: post
-   define\_acl: acl
-   upgrade: old\_version, new\_version
-   install: plugin\_id
-   before\_save\_form\_record: record, post
-   after\_save\_form\_record: record, post
-   before\_insert\_record: record
-   before\_update\_record: record
-   before\_save\_record: record
-   after\_insert\_record: record
-   after\_update\_record: record
-   after\_save\_record: record
-   before\_delete\_record: record
-   after\_delete\_record: record
-   before\_save\_form\_\*: record, post
-   after\_save\_form\_\*: record, post
-   before\_insert\_\*: record
-   before\_update\_\*: record
-   before\_save\_\*: record
-   after\_insert\_\*: record
-   after\_update\_\*: record
-   after\_save\_\*: record
-   before\_delete\_\*: record
-   after\_delete\_\*: record

The following filters have been modified to accommodate the above
changes. Filter names are followed by their available arguments
(accessed via the \$args keys):

-   login\_adapter: login\_form
-   items\_batch\_edit\_error: metadata, custom, item\_ids
-   storage\_path: filename, type
-   item\_citation: item
-   display\_search\_filters: request\_array
-   array(Display, Record): record, element\_text
-   array(Form, Record): input\_name\_stem, value, record, element
-   element\_form\_display\_html\_flag: element
-   display\_file: file, callback, options, wrapper\_attributes
-   array(Save, Record): record, element
-   array(Flatten, Record): post\_array, element
-   array(Validate, Record): text, record, element
-   theme\_options: theme\_name
-   admin\_items\_form\_tabs: item
-   define\_action\_contexts: controller, context\_switcher

### <span id="New_Filters" class="mw-headline"> New Filters </span>

-   `<model>_browse_params`
-   `record_metadata_elements`
-   `public_navigation_admin_bar`
-   `search_record_types`
-   `admin_navigation_global`
-   admin\_dashboard\_stats
-   admin\_dashboard\_panels
-   item\_search\_filters

### <span id="Changed_Filters" class="mw-headline"> Changed Filters </span>

  Old Filter             New Filter
  ---------------------- ------------------------------
  display\_setting\_\*   display\_option\_\*
  array('Form' ....)     array('ElementInput' . . . )

### <span id="Removed_Filters" class="mw-headline"> Removed Filters </span>

-   admin\_navigation\_items\_browse
-   admin\_navigation\_tags

<span id="Search" class="mw-headline"> Search </span>
-----------------------------------------------------

Omeka 2.0 allows any record to be full-text searchable, not just items,
but also files, collections, exhibits, etc.

**Individual record indexing and bulk-indexing will only work on record
types that have been registered via the new "search\_record\_types"
filter:**

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// Tell Omeka where your search_record_types callback is. 
add_filter('search_record_types', 'your_search_record_types_callback');
 
// Accept an array and return an array.
function your_search_record_types_callback(array $searchableRecordTypes)
{
    // Register the name of your record class. The key should be the name 
    // of the record class; the value should be the human readable and 
    // internationalized version of the record type.
    $searchableRecordTypes['YourRecord'] = __('Your Record');
    return $searchableRecordTypes;
}
```

</div>

</div>

Follow this template to make your record searchable:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
class YourRecord extends Omeka_Record_AbstractRecord
{
    // Add the search mixin during _initializeMixins() and after any mixins
    // that can add search text, such as Mixin_ElementText. Doing this
    // tells Omeka that you want this record to be searchable.
    protected function _initializeMixins()
    {
        // Add the search mixin.
        $this->_mixins[] = new Mixin_Search($this);
    }
 
    // Use the afterSave() hook to set the record's search text data.
    protected function afterSave($args)
    {
        // A record's search text is public by default, but there are times
        // when this is not desired, e.g. when an item is marked as
        // private. Make a check to see if the record is public or private.
        if ($private) {
            // Setting the search text to private makes it invisible to
            // most users.
            $this->setSearchTextPrivate();
        }
 
        // Set the record's title. This will be used to identify the record
        // in the search results.
        $this->setSearchTextTitle($recordTitle);
 
        // Set the record's search text. Records that implement the
        // Mixin_ElementText mixin during _initializeMixins() will
        // automatically have all element texts added. Note that you
        // can add multiple search texts, which simply appends them.
        $this->addSearchText($recordTitle);
        $this->addSearchText($recordText);
    }
 
    // The search results need a route to the record show page, so build 
    // a routing array here. You can also assemble the URL yourself using 
    // the URL view helper and return the entire URL as a string.
 
    // The abstract Omeka_Record_AbstractRecord class has this method,
    // so you only need to override it if the route to your record does 
    // something unusual
 
    public function getRecordUrl($action)
    {
        if ('your-show-action' == $action) {
            return array(
                'module' => 'your-module', 
                'controller' => 'your-controller', 
                'action' => $action,
                'id' => $this->id, 
            );
        }
        return parent::getRecordUrl($action);
    }
}
```

</div>

</div>

### <span id="Indexing_Your_Records" class="mw-headline"> Indexing Your Records </span>

Indexing means to collect, parse, and store data to facilitate fast and
accurate searches. Omeka will index individual records as they are
saved, but there are circumstances when your records are not indexed;
for instance, when updating from an earlier version of Omeka.

**In 2.0 we've added a feature that lets you index all your records at
one time.** Just go to the new search settings page on the settings tab
and press the index button. This is done using a background process so
you may continue administering your site while it indexes. The process
may take a while to complete.

### <span id="Customizing_Search_Type" class="mw-headline"> Customizing Search Type </span>

Omeka now comes with three search query types: full text, boolean, and
exact match. Full text and boolean use [MySQL's native full text
engine](http://dev.mysql.com/doc/refman/5.0/en/fulltext-search.html),
while exact match searches for all strings identical to the query.

Plugin authors may customize the type of search by implementing the
`search_query_types` filter. For example, if you want to implement a
"ends with" query type that searches for records that contain at least
one word that ends with a string:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
// Tell Omeka where your search_query_types callback is. 
add_filter('search_query_types', 'your_search_query_types_callback');
 
// Accept an array and return an array.
function your_search_query_types_callback($queryTypes)
{
    // Register the name of your custom query type. The key should be the
    // type's GET query value; the values should be the human readable and
    // internationalized version of the query type.
    $queryTypes['ends_with'] = __('Ends with');
    return $queryTypes;
}
```

</div>

</div>

Then you must modify the search SQL, like so:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
add_plugin_hook('search_sql', 'your_search_sql_callback');
function your_search_sql_callback($args)
{
    $params = $args['params'];
    if ('ends_with' == $params['query_type']) {
        $select = $args['select'];
        // Make sure to reset the existing WHERE clause.
        $select->reset(Zend_Db_Select::WHERE);
        $select->where('`text` REGEXP ?', $params['query'] . '[[:>:]]');
    }
}
```

</div>

</div>

Remember that you're searching against an aggregate of all texts
associated with a record, not structured data about the record.

<span id="Plugin_Hooks" class="mw-headline"> Plugin Hooks </span>
-----------------------------------------------------------------

The functions that theme developers should use to fire plugin hooks have
been removed. Instead of, for example,

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
echo plugin_append_to_collections_show()
```

</div>

</div>

use

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
fire_plugin_hook('append_to_collections_show');
```

</div>

</div>

<span id="Testing" class="mw-headline"> Testing </span>
-------------------------------------------------------

Previously, plugins had to add setUp code to make sure that their hooks
and filters were reloaded on each test run. This is no longer required.
Simply using the Plugin test helper will correctly re-load the hooks and
filters every time.

As a side effect, plugin.php can no longer contain declarative code
(declaring functions, classes, etc.). This was already an informal rule,
with many plugins separating into plugin.php and functions.php files,
but now the plugin loader assumes plugins are written this way. Using
the Omeka\_Plugin\_AbstractPlugin class in a separate file will
naturally cause this separation (and even allows you to omit plugin.php
entirely).

<span id="Development_Environment" class="mw-headline"> Development Environment </span>
---------------------------------------------------------------------------------------

The .htaccess file has added a

setEnv APPLICATION\_ENV development

directive. Make sure that you update your .htaccess file.

<span id="Admin_Views" class="mw-headline"> Admin Views </span>
---------------------------------------------------------------

Example structure of a fieldset within a form:

<div class="mw-geshi mw-content-ltr" dir="ltr">

<div class="php source-php">

``` {.de1}
 <div class="field">
   <div id="administrator_email-label" class="two columns alpha"><label for="administrator_email" class="required">Administrator Email</label></div>
   <div class="inputs five columns omega"><input type="text" name="administrator_email" id="administrator_email" value="knguye27@gmu.edu <mailto:value=%22knguye27@gmu.edu>"></div>
</div>
```

</div>

</div>

Follows these guides:

-   <http://www.getskeleton.com/>
-   <https://github.com/dhgamache/Skeleton/blob/master/stylesheets/skeleton.css>

<div class="printfooter">

Retrieved from
"[http://omeka.org/codex/Updating\_Plugins\_For\_2.0](Updating_Plugins_For_2.0.html)"

</div>

<div id="catlinks" class="catlinks">

<div id="mw-normal-catlinks">

[Category](http://omeka.org/codex/Special:Categories "Special:Categories"):
<span
dir="ltr">[Drafts](http://omeka.org/c/index.php?title=Category:Drafts&action=edit&redlink=1 "Category:Drafts (page does not exist)")</span>

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

    [Page](Updating_Plugins_For_2.0.html)
-   <div id="nav-discussion">

    </div>

    [Discussion](http://omeka.org/c/index.php?title=Talk:Updating_Plugins_For_2.0&action=edit&redlink=1)
-   <div id="nav-view_source">

    </div>

    [View
    source](http://omeka.org/c/index.php?title=Updating_Plugins_For_2.0&action=edit)
-   <div id="nav-history">

    </div>

    [History](http://omeka.org/c/index.php?title=Updating_Plugins_For_2.0&action=history)

</div>

<div id="wiki-toolbox" class="portlet">

Toolbox
-------

-   <div id="t-whatlinkshere">

    </div>

    [What links
    here](Special:WhatLinksHere/Updating_Plugins_For_2.0.html)
-   <div id="t-recentchangeslinked">

    </div>

    [Related
    changes](Special:RecentChangesLinked/Updating_Plugins_For_2.0.html)
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
