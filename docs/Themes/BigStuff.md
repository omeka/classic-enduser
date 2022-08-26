# Big Stuff

## Theme settings

Page Design
Background Color

The background colour, where there is no background image. Any CSS color can be used
Background Image

Choose an image file to use as a background for the area outside the content. If absent, the background will be a solid colour
Tile Background Image

The background image is a tile that will repeat hoizontally and vertically. If unchecked, the background image will show horizontally centred.
Single Line Item

Check this box if you wish items to appear as a list-like single line caption with more information available on mouse-over.
User-Sortable Shortcodes

Check this box if you wish item and collection lists in a shortcode to have user-selectable sort options, similar to the browse pages.
Logo File

Choose a logo file. This will replace the site title in the header of the theme. Recommended maximum width for the logo is 500px.
Site Title Size

The text size of a site title if a logo file is not used. Any CSS size can be used
Site Title Color

The color of a site title if a logo file is not used. Any CSS color can be used
Header Image

Choose an image file to display below your header. Recommended max height is 100px.
Footer Text

Add some text to be displayed in your theme's footer.
Display Copyright in Footer

Check this box if you wish to display your site's copyright information in the footer.
Use Advanced Site-wide Search

Check this box if you wish to allow users to search your whole site by record (i.e. item, collection, file) and choose their boolean method.
Homepage
Display Featured Item

Check this box if you wish to show the featured item on the homepage.
Display Featured Collection

Check this box if you wish to show the featured collection on the homepage.
Display Featured Exhibit

Check this box if you wish to show the featured exhibit on the homepage.
Homepage Recent Items

Choose a number of recent items to be displayed on the homepage.
Homepage Text

Add some text to be displayed on your homepage.
Citation Styles
Article Item Type

The name of the item type that means that the item is an article published in a journal.
Conference Paper Item Type

The name of the item type that means that the item is a paper given at a conference.
Book Item Type

The name of the item type that means that the item is a book.
Manual Item Type

The name of the item type that means that the item is a manual, technical documentation or similar.
Thesis Item Type

The name of the item type that means that the item is a PhD or Masters thesis.
Report Item Type

The name of the item type that means that the item is a report.
Text Item Type

The name of the item type that means that the item is non-specific text.
Website Item Type

The name of the item type that means that the item is a reference to an entire website.
Hyperlink Item Type

The name of the item type that means that the item is a reference to a single web resource.
Still Image Item Type

The name of the item type that means that the item is a still image.
Moving Image Item Type

The name of the item type that means that the item is a moving image.



## Admin info

# BigStuff Omeka Theme

The BigStuff [Omeka](http://omeka.org/) theme is a theme designed for the home of the Big Stuff large technology
object conferences.

This theme is based on the [Berlin](https://github.com/omeka/theme-berlin) Omeka theme and
uses the highly configurable index page features from Berlin.

## Features

* Features from Berlin
    * Configurable logo image
    * Configurable header image
    * Configurable footer text and copyright
    * Configurable home page text
    * Configurable info boxes, such as a featured item or collection, for the home page.
* Features from BigStuff
    * Customisable background filler image
    * A *hero-shot* image on the home page, selected randomly from items with images in the featured collections.
    * Single-line item lists, which expand on mouse-over, as a configurable option.
    * Citation-style item information. BigStuff is designed to contain collections of conference papers, as well as
    other collections. If given a suitable item type, the item will be provided with a citation.
    * The ability for the user to sort lists of items and collections displayed by shortcodes.

## Installation and Configuration

Copy the root of this source directory to `$OMEKA/themes/bigstuff` where `$OMEKA` is the root of the Omeka installation
(eg. `/srv/www/htdocs/omeka`).
It should them appear as an avilable theme in the Omeka administration pages.

Once installed, go to the *Appearance* menu in Omeka administration.
You can then configure the theme.

### Citations

The BigStuff theme generates bibliographic citations for items with appropriate item types and information.
These are designed to allow things like papers and publications to be added and browsed.
A short citation, generally either author-title or just the title, depending on the item type, is used as a headline.
A full citation is generated as part of the item summary.

#### Addtional Item Types and Elements



To get full citation information, a number of additional item types and elements need to be added to your site.
These don't need to be added, or can be partially added; the citation generator will omit any information
that it can't find.
The new item types and elements are listed below, with the standard Dublin Core elements ignored.
Elements in **bold** are completely new elements or item types.
Items in *italics* are existing elements that need to be added to item types.

| Type | Description | Elements |
| ---- | ----------- | -------- |
| **Article** | An article in a journal or periodical | **Journal**, *Location*, **Pages**, **Volume**, **Number**, **DOI** |
| **Paper** | A paper presented as part of a conference, workshop, etc. | **Editor**, **Book**, *Location*, **Pages**, **DOI** |
| **Book** | A book, including published collections such as conference proceedings. | **Editor**, *Location*, **Volume**, **Pages**, **ISBN** |
| **Manual** | A technical or procedural manual or set of instructions | **Institution**, **Number**, **DOI** |
| **Thesis** | A PhD or masters thesis | **Location**, **Institution**, **Number**, **DOI** |
| **Report** | A report produced for a specific purpose |  **Institution**, **Number**, **DOI** |
| Text | The standard Omeka text item | **DOI** |
| Website | The standard Omeka website type | |
| Hyperlink | The standard Omeka hyperlink type |
| Moving Image | The standard Omeka moving image type | |
| Still Image | The standard Omeka still image type | |

The additional elements are

| Element | Description |
| ------- | ----------- |
| Journal | The name of the journal |
| Location | Already included in Omeka but used for a publisher's address or conference location |
| Pages | The page or pages where an article, paper or part of a book can be found |
| Volume | The journal or book volume |
| Number | The number of the journal with a volume for a journal. For manuals, reports, etc., the reference number assigned to the document by the creating institution |
| DOI | The [Digital Object Identifier](https://www.doi.org/) for documents with a persistent DOI |
| Editor | The editor of a collection or book |
| Book | The title of the book in which a paper or section has been published |
| ISBN | The [International Standard Book Number](https://www.isbn-international.org/) of a book |


#### Citation Types

Citations are presented differently depending on the *Item Type* of the item, or the Dublin Core *Type* of the collection.
Citations use the following Dublin Core terms:

| Type | Author | Year | Editor | Title | Journal/Proceedings | Publisher | Location | Pages | Volume | Number | Date | Institution | Document Number | URL | DOI/ISBN |
| ---- | ------ | ---- | ------ | ----- | ------------------- | --------- | -------- | ----- | ------ | ------ | ---- | ----------- | --------------- | --- | -------- |
| Article(2) | Creator | Date(1) | | Title | Journal(3) or Collection Title | Publisher or Collection Publisher | Location | Pages(3) | Volume(3) | Number(3) | | | | | DOI(3) |
| Paper(2) | Creator | Date(1) | Editor(3) or Collection Creator | Title | Book or Collection Title | Publisher or Collection Publisher | Location | Pages(3) | | | Date | | | | DOI(3) |
| Book(2) | Creator | Date(1) | Editor(3) | Title | | Publisher | Location | | Volume(3) | | Pages(3) | | | | ISBN(3) |
| Manual(2) | Creator | Date(1) | | Title | | | | | | | | Institution(3) | Number(3) | | DOI(3) |
| Thesis(2) | Creator | Date(1) | | Title | | | Location(3) | | | | | Institution | Number(3) | | DOI(3) |
| Report(2) | Creator | Date(1) | | Title | | | | | | | | Institution(3) | Number(3) | | DOI(3) |
| Text | Creator | | | Title | | Publisher | | | | | Date | | | | DOI(3) |
| Website | | | | Title | | | | | | | Date | | | Local URL or Source | |
| Hyperlink | | | | Title | | | | | | | Date | | | URL | |
| Moving Image | Creator, Director, Producer | Date(1) | | Title |  | Publisher | | | | | | | | | |
| Still Image | Creator | Date(1) | | Title |  | Publisher | | | | | | | | | |
| default | Creator | | | Title | | Publisher | Location | Pages | | | Date | Institution(3) | Number(3) | URL | DOI(3) |


*(1)* Dates are parsed using the PHP `parse_date` function to see if a year can be recognised. In general, use
*mm/dd/yyyy* for US-style dates, *dd-mm-yyyy* or *dd.mm.yyyy* for European-style dates and *yyyy-mm-dd* for ISO-style dates.
Two digit years will be interpreted as *yy-mm-dd* - you have been warned. If a date cannot be parsed, the entire date is used.

*(2)* These item types are not part of the standard set of supplied item types.


*(3)* These would be really useful but don't have a corresponding Dublin Core term. Boo. Hiss. 
Instead, they can be added to the item type metadata associated with the new item types.


#### Inheritance

Journal articles and conference papers can draw some information from the collection that they are in.
In this case the collection is treated as the journal or conference proceedings, with the title of the collection
the title of the journal or conference and the creator of the collection the editor.
For example, an article will get the journal title from the collection title if the Source is not present.

To override this behaviour, put `na` in the item's term (eg. Putting `na` in the Source for an article
means that no journal will be listed).

### Background Images

You can use any repeatable image as a background image.
Three backgrounds are available as part of the theme, all reflecting the technical background to the theme:

* Gears
* Bluebrint
* Old Blueprint

### Sortable Shortcodes

The `[items ...]` and `[collections ...]` shortcodes have been extended to allow
user-selected sort options, similar to the browse pages.

The old behaviour can be selected via a configuration checkbox.
Alternately, the `sortable=1` or `sortable=0` options can be added to a shortcode
to override the default behaviour.

The sort options are dc:title, dc:creator, dc:date and added.
The initial sort option can either be defined in the shortcode or defaults to added.

The sort option applies to the whole page.

## Geeks Corner

### Licence

Licenced under the [GPLv3](http://www.gnu.org/licenses/gpl-3.0.en.html).

### Building the Theme

If you feel like modyfiying the theme, the CSS is generated by [Compass](http://compass-style.org/)/[SCSS](http://sass-lang.com/).
You will need to install Compass before generating CSS; follow the instructions on the
Compass page and then find out where gem has put the compass command.

Note, you may need to do a sequence of installs:

```$xslt
gem install --no-rdoc --no-ri sass
gem install --no-rdoc --no-ri compass
```

To modify the the CSS modify the SCSS files found in `css/scss` and then run compass.
On the command line, change to the source directory and run compass with the following command:
`$COMPASS/bin/compass compile css` where `$COMPASS` is where-ever gem has decided to put Compass
(eg. `/usr/lib64/ruby/gems/2.1.0/gems/compass-1.0.3`).

### Citation Styles

Citation styles follow the Australian Government Style Manual (6th ed.) as far
as is possible.
If you want to change the way citations are presented, edit `functions.php`.