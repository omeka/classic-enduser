# Navigation

The Navigation tab in the Appearance section lets you manage your Omeka site's menu by ordering, editing, and adding navigation links, and by selecting a homepage.

Access Navigation settings by clicking "Appearance" in the top navigation menu in the admin dashboard and then going to the "Navigation" tab in that section.

![Main navigation](../../doc_files/navigationMain.png) 

Omeka includes links to Browse Items and Browse Collections by default. Plugins can also add pages to your navigation automatically when installed and activated. If you have installed [Simple Pages](../../Plugins/SimplePages.md), the About page will appear by default, and Simple Pages you publish will be automatically added to the navigation. Likewise, once you have installed Exhibit Builder, Browse Exhibits will automatically appear in the navigation. Check your navigation when installing new plugins and be sure to uncheck or remove undesired additions until they are ready to be published.

You may arrange navigation items in any order by dragging and dropping, and organize them into hierarchical trees. Depending on your site theme (and exhibit themes), hierarchical menu items may not display to your liking. Always check the public site for function and appearance when changing your navigation settings. 

Manage navigation links
----------------------------------------------------

The checkbox located to the left of each section or page title indicates when a navigation link is visible on the public site. This is useful for default pages, plugin-added pages, and temporarily turning custom links on and off. For example, if you don’t want "Browse Collections" to display, uncheck the box.

![Cursor hovering over a checkbox for a navigation option](../../doc_files/Navchoice.png)

To rename the link text that appears on the public site, click the arrow to the right of the page or section's title to reveal the Label and URL.

Edit the word or phrase that appears in the Label text box. For instance, you may change "Browse Items" to "See All Documents".

![Browse items renamed sources](../../doc_files/navSources.png)

To add menu navigation for a specific collection, exhibit, or item, see the section on links, below.

Add navigation links
----------------------------------------------------------------
In the section, "Add a Link to the Navigation," you may add links to other content, whether on your site or elsewhere.

Enter a Label (the display text for the link), and paste in the URL to the external or internal webpage.

Click "Add Link", ensure the checkbox is checked, and save the Navigation screen. We recommend you refresh the public page and test to ensure the link works as expected.

You can use relative links if the page is on your Omeka site. For example, if you had an exhibit you wished to include in the navigation, you could enter `/mysite/exhibits/show/my-exhibit-title` in the URL field. 

![Adding link](../../doc_files/navAddLink.png)

When adding items to the navigation, we recommend you review the public display frequently. Some themes can only have so many top-level items before the navigation becomes too wide (or long) for an average user's browser display. Use the hierarchy ability to form your navigation links into trees, then review to be sure that the organizational system makes sense and all links are accessible given your theme. 

Be aware that if you are using different themes for your site and your exhibits, you may need to check each to ensure your navigation looks good and works in each theme display. 

Choose a homepage
--------------------------------------------------------------
You may change the homepage of your installation by selecting a page from the dropdown menu located under the heading "Select a Homepage" found on the right side of the screen. The dropdown lists all of the public navigation links you created. "[Default]" will display the Homepage as set up in the Theme's settings (so, if you change themes, you will need to re-enter Homepage information if you are utilizing this feature).

Select the desired page from the list and click "Save Changes" to designate a new homepage.

![Choose homepage dropdown with multiple options](../../doc_files/navHomepage.png)

Reset the navigation
--------------------
To reset the navigation back to the Omeka default, click the "Reset Navigation" button below the "Save Changes" button and Homepage dropdown. **All customizations will be lost**: custom links will be deleted, and navigation item order and custom labels will revert to Omeka defaults.

![arrow points to reset button](../../doc_files/navReset.png)
