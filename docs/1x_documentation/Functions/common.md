---
title: Omeka Classic 1x Functions common
---
*This documentation for Omeka versions up to 1.5 only*

The `common` function loads a script, optionally passing in some variables. Themes and plugins can use this function to separate distinct blocks of output into different scripts, even if all the output will appear on one page.

By default, `common` tries to load the script from the "common"
directory for the current theme, but any view directory can be
specified.

Usage
---------------------------------------------------

``` {.de1}
common($file, $vars = array(), $dir = 'common')
```

Arguments
-----------------------------------------------------------

 *string* `$file` {{\#if
:   | (optional)}}
:   The name of the script to be included.
:   {{\#if: | Default: `{{{default}}}`}}

 *array* `$vars` {{\#if
:   array() | (optional)}}
:   A key-value array of variables that will be available to the
    loaded script.
:   {{\#if: array() | Default: `array()`}}

 *string* `$dir` {{\#if
:   'common' | (optional)}}
:   The theme directory to search for the script in.
:   {{\#if: 'common' | Default: `'common'`}}

Return Values
------------------------------------------------------

This function does not return a value.

Example(s) / Usage
---------------------------------------------------------------


``` {.de1}
 
```


Source File / Version
---------------------------------------------------------------

-   application/helpers/Functions.php since Omeka 1.0.
