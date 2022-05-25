# Working with Dublin Core

Why Dublin Core?
----------

The Omeka team decided that we wanted to contribute to a movement that is helping to standardize data about digital objects. While there are different standards available, the Dublin Core Metadata Initiative is the most widely adopted and offers users the greatest flexibility.

- [About the Dublin Core Metadata Initiative](http://dublincore.org/about/){target=_blank}
- [Dublin Core Metadata Element Set, Version 1.1: Reference Description](http://dublincore.org/documents/dces/){target=_blank}; [Latest version here](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#section-3){target=_blank}
- [Historical overview and bibliography of Dublin Core resources (2010)](http://www.oclc.org/research/activities/past/orprojects/dublincore/default.htm){target=_blank}

Interpreting Dublin Core Fields in Omeka Classic 
--------------------------------------------------------

The following Dublin Core fields are available in Omeka, together with some suggestions on interpreting the fields. The fields are broad and loosely-defined by design, so please consult with the [DCMI element descriptions](http://dublincore.org/documents/usageguide/elements.shtml){target=_blank} to be sure you are meeting the specific needs of your project. 

Read one example of Dublin Core interpretations from the [North Carolina Exploring Culture and Heritage Online](https://www.digitalnc.org/partners/describing-your-materials/){target=_blank} project.

For almost any field, the [Library of Congress Suggest](../Plugins/Library_of_Congress_Suggest.md) plugin can supply you with the ability to select from a controlled vocabulary. This includes not just subject headings but people, places, and other authorities offered by LC. 

With the [Simple Vocab plugin](../Plugins/SimpleVocab.md) you can design custom controlled vocabularies, such as a list of notable people relevant to your materials, and attach them to the Dublin Core elements below.

You may also want to review the detailed breakdown of [item types](Item_Types.md) with examples and a list of their item type metadata elements, and customize the Dublin Core fields most useful to you based on the item type.

With these tools, you can plan a comprehensive and coordinated approach to using the Dublin Core fields in your Omeka site. 

### Title

A name given to the resource.

Examples: title of a painting, photo, document; the name of a person when using the "person" item type; the name of a lesson plan.

### Subject

The topic of the resource.

Typically, the topic will be represented using keywords, key phrases, or classification codes. Recommended best practice is to use a controlled vocabulary. To describe the spatial or temporal topic of the resource, use the [Coverage](#coverage) element. Examples: Library of Congress subject headings; subject-specific nomenclature.

### Description

An account of the resource.

Description may include but is not limited to: an abstract, a table of contents, a graphical representation, or a free-text account of the resource. 

### Creator

An entity primarily responsible for making the resource.

Examples: the author(s), artist(s), or photographer; institutional author(s), such as a university or federal agency.

### Source

The resource from which the described resource is derived.

The described resource may be derived from the related resource in whole or in part. Recommended best practice is to identify the related resource by means of a string conforming to a formal identification system, such as a URL to another descriptive page. 

You may wish to use this field to indicate that the file in your Omeka database is a digital surrogate of a physical item, and give the call number or citation, or clarify that is an excerpt and give information about the encompassing source (e.g. one photograph in a photo album; one slide from a slide collection; an audio clip from a longer recording; one document from an archival collection).  

For a related way to express this information, see the [Identifier](#identifier) field.

### Publisher

An entity responsible for making the resource available.

Examples: actual publisher, if there is one; entity or consortium publishing digital materials; holding institution such as a museum or archives.

### Date

A point or period of time associated with an event in the lifecycle of the resource.

Date may be used to express temporal information at any level of granularity. Recommended best practice is to use an encoding scheme, such as the [W3CDTF](https://www.w3.org/TR/NOTE-datetime){target=_blank} profile of [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html){target=_blank}.

A resource may have several dates associated with it, including: creation date, copyright date, revision date, edition date, modification date, etc. You could use separate Date elements to enter multiple dates, but you cannot specify the meaning of each within Omeka Classic. 

You may want to use this field for a specific point in time, such as a publication or creation date, and use the [Coverage](#coverage) field to specify a duration, such as the earliest and last entry dates of a personal diary, or more topically, such as the period of time the resource is about. 

Date can be one of the trickiest fields to fill. You will want to decide how best to use it for your project for consistency. Where possible, a structured date such as YYYY-MM-DD for a specific day or YYYY for a specific year is preferred, but other formats or levels of specificity can be used (such as "circa 1940" or "18??").

### Contributor

An entity responsible for making contributions to the resource.

Entries here should be akin to the [Creator](#creator) field, but for entities that made a less significant or unknown contribution.

### Rights

Information about rights held in and over the resource.

Typically, rights information includes a statement about various property rights associated with the resource, including intellectual property rights.

Examples: spell out conditions of use for specific items here; Creative Commons or other specific license; Public Domain.

### Relation

A related resource.

Recommended best practice is to identify the related resource by means of a string conforming to a formal identification system.

Example: Specify that a still image is the portrait of a person entered separately as a "person" type; identify an item as the sequel or addendum to another item. 

### Format

The file format, physical medium, or dimensions of a resource.

Examples: the [Internet media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of a digital file; the physical size of an object; the duration of a film or audio clip; or the medium of a work of art.

You may find it useful to use more specific format-specific fields attached to the [Item Types](../Admin/Settings/Item_Type_Elements.md). 

### Language

One or more languages of the resource.

[IETF BCP 47 language tags](https://en.wikipedia.org/wiki/IETF_language_tag){target=_blank} are the suggested standard, created by the Internet Engineering Task Force (IETF) and documented in *Best Current Practice (BCP) 47*.

### Type

The nature or genre of the resource.

Recommended best practice is to use a controlled vocabulary such as the [DCMI Type Vocabulary](http://dublincore.org/documents/dcmi-terms/#section-7). 

To describe the file format, physical medium, or dimensions of the resource, use the [Format](#format) element.

### Identifier

An unambiguous reference to the resource within a given context.

Recommended best practice is to identify the resource using a formal identification system, such as an ISBN, or a catalog number, or a URL to an external authority.

### Coverage

The spatial or temporal topic of the resource, the spatial applicability of the resource, or the jurisdiction under which the resource is relevant.

Spatial topic and spatial applicability may be a named place or a location specified by its geographic coordinates. Temporal topic may be a named period, date, or date range. A jurisdiction may be a named administrative entity or a geographic place to which the resource applies.

Recommended best practice is to use a controlled vocabulary such as the [Thesaurus of Geographic Names (TGN)](http://www.getty.edu/research/tools/vocabularies/tgn/index.html){target=_blank}. Where appropriate, named places or time periods can be used in preference to numeric identifiers such as sets of coordinates or date ranges.
