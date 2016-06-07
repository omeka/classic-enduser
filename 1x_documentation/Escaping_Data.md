---
title: Escaping Data
---

*This documentation is for Omeka Classic versions 1.0-1.5*

*Note to theme designers*: Omeka themes should be secure out of the box, so theme designers who do not plan on modifying or adding PHP code to the existing themes will not need to worry about this. However, this document details best practices for web development in general, so theme writers who are also web developers may find it useful.

The Gist 
---------------------------------------------------------

Data that comes from the user is untrustworthy. "User data" includes both data retrieved from the database as well as input from any given user request (e.g. from the URL, form submissions, etc.). The way to avoid problems from untrustworthy data is twofold: validating data prior to storing in the database, and escaping data properly before display. Omeka takes care of validating data that will go into the database (though not automatically for plugins -- that is responsibility of plugin writers), but ensuring the security of displayed data is, unfortunately, the responsibility of the theme writer. Failing to do this won't always leave your Omeka site open to attack, but under certain circumstances it will. The only way to prevent problems for certain is to make sure that data is escaped properly before display.

What could possibly go wrong?
-----------------------------------------------------------------

Just for example, suppose you have a theme that displays the search query for which results are being displayed, and the code currently looks like this:


``` {.de1}
Search Results for: <?php echo $_GET['search']; ?>
```

How XSS Attacks Work
-------------------------------------------------------------

If someone did a search for: `<script src=“my-evil-site.com/bad.js”></script>`, that search query is stored in `$_GET[‘search’]`, so that bad HTML would be injected directly into the search results page, and the evil javascript would run. Then the attacker could send some 3rd party a link to those search results, and when that third person followed the link, they would be compromised by the bad javascript.

How to Prevent These Attacks 
--------------------------------

Omeka has a set of helper functions that need to be used in situations such as this. The most important of these is `html_escape()`, which basically translates a PHP value into valid HTML by encoding HTML`entities so that `<` becomes &lt;, `>` becomes &gt;, etc. PHP developers will recognize the similarity to PHP's builtin htmlentities() function, which is basically what this is, with the added ability for plugins to filter the output if necessary.

The previous example could be corrected by wrapping the \$\_GET parameter in html\_escape(), like so:

``` {.de1}
Search Results for: <?php echo html_escape($_GET['search'); ?>
```

Why Doesn't Omeka Do This Automatically? 
-----------------------------------------------------------------

There are a few complicated reasons why the current version of Omeka can't escape all data automatically for theme writers, most of which has to do with the fact that there seems to be no one-size-fits-all solution for this type of problem. That said, we're looking into possible solutions for future releases that would make this easier. Users are welcome to contribute suggestions on the dev mailing list.

Caveats 
-------------------------------------------------------

Not everything in a theme needs to be (nor should be) escaped using `html_escape()`. Important counterexamples include helper functions that`generate HTML, e.g. `auto_discovery_link_tag()`, link\_to(), etc. Also, the output of certain functions like item() should not be escaped, as that is taken care of automatically based on whether or not the field was marked as HTML in the admin.

In addition, this may seem obvious, but pretty much any data over which the theme designer has control does not need to be escaped. For example, escaping literal strings, such as the following, is pointless:



``` {.de1}
<?php echo html_escape('cookies & cream'); ?>
```


Instead, it should just be:

``` {.de1}
cookies &amp; cream
```


Useful Examples of When to Escape Data
---------------------------------------------------------------------------

### User Input

Superglobals like `$_REQUEST, $_GET, $_POST, and $_SERVER` shouldalways be escaped before display.

-   Bad:

``` {.de1}
Search terms: <?php echo $_GET['search']; ?>
```

-   Good:


``` {.de1}
Search terms: <?php echo html_escape($_GET['search']); ?>
```

### From Database

-   Bad:

``` {.de1}
Welcome, <?php echo current_user()->first_name; ?>
```
-   Good:
``` {.de1}
Welcome, <?php echo html_escape(current_user()->first_name); ?>
```

### URLs

In HTML, "href" and "src" attributes must always contain a URL that is properly escaped.

-   Bad:
``` {.de1}
<a href="<?php echo uri('items/browse'); ?>">Go to Items</a>
```
-   Good:
``` {.de1}
<a href="<?php echo html_escape(uri('items/browse')); ?>">Go to Items</a>
```

-   Better:

``` {.de1}
<?php echo link_to('items', 'browse', 'Go to Items'); ?>
```

Also, URL query string parameters must be properly encoded with
urlencode() before they are escaped.

-   Bad:
``` {.de1}
<a href="<?php echo uri('items/browse?tags=' . $tag); ?>">
```
-   Good:
``` {.de1}
<a href="<?php echo html_escape(uri('items/browse?tags=' . urlencode($tag))); ?>">
```
-   Better:
``` {.de1}
<a href="<?php echo html_escape(uri('items/browse', array('tags'=>$tag))); ?>">
```

### Javascript and XML

For developers writing javascript and XML, Omeka has 2 functions (since Omeka 1.1) for escaping data: `js_escape()` and `xml_escape()`. These are necessary because the behavior of `html_escape()` is not necessarily desirable (or valid) for translating from PHP to Javascript or XML. Basically, any context for using `html_escape()` in a theme applies also to `js_escape()` or `xml_escape()`.

-   Bad Example in Javascript:
``` {.de1}
new Ajax.Request("<?php echo uri("items/change-type") ?>");
```
-   How it should be done:
``` {.de1}
new Ajax.Request(<?php echo js_escape(uri("items/change-type")) ?>);
```