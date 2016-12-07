---
title: Internationalization
---

*This documentation is for Omeka Classic versions 1.0-1.5*
 
*Note: this is the developer documentation for internationalization. This page is written to help theme and plugin authors make their code work with different locales.*

Starting with version 1.5, Omeka allows users to pick the locale they want Omeka to use. The core software fully supports this new feature, but plugins and themes may need to be *internationalized* to make display in different languages and locales possible.

Making text translatable 
----------------------------------------------------------------

For most plugins and themes, making text translatable will be the lion's share of the internationalization work. All user-facing text needs to be translated. This includes the obvious suspects like text in paragraphs and other visible HTML elements, but also less-obvious places like `title` attributes.

Translating text is done with the `__()` or double-underscore function. All strings you want to be translated need to be passed through this function.

### Bare text

You might have previously written much of the user-facing text in your plugin or theme directly in HTML or plain text without PHP. To allow this text to be translated, it needs to be in a PHP block.

**Untranslatable**
``` {.de1}
<p>Some text.</p>
```


**Translatable**
``` {.de1}
<p><?php echo __('Some text.'); ?></p>
```

### PHP strings
PHP strings that will end up being shown to the user need to get translated too. Since these strings are already in PHP code, it's easy: just wrap the `__()` function around the string that's already there.

**Untranslatable**
``` {.de1}
<?php
head(array(
    'title' => 'Page Title'
));
?>
```

**Translatable**
``` {.de1}
<?php
head(array(
    'title' => __('Page Title')
));
?>
```

### Strings with variables 

A common pattern in PHP is to write strings that directly contain variables. These need a slightly different approach to be translatable. You want to make it so that translators only have to translate your string once, no matter what the values of the variables inside are. To do this, you replace your variables with *placeholders*, and pass your variables separately into `__()`. The basic placeholder is `%s`:

**Untranslatable**
``` {.de1}
<?php
echo "The site contains $numItems items.";
?>
```


**Translatable**
``` {.de1}
<?php
echo __('The site contains %s items.', $numItems);
?>
```

This way, translators work with the single string
`'The site contains %s items.'`, instead of different strings for every
possible number. The `__()` function handles replacing the `%s` with the
actual value.

####  Multiple variables 

The `%s` placeholder is fine for when a string only contains one variable. However, once there are two or more, you need to account for the possibility that some translators will need to reorder the variables. So, with multiple variables, you need to use *numbered placeholders*: `%1$s, %2$s, %3$s` and so on.

**Untranslatable**
``` {.de1}
<?php
echo "Added $file to $item.";
?>
```

**Translatable**
``` {.de1}
<?php
echo __('Added %s$1 to %s$2.', $file, $item);
?>
```

Dates and times 
---------------------------------------------------------------
The other major thing you will often want to display differently for different locales are dates and times. Unlike translations, Omeka (courtesy of Zend Framework) comes with the date formats for different locales already.

Where translations all ran through one function, `__()`, dates and times similarly work with one function: `format_date()`. `format_date` automatically changes the output format based on the site's currently selected locale.

`format_date()` takes two parameters. The first is the time you want to display. The second, which is optional, is the format you want to use. If you don't pick a format, the default is appropriate for displaying a date.

###  Time

There are two possible types for the time given to `format_date`: integer and string. If you pass an integer, the time is interpreted as a Unix timestamp. If you pass a string, the time is interpreted according to the ISO 8601 standard (this will, among many other formats, correctly parse the output from MySQL date and time columns).

### Format

`format_date()` uses Zend\_Date internally, so the Zend documentation is the place to go for an [exhaustive list of available formats](http://framework.zend.com/manual/en/zend.date.constants.html#zend.date.constants.list).

Format constants starting with `DATE` are used for displaying dates without a specific time, ones starting with `DATETIME` are used for date/time combinations, and ones starting with `TIME` are for times alone. For each, there are `FULL`, `LONG`, `MEDIUM`, and `SHORT` variants. Each variant will automatically use a format specific to the current locale, including things like the proper ordering for dates and the correct names of months.

The default format is `Zend_Date::DATE_MEDIUM`. This will display, as you might think, the given time value as a date, with medium length. In the standard US English locale, this looks like "May 24, 2012." In, for example, a Brazilian locale, the same date is displayed as "24/05/2012."

