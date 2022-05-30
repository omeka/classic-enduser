# Output Formats

Omeka Classic uses Zend Framework's [ContextSwitch](https://framework.zend.com/manual/1.12/en/zend.controller.actionhelpers.html#zend.controller.actionhelpers.contextswitch){target=_blank} action helper to return different response formats on request. Omeka Classic comes bundled with several response formats: omeka-xml, omeka-json, dcmes-xml, json, and rss2. See below for more information about these bundled formats.

To access the response formats, simply add `output=format-name` to the URL query string. For example:

` http://www.example.com/items/show?output=omeka-xml `

## omeka-xml

The *omeka-xml* response format is an XML instance of the official Omeka Classic omeka-xml schema. It is currently available on the following pages:

-   items/browse
-   items/show
-   files/show

## dcmes-xml

The *dcmes-xml* response format is an [RDF/XML](http://www.w3.org/TR/rdf-syntax-grammar/){target=_blank} instance of [simple Dublin Core](https://www.dublincore.org/specifications/dublin-core/dcmes-xml/){target=_blank}. This is the most accurate representation of Omeka's *Dublin Core* element set. It is currently available on the following pages:

-   items/browse
-   items/show

## json

The *json* response format is a streamlined JSON output primarily used for [Ajax](http://en.wikipedia.org/wiki/Ajax_(programming)){target=_blank} requests. There is discussion to deprecate this format once the omeka-json format matures. It is currently available on the following pages:

-   items/show

## atom

The *atom* response format is a commonly used Web content syndication format, [Atom](http://tools.ietf.org/html/rfc4287){target=_blank}. It is currently available on the following pages:

-   items/browse
-   items/show

## rss2

The *rss2* response format is a commonly used Web content syndication format, [RSS 2.0](http://cyber.law.harvard.edu/rss/rss.html){target=_blank}. It is currently available on the following pages:

-   items/browse
