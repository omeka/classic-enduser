---
title: Release Notes for 2.0
---
Omeka 2.0 is the second major release. It represents many fundamental changes and improvements to the core and development API

----------------------------------------------------------------

-   Fixed [numerous issues](https://github.com/omeka/Omeka/issues?milestone=1&page=1&state=closed)
-   Shifted naming conventions for better comformity to upcoming Zend 2.0 standards
-   Removed Data Types from ElementTexts
-   Removed Entities to represent Users. All user information is now directly on User objects
-   Added Dublin Core information to Collections
-   Removed Orderable mixin
-   Added Searchable mixin
-   Ownable mixin now named Mixin\_Owner
-   Taggable mixin now named Mixin\_Tag
-   ActsAsElementText mixin now named Mixin\_ElementText
-   PublicFeatures mixin now named Mixin\_PublicFeatured
-   Omeka\_Acl removed. User Zend\_Acl instead
-   Derivative images now produced for many more file types
-   archive directory changed to files
-   archive/files directory changed to files/original
-   Phased loading is now removed in favor of loading resources when
    needed

API Changes
---------------------------------------------------------------

-   Removed many functions with overlapping or similar functionality [details](Updating_Plugins_For_2.0.html#Helper_Functions)
-   Functions no long echo directly and instead return values
-   Form functions have been removed in favor of using [Zend Form     Helpers](http://framework.zend.com/manual/en/zend.view.helpers.html)
-   Many new and renamed hooks and filters [details](Updating_Plugins_For_2.0.html#Hooks_and_Filters)
-   Arguments passed to all hooks consolidated into one \$args array
-   beforeSaveForm() and afterSaveForm() callbacks removed from records
-   Omeka\_Form\_Admin class added to help build simple admin forms
-   Omeka\_Plugin class renamed Omeka\_Plugin\_AbstractPlugin
-   Controllers should now extend Omeka\_Controller\_AbstractActionController
-   Models should now extend Omeka\_Record\_AbstractRecord
-   Db wrappers removed :getDb, getTable, and findById are replaced by equivalent calls to \_helper-&gt;db-&gt;{methodName}.
-   Omeka\_Context removed in favor of using Zend\_Registry
-   Plugins can now add their content to search with Mixin\_Search

Additional details can be found [in the codex](Updating_Plugins_For_2.0.html) and [in the new documentation](http://omeka.readthedocs.org/en/latest/Tutorials/migratingCodeTo2.0.html)