# Foundation

## Theme settings

General
Stylesheet
Header and Footer
Navigation Layout

Select a style for the global navigation.
Show Top Navigation Child Pages

Check to show child pages in the top navigation bar. Uncheck to show top-level items only.
Logo File

Choose a logo file. It is recommended to use an image no bigger than 150px in height.
Logo File For Mobile Devices

This logo file appears on mobile devices. It is recommended to use an image that is legible at small sizes.
Banner File

A large image at the top of the page.
Banner Width

The maximum banner width.
Banner Height For Desktop

The maximum height the banner should use. Use valid CSS length units (px, em, rem, etc.)
Banner Height For Mobile

The maximum height the banner should use for mobile widths. Use valid CSS length units (px, em, rem, etc.)
Banner Position

SWhere to affix banner image when scaling down using a fixed height.
Footer Text

Add some text to be displayed in your theme's footer.
Display Copyright in Footer

Check this box if you wish to display your site's copyright information in the footer.
Use Advanced Site-wide Search

Check this box if you wish to allow users to search your whole site by record (i.e. item, collection, file) and choose their boolean method.
Homepage
Homepage Text

Add some text to be displayed on your homepage.
Homepage Intro Background

Choose an image file for your intro background on the homepage.
Main Featured Selection

Display a random featured record of this type for the largest featured area on the home page.
Second Featured Selection

Display a random featured record of this type for the second featured area on the home page.
Main Featured Selection

Display a random featured record of this type for the third featured area on the home page.
Browsing
Browse Layout

Select a layout for browsing items, collections, or exhibits. List will provide a single column layout. Grid will proved a multi-column and row layout. Toggle lets the user decide.
Hide Thumbnails While Browsing

Toggle thumbnails off when browsing item, collections, or exhibits.
Truncate Body Property

How to handle long values for the body property of each resource on the browse page.
Default Thumbnail Size

The default thumbnail size to use when browsing items, collections, and exhibits.
Metadata View
Display Metadata Values Inline

Check this box if you wish to show metadata values inline with their properties.
Single Item Layout

Select a layout for viewing a single item. Two columns displays media attachments next to the item metadata.
Media Display

Select a style for displaying media on an item's show page. Note: This overrides the square thumbnail appearance setting.
Media Position

Placement of attached media on the metadata view. Note: This setting does not apply if the two column layout is selected.




## Admin info

his is an Omeka Classic theme based on ZURB Foundation Sites. It currently comes with a default stylesheet for prototyping as well as 3 other style options.

Foundation Classic is Copyright © 2018-present Corporation for Digital Scholarship, Vienna, Virginia, USA http://digitalscholar.org

The Corporation for Digital Scholarship distributes the Omeka source code under the GNU General Public License, version 3 (GPLv3). See the LICENSE file for the full text.

The Omeka name is a registered trademark of the Corporation for Digital Scholarship.

Third-party copyright in this distribution is noted where applicable.

All rights not expressly granted are reserved.
Installation

For basic out-of-the-box use of the theme, follow the Omeka Classic User Manual instructions for installing themes.

For more advanced use, such as customizing the theme with Sass, you'll need to install the tools with NodeJS (0.12 or greater). Navigate to your theme directory and run npm install.
Theme Configuration

    Stylesheet: The theme provides 4 style options.
    Default uses ZURB Foundation's default styles for prototyping, which are all viewable in their documentation under the Kitchen Sink.
    Revolution aims to capture the feel of old documents and juxtaposes it with a bright red accent. It includes a textured paper background image.
    Sea Foam offers a clean, friendly look with a teal palette.
    Inkwell features a high contrast serif family for its typography, as well as sunny yellow accents.
    Navigation layouts: Global navigation can display as a horizontal top bar with optional dropdown menus or a left vertical column.
    Show Top Navigation Child Pages: Toggle display of child pages within the main navigation.
    Logo: Upload an image asset to use as a logo in place of a text site title.
    Footer Content: Control what appears in the footer. This field takes HTML markup.
    Layout for Browse Pages: Select how to display items within their "browse" views.
    Grid: Items are organized into rows and columns. This is recommended for items that prominently feature images.
    List: Items are stacked into a single column.
    Toggle (default: grid): Site visitors can choose to display the browse views as grids or lists, and grids are the default.
    Toggle (default: list): Site visitors can choose to display the browse views as grids or lists, and lists are the default.
    Layout for Show Pages: Resource metadata can show display as stacked with properties as headings above their values, or inline with properties as headings inline with their values.

Customizing the Theme

For those dipping their toes into customizing sites with CSS, the CSS Editor module allows site administrators to write style overrides.

For advanced CSS and Sass users, Foundation S uses ZURB Foundation Site's toolkit that includes variables and mixins for managing and extending many styles.
Sass Tasks

Run these commands within the theme's root directory.

    npm start: While this task runs, it watches for changes to sass files and recompiles the CSS.
    gulp sass: This is the one-off task for compiling the current Sass/CSS.

Sass File Structure

Foundation S comes with the Default theme, as well as 3 other customized stylesheets that were built on top of Default. The "Sea Foam" theme has the fewest overrides and is thus the easiest reference for a custom theme model.

/asset/sass/seafoam.scss

@charset 'utf-8';

@import 'globals-default';
@import 'globals-seafoam';
@import 'settings';

// Sea Foam Settings

$topbar-background: $primary-color;

$thumbnail-border: 4px solid $secondary-color;
$thumbnail-shadow: none;
$thumbnail-shadow-hover: 0 0 6px 1px rgba($primary-color, 0.5);

$button-background: $secondary-color;
$button-color: $primary-color;

@import 'foundation-core';
@import 'omeka';

header a {
  color: $white;
}

Much of the customizability within the theme lies in managing its settings variables. ZURB Foundation's default global variables from their original _settings.scss all sit in _globals-default.scss. Many of these variables are used throughout the rest of _settings.scss, so it was necessary to separate them out into their own file if the theme writer wants to set their own global variables. Here all the overrides live in _globals-seafoam.scss, and so all overridden values will be appropriately updated for use throughout the rest of _settings.scss.

Any non-global setting variable overrides should come after the import for _settings.scss and before their usagee in the rule files, _foundation-core.scss, and _omeka.scss.

ZURB Foundation's default style rules are all managed in _foundation-core.scss. All style rules specific to Omeka S are contained within _omeka.scss.

After all those imports come all style rules specific to the theme.
