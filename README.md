# Omeka Classic User Manual

[Omeka Classic](https://omeka.org/classic/) is a web publishing platform for sharing digital collections and creating media-rich online exhibits.

Omeka Classic is part of the [Omeka family of web publishing platforms](https://omeka.org/).

This repository is the content of the [Omeka Classic User Manual](https://omeka.org/classic/docs/) and is best viewed on the offical site.

## Contributing to the User Manual

If you notice something that could be improved, we would love your help. 

You can click the "Edit on GitHub" link at the top right corner of any page in the manual. That link will bring you here, where you can edit the page directly and submit your suggested changes as a pull request. This can be useful for typos, dead links, or minor formatting issues. You may need to know some Markdown to make these edits. 

If you do not wish to suggest an edit directly, please [create a new issue](https://github.com/omeka/classic-enduser/issues) here in this repository. If you do not wish to have a GitHub account, you can make suggestions and requests in the [Omeka Forum](https://forum.omeka.org/).

Multi-page edits, larger additions, image modifications or submissions, and significant changes should be created in a branch and submitted as a pull request. Please take the following into consideration when writing documentation:

- This is documentation for ordinary users, not developers. Please use clear, jargon-free language. 
- Explain every possible step, even the ones which seem obvious. It is better for users to skip a step they've already completed than be confused by a leap they can't follow. Do not assume any prior knowledge of technology on the part of the user for this documentation.
- Break longer tasks up into short paragraphs or lists.
- Use illustrative images when needed, especially to indicate which button or link users should engage with.

If you are cloning the user manuals to your local computer and creating a branch, you may wish to [install and use MkDocs](https://www.mkdocs.org/#installation) to preview your changes and ensure the formatting and syntax are correct.

### Formatting 

**Section headings** should start with H2 (`##`) and go down to H4. Create sections where it is logical in the documentation structure; they will appear in the left navigation of the documentation. (See [Searching](https://omeka.org/classic/docs/GettingStarted/Searching/#basic-search) for an example of extensive section use.) Use "Sentence case for section headings", not "Camel Case".
  
**Links** should be composed as relative to the current file. They will look something like `../Plugins/CSV_Import.md` if you are linking to a page that sits within a folder, or `../Admin/Users.md#add-a-user` if you are linking to a section of a page. Do not forget the `.md` part of the page.
 
Links to external websites require the full URL as well as the addition of "{target=_blank}" after the link syntax: for example, `[create a new issue](https://github.com/omeka/classic-enduser/issues){target=_blank}`.

**Images** for a page go into the `doc_files` directory, with images for plugins in the `doc_files/plugin_images` directory. Name images clearly, starting with an indicator of the relevant page, and use an underscore to separate out the image's purpose (for example, `items_addItem.png`).

Images should never give information that is not provided in the text (or in the image alt text and title). No one with vision problems should be missing out. Think of images as a shortcut, not the only route, to understanding how to do something. 

All images should have alt text. A title can also be supplied if having some pop-up text would be useful to readers. An image entered in Markdown looks like this:

```
Some text ends here.

![Alt text for the image goes here.](../doc_files/animage_pathGoesHere.png "An optional title which will appear when a user mouses over the image.")

More text picks up here.
```

The maximum display width of an image in the user manuals currently is around 1300px (actually 1296px). A screenshot of the full Omeka Classic interface (public or admin side) should be large. Images can be saved larger (up to 2000px wide) so that readers can open them in new tabs and inspect them in full-scale detail if desired. 

A screenshot of a portion of the interface, such as the left-hand navigation, should appear at full scale for maximum readability. Currently, Omeka Classic has a left-side menu-bar width of about 200px, and a main content width of about 1040px, on a 1920x1080 screen. Expand the browser window wide enough to add some whitespace and keep things from looking cramped, but screenshots do not need to be the full width of your monitor.

**Format your text** as follows: 

Buttons appear in quotes, as in the "Save" button. 

You can highlight interface features (such as page titles, page tabs, links, dropdown menus, and checkboxes) in **bold**. 

URLs, file paths, bits of code, and metadata fields are highlighted using `code formatting`. 

Use the [language found in the Glossary](https://omeka.org/s/docs/user-manual/glossary/) to refer to elements in the Omeka Classic interface.

Omeka Classic terms:
- Left-hand navigation: the bar on the left of the admin dashboard with Items, Collections, Item Types, Tags, and plugins
- Top menu: the bar with Plugins, Appearance, Users, and Settings
- Main work area: center of window, to the right of the left-hand navigation
- Admin dashboard
- Plugins
- Elements
- Collections
- Item types.

### After you submit your changes

A member of the Omeka team will review your suggested edits. If your pull request is approved and merged, you will see your edits on the GitHub version of the documentation immediately. The user manuals are refreshed nightly so you may not see your changes in the user manuals until the next day.

## Rights

This documentation is [CC-BY-NC](https://creativecommons.org/licenses/by-nc/4.0/).

