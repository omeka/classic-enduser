Plugins/ItemRelations 2.0
=========================

[Plugins](../Plugins.1.html "Plugins")

The Item Relations plugin lets you **define relations between items**.
For example, you can make one item a part of another item, where "part
of" is the relation. You can also make one item a "reproduction of" or a
"translation of" another item.

We've bundled the plugin with common relations derived from several
**formal vocabularies**, including [Dublin Core](http://dublincore.org/documents/dcmi-terms/),
[FRBR](http://vocab.org/frbr/core.html),
[FOAF](http://xmlns.com/foaf/spec/), and
[BIBO](http://bibotools.googlecode.com/svn/bibo-ontology/trunk/doc/index.html).
You may use these or create a **custom vocabulary** with the relations
needed in your site. You could, for example, define custom relations
like "is parent of," "is better than," and "fits within."

Instructions 
-----------------------------------------------------------------

After you
[install](../Managing_Plugins_2.0.html#Installing_a_Plugin "Managing Plugins 2.0")
the plugin you'll be given the opportunity to configure it.

1.  Decide if you want to display an item's relations on its public show
    page
2.  Select the format of an item's relations that you'd prefer to appear
    on the item page: prefix:localPart or the label given to
    that relationship.

### Customize Relationship Vocabulary

On the "Item Relations" tab in the left side of the admin navigation you
will find the vocabularies available and their **properties** (a more
general term for relations).

If you wish to create your own vocabulary, edit the "Custom" vocabulary
by clicking on "Edit Custom Vocabulary" in its property show page. Here
you can add, edit, and delete properties in your custom vocabulary.

### Relating Items

When adding or editing an item, click on the "Item Relations" tab, at
the top of the admin/item page to relate the item to another item, or to
delete existing relations.

To relate need the item ID of the other item to define a relation.

You may batch relate items using the Batch Edit function from the Browse
Items pages in the admin.

Item Relations and RDF
-------------------------------------------------------------------------------------

The plugin follows the [RDF](http://en.wikipedia.org/wiki/Resource_Description_Framework) model
for defining relations between items. There's a subject item, a
predicate (a relation/property in this case), and an object item. If we
decompose the sentence: "Item 1 is a part of Item 2," "Item 1" is the
subject, "is a part of" is the predicate, and "Item 2" is the object.
These **triples** are the foundation of RDF. Your end users won't have
to know this, but it's helpful to know it as an administrator.

Following RDF, every formal vocabulary has a **namespace prefix** and
**namespace URI**, which provide unambiguous context for its
relations/properties. Every property has a **local part** and/or
**label**, which are machine-readable and human-readable names of the
property, respectively. As an administrator you'll only need to create
labels, everything else is there for XML and RDFS compliance, to be used
for future output formats.

