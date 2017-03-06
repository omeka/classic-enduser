---
title: Controlling Editing Access on Plugin Content
---
PatrickMJ 2012

Problem
-------------------------------------------------------
Your plugin adds a model for content. You want many roles to see and add that type of content, but only the creator of that content should beable to edit it.

Solution 1
-------------------------------------------------------------
This solution only works in Omeka 1.5 or above

We'll need to make use of the Ownable mixin on your model, and the Omeka_Assert_Ownership class in defining the Acl.

### Creating the Model Class
In addition to the usual extending of the Omeka\_Record class, you will also implement Zend_Acl_Resource_Interface. There is only one method from Zend_Acl_Resource_Interface that you will need to implement: getResourceId()

getResourceId() simply returns the name of the resource that you will add to the Acl in your plugin. In Acl-speak, this is the name of the controller for the model.

The Ownable mixin handles most of the heavy lifting. You just need to initialize it as part of the model class, and tell it what database column carries the user id of the owner. The default value is 'owner_id';

``` {.de1}
class SpecialContent extends Omeka_Record implements Zend_Acl_Resource_Interface
{
    public $id;
    public $content;
    public $user_id;
 
    protected function _initializeMixins()
    {
        $this->_mixins[] = new Ownable($this, 'user_id');
    }
 
// other methods that your model might need . . .
 
    public function getResourceId()
    {
        return 'SpecialContent_ContentController';
    }
 
 
}
```

That much takes care of the model. Now let's turn to setting up the Acl itself. Your plugin will do this via the define_acl hook. First, you assert what privileges each role should have. Then, you will use the Omeka_Assert_Ownership class in a second assertion.

``` {.de1}
$acl->allow(array('researcher', 'contributor'), 'SpecialContent_Content', array('add', 'editSelf'));
$acl->allow(array('researcher', 'contributor'), 'SpecialContent_Content', 'edit', new Omeka_Acl_Assert_Ownership);
```

The first line gives researchers and contributors the ability to add content and sets up those roles to only edit their own content. The second line sets up the actual ownership checking. Notice that the third parameter is 'edit', not 'editSelf', in the second line.

So a snippet of the plugin might look like:

``` {.de1}
class SpecialContentPlugin extends Omeka_Plugin_Abstract
{
    protected $_hooks = array('define_acl');
 
    public function hookDefineAcl($acl)
    {
        $acl->allow(array('researcher', 'contributor'), 'SpecialContent_Content', array('add', 'editSelf'));
        $acl->allow(array('researcher', 'contributor'), 'SpecialContent_Content', 'edit', new Omeka_Acl_Assert_Ownership);
 
    }
}
```


Chances are you would also want the same principle for deleting content. That would follow a very similar pattern:

``` {.de1}
$acl->allow(array('researcher', 'contributor'), 'SpecialContent_Content', array('add', 'editSelf', 'deleteSelf'));
 
$acl->allow(array('researcher', 'contributor'), 'SpecialContent_Content', array('edit', 'delete'), new Omeka_Acl_Assert_Ownership);
```

Remember that the above assumes a controller called
'SpecialContent_ContentController', with methods addAction(), editAction(), and deleteAction() that correspond to the privileges we're working with. Of course, those methods are already present in the Omeka_Controller_Action class that you would be extending. I'm only pointing that out here by way of saying that the same approach can be used for any additional actions that you add to your controller.

### Hooks used
[define_acl]