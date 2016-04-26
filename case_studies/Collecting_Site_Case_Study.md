Collecting Site Case Study
==========================

Hurricane Digital Memory Bank | Collecting Site 
-----------------------------------------------------------------------------------------------------------------------------------------

### Introduction

A collecting site can be built very quickly, because you are asking for others to contribute the content. The hardest part is tailoring the questions on the form to suit the needs of your project.

Look at the [Hurricane Digital Memory Bank](http://hurricanearchive.org/) while reading through the site breakdown.

### Site Breakdown 

-   Theme: HDMB-specific theme. One of the packaged seasonal themes might work well.
-   Plugins: Contribution, Geolocation, Simple Pages, Dropbox (for uploading large files in the admin side)
-   Major Sections and pages
    -   Homepage:
        -   Featured items: You can feature any item from the admin/items screen.
        -   "Add Your Photos" and "Add Your Story" buttons linked to the
            /contribution page and are hard coded into the
            index.php page. We did this to make adding very easy and
            obvious for someone coming to the site.
    -   Add to the Memory Bank: links to the /contribution page which
        brings up the form.
        -   You may modify the standard form packaged in Contribution
            plugin (See: [Contribution plugin
            instructions](http://omeka.org/codex/Plugins/Contribution))
            -   In HDMB, individuals may map their contributions. This
                is difficult to do out of the box, but for your site,
                you can create a field in the form that says "location"
                and then you could map those locations from the
                admin side. (See: [Geolocation plugin
                instructions](http://omeka.org/codex/Plugins/Geolocation).)
        -   Contributions will be added to the archive as
            un-public items. It is up to you to review the items and
            make them public for viewing on the public site.
            **Remember**: if you are logged into the admin side and then
            you check the public side, you will be able to see
            everything in the archive, public and not public. So, to
            check for an accurate public view, be sure to log out from
            the admin.
    -   Browse: This section is the /items/browse section created
        automatically for you in Omeka. If you would like to browse by
        item type, you can add in links that will browse different item
        types, such as:
         -   Collections: This section is simply the /collections/browse
        section automatically generated in your installation.
   		 -  About: This can be made with the Simple Pages plugin.
   		 -   FAQs: This can be made with the Simple Pages plugin
   		 -   News—if you want a blog, you can install a WordPress blog in a
        directory w/in the Omeka installation and had to make it work
        within the Omeka theme. This is a bit more advanced!

