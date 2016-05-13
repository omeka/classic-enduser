Working with Dublin Core
========================

Why Dublin Core?
----------

The Omeka team decided that we wanted to contribute to a movement that is helping to standardize data about digital objects. While there are different standards available, the Dublin Core Metadata Initiative is the most widely adopted and offers users the greatest flexibility.

-   [Learn more about the Dublin Core Metadata Initiative](http://dublincore.org/documents/usageguide/)

-   [Historical overview and bibliography of Dublin Core resources](http://www.oclc.org/research/activities/past/orprojects/dublincore/default.htm).

Interpreting Dublin Core Fields in Omeka 
--------------------------------------------------------

The following Dublin Core fields are available in Omeka, together with some suggestions on interpreting the fields. The fields are vague by design so please consult with the [DCMI element descriptions](http://dublincore.org/documents/usageguide/elements.shtml) to be sure you are fulfilling the demands of your project.

Read one example of Dublin Core interpretations from the [North Carolina Exploring Culture and Heritage Online](http://www.digitalnc.org/about/participate/describe/) project.

**Title:** A name given to the resource. Examples: title of a painting, photo, document; the name of a person when using the "person" item type; the name of a lesson plan.

**Subject:** The topic of the resource. Typically, the topic will be represented using keywords, key phrases, or classification codes. Recommended best practice is to use a controlled vocabulary. To describe the spatial or temporal topic of the resource, use the Coverage element. Examples: Library of Congress subject headings; subject-specific nomenclature.

**Description:** An account of the resource. Description may include but is not limited to: an abstract, a table of contents, a graphical representation, or a free-text account of the resource. 
Examples: a photo caption; descriptive information of an artifact/museum object; summary of a lesson plan; abstract or summary of a long document;

**Creator:** An entity primarily responsible for making the resource. Examples: Author/authors; artists; photographers; institutional authors or producers, such as university or federal agency.

**Source:** The resource from which the described resource is derived. The described resource may be derived from the related resource in whole or in part. Recommended best practice is to identify the related resource by means of a string conforming to a formal identification system. Examples: Accession number; Collection of objects; Division of an archive or library.

**Publisher:** An entity responsible for making the resource available. Examples: actual publisher, if there is one; entity or consortium publishing digital materials.

**Date:** A point or period of time associated with an event in the lifecycle of the resource. Date may be used to express temporal information at any level of granularity. Recommended best practice is to use an encoding scheme, such as the W3CDTF profile of ISO 8601 (W3CDTF) Date is one of the trickiest fields to fill. You will want to decide how best to use it for your project for consistency. There is an open text field for date so that you can reflect the type of date information you have whether it is a very specific date MM/DD/YYYY or if it is "circa 1940".

**Contributor** An entity responsible for making contributions to the resource. Examples: person who contributed a story or file for an Omeka collecting project; owner or donor of collected objects;

**Rights** Information about rights held in and over the resource. Typically, rights information includes a statement about various property rights associated with the resource, including intellectual property rights. Examples: spell out conditions of use for specific items here; Creative Commons type; Public Domain.

**Relation** A related resource. Recommended best practice is to identify the related resource by means of a string conforming to a formal identification system. Examples: a still image of a person entered as a "person" type.

**Format** The file format, physical medium, or dimensions of a
resource. Examples include size and duration. Recommended best practice is to use a controlled vocabulary such as the Internet Media Types (MIME).

**Language** A language of the resource. Examples: English; Russian; Spanish, et al.

**Type** The nature or genre of the resource. Recommended best practice is to use a controlled vocabulary such as the DCMI Type Vocabulary (DCMITYPE). To describe the file format, physical medium, or dimensions of the resource, use the Format element. Examples: For consistency, use item type controlled vocabulary provided by Omeka: Document, Moving Image, Oral History, Sound, Still Image, Website, Event, Email, Lesson Plan, Hyperlink, Person, or Interactive Resource.

**Identifier**: An unambiguous reference to the resource within a given context. Recommended best practice is to identify the resource by means of a string conforming to a formal identification system.

**Coverage** : The spatial or temporal topic of the resource, the spatial applicability of the resource, or the jurisdiction under which the resource is relevant. Spatial topic and spatial applicability may be a named place or a location specified by its geographic coordinates. Temporal topic may be a named period, date, or date range. A jurisdiction may be a named administrative entity or a geographic place to which the resource applies. Recommended best practice is to use a controlled vocabulary such as the Thesaurus of Geographic Names (TGN). Where appropriate, named places or time periods can be used in preference to numeric identifiers such as sets of coordinates or date ranges.
