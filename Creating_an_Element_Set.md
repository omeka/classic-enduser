
Creating an Element Set
=======================


First of all, what is an element set?
-----------------------------------------------------------------------------------------------------------------------

It's best to think of an element set as a set of related elements that are available to all items, regardless of item type. For example, we've included the [Dublin Core Metadata Element
Set](http://dublincore.org/documents/dces/) in all new Omeka installations. Dublin Core is an internationally recognized standard for describing any conceivable resource. This element set comprises 15 elements, including "title," "description," "date," and "format." While it is not required, we strongly recommend that you mark up all your items using the Dublin Core element set because doing so will standardize your repository's metadata and facilitate interoperability.

Whereas Dublin Core is a generic set of elements used to describe any item, there can be other, more domain-specific element sets. For example, art museums may consider adding a [CDWA Lite](http://www.getty.edu/research/conducting_research/standards/cdwa/cdwalite.html) element set, which contains elements that describe core records for works of art and material culture. Libraries may consider adding a [METS](http://www.loc.gov/standards/mets/) element set, which contains elements for encoding descriptive, administrative, and structural metadata regarding objects within a digital library. And archives may consider adding an [EAD](http://www.loc.gov/ead) element set, which contains elements for describing the content and intellectual organization of collections of archival materials.

You may have noticed that element sets resemble Omeka's item types, so it is important to make a distinction. An element set is intended to represent a formal metadata schema that may be applied to all items. An item type is a useful but informal aggregation of custom elements that describe a particular type of item. ("Document," "Email," and "Oral History" are examples of item types.) The biggest difference here is that element sets are available for all items, while item type elements are available only to those items that belong to that item type. So, if you need a standardized set of elements that is available across all item types, an element set is the way to go.

Creating an element set
---------------------------------------------------------------------------------------

There is no way to create or edit element sets using Omeka's administrative interface. Element sets will only be distributed via Omeka plugins. This may seem inconvenient, but we want to encourage strict adherence to a formal schema, which, in turn, will standardize your data within and across repositories.

To create an element set, you must write a plugin that adds the element set and its associated elements to the Omeka database. Simply map your schema of choice to the \`element\_sets\` and \`elements\` tables. For your convenience, Omeka includes the insert\_element\_set() helper function, which creates a custom element set and its associated elements:

``` {.de1}
$elementSetMetadata = array(
    'name'        => [(string) element set name, required, unique], 
    'description' => [(string) element set description, optional]
);
$elements = array(
    array(
        'name'           => [(string) name, required],
        'description'    => [(string) description, optional],
        'record_type'    => [(string) record type name, optional],
        'data_type'      => [(string) data type name, optional],
        'record_type_id' => [(int) record type id, optional],
        'data_type_id'   => [(int) data type id, optional]
    ), 
    // etc.
);
insert_element_set($elementSetMetadata, $elements);
```


To simulate hierarchical elements in your schema we recommend delimiting the elements with a colon. For example, in the full Dublin Core list of terms, "created" is a refinement of "date," so an element with the name "date:created" is sufficient.