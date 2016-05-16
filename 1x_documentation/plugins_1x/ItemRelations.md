Plugins/ItemRelations
=====================


[Plugins](../Plugins.1.html "Plugins")


The Item Relations plugin lets you **define relations between items**.
For example, you can make one item a part of another item, where "part
of" is the relation. You can also make one item a "reproduction of" or a
"translation of" another item.

We've bundled the plugin with common relations derived from several
**formal vocabularies**, like [Dublin Core](http://dublincore.org/documents/dcmi-terms/) and
[FRBR](http://vocab.org/frbr/core.html). You can use these or you could
populate a **custom vocabulary** with the relations needed in your
archive. You could, for example, define custom relations like "is parent
of," "is better than," and "fits within."

Instructions
-----------------------------------------------------------------

After you install the plugin you'll be given the opportunity to
configure it. You can 1) indicate whether you want to display an item's
relations on its public show page; and 2) select the format of an item's
relations that you'd prefer to show: prefix:localPart or label (see
below under "Item Relations and RDF"). You can always reconfigure the
plugin by going to the "Plugins" tab on the "Settings" page.

On the "Item Relations" tab on the main navigation you can browse the
vocabularies and their **properties** (a more general term for
relations). You can edit the "Custom" vocabulary by clicking on "Edit
Custom Vocabulary" in its property show page. Here you can add, edit,
and delete properties in your custom vocabulary.

When adding or editing an item, click on the "Item Relations" tab to
relate the item to another item and delete existing relations. For now
you'll need the item ID of the other item to define a relation, but we
plan to add a more user-friendly item selector system in a future
version.

In version 1.1, users may batch relate items using the Batch Edit
function for items.

Item Relations and RDF 
-------------------------------------------------------------------------------------

The plugin follows the
[RDF](http://en.wikipedia.org/wiki/Resource_Description_Framework) model
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
