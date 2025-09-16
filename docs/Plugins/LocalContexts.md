# Local Contexts

With the [Local Contexts plugin](https://omeka.org/classic/plugins/LocalContexts/){target=_blank} users can apply [Local Contexts](https://localcontexts.org/){target=_blank} Labels and Notices to Omeka Classic sites and resources. This requires setting up a Local Contexts Hub account and creating Projects in the registry. Then enter the API key into Omeka to bring the chosen [Labels](https://localcontexts.org/labels/about-the-labels/){target=_blank} and [Notices](https://localcontexts.org/notices/about-the-notices/){target=_blank} over and apply them to items and exhibits. 

![Image](../doc_files/plugin_images/LocalContexts_metadataPublic.png)

## What is Local Contexts?

Local Contexts is a global initiative that supports Indigenous communities with tools that can reassert cultural authority in heritage collections and data. Local Contexts has three components of note to Omeka users: Notices, Labels, and Projects.

### Notices

This text is from the [Local Contexts website](https://localcontexts.org/notices/about-the-notices/){target=_blank}:

> *The Notices are tools for institutions and researchers to identify Indigenous collections and data and recognize Indigenous rights and interests. The Notices were developed to create pathways for partnership, collaboration, and support of Indigenous cultural authority.*

> *Notices can be applied to websites, publications, datasets, museum exhibitions, items in a collection, genetic samples, and more. Institutions and researchers can generate Notices using the Local Contexts Hub.*

> *There are three categories of Notices: Engagement, Disclosure, and Collections Care Notices. See below for more information on the different types of Notices.*

![Image](../doc_files/plugin_images/LocalContexts_notices.png)

### Labels

This text is from the [Local Contexts website](https://localcontexts.org/labels/about-the-labels/){target=_blank}:

> *The Traditional Knowledge (TK) and Biocultural (BC) Labels are tools for Indigenous communities and local organizations. Developed through sustained partnership and testing within Indigenous communities across multiple countries, the Labels allow communities to express local and specific conditions for sharing and engaging in future research and relationships in ways that are consistent with already existing community rules, governance, and protocols for using, sharing, and circulating knowledge and data.*

> *Labels can be applied to websites, publications, datasets, museum exhibitions, items in a collection, genetic samples, and more. Communities can customize and apply their TK and BC Labels using the Local Contexts Hub.*

![Image](../doc_files/plugin_images/LocalContexts_labels.png)

### Projects

This text is from the [Local Contexts website](https://localcontexts.org/support/getting-started-on-the-hub/){target=_blank}:

> *What is a Local Contexts Project?*

> *Local Contexts Projects describe the context where Labels or Notices are being applied. For example, a Project could include: a website, university syllabus, dissertation, research publication, dataset, museum exhibition, archival record, item in a collection, library database, photography collection, voucher specimen, and/or metadata about a record.*

> *When you create a Local Contexts Project, you will be asked for Project details and contacts, and have the option to add metadata.*

> *Creating Projects allows institutions and researchers to generate Notices and engage, acknowledge, and make visible Indigenous interests in collections, information, and data. Communities may then choose how and when to add their Labels.*

> *Community accounts can apply customized Labels to Projects they create in the Hub, as well as to Projects they have been sent by institution and researcher accounts. You can see Projects that have been added to the Hub publicly on the Projects Board.*

![Image](../doc_files/plugin_images/LocalContexts_hub.png)

## Preparing to use the Local Contexts plugin

Local Contexts Notices are meant to encourage engagement with members of Indigenous communities, in the form of community created Labels or institutionally applied Notices. An "Open to Collaborate" Notice, for example, indicates that collaboration is welcome. As a result, you must be prepared to manage that collaboration. Be sure, if you are using Notices, that your Omeka site has a means for Indigenous community members to participate: account creation for Indigenous community members, the ability to add Local Contexts Projects and Labels to the site, a contact form, comments on items, or a plan for staff responsiveness to contributions. Think about your intended workflow for improving your collections in collaboration before proceeding further.

### Local Contexts Hub account

To use this plugin, you must have a Local Contexts Hub account. Creating a profile there allows you to have one or more Projects, which can then be connected to your Omeka installation with an API key.

[Go to the Local Contexts website to learn more and set up your Projects](https://localcontexts.org/support/getting-started-on-the-hub/#about-projects){target=_blank}. 

A Project can be designed for one single object, a collection, an exhibit, or for your entire institution. You may have simple needs - adding an "Open to Collaborate" Notice in your Omeka site footer - or complex ones, such as separate and unique sets of Labels for each of hundreds of items. Familiarize yourself with all of the Local Contexts Notice and Label options, and plan which set of Projects you will need to express your organization's situation. 

### Enable images in HTML elements

In order for Local Contexts thumbnail images to consistently appear in item metadata, a site administrator will need to add `img` to the "Allowed HTML Elements" list, and `img.src` to the "Allowed HTML Attributes" list in the Omeka Classic installation security settings. These settings only apply if HTML filtering is turned on for your site. 

![Image](../doc_files/plugin_images/LocalContexts_filter.png)

### Permissions

This plugin is available to Omeka Classic users at all levels. Any user can enter in a new API key and add new Projects to the Omeka site, and any user can apply those projects to items or exhibits to which they have access (e.g. Contributors can add them to items they create and/or own). Only Super Users can add Projects to the site footer. 

## How to use the LC plugin

### Import projects

With the plugin installed and active on your Omeka site, go to the "Local Contexts" plugin entry in the sidebar of the administrative dashboard. There you will be able to enter in your API key.

![Image](../doc_files/plugin_images/LocalContexts_API.png)

You can optionally select only a few of your Projects for import, by entering in their IDs. If you leave the "Projects" field blank, Omeka will load all the projects associated with your Local Contexts API key. 

When you save the page, the projects will load on an "Assign" tab. You will see each project name and all of its associated notices and labels. On this screen you can check the box of each project you wish to make available from the API key you just input. If you do not check any of these projects before saving the page, they will not persist in the Omeka site. Assigning the projects at this stage will not make them appear on your site - you will still need to apply them manually to items and exhibits, and place them into the site footer. 

![Image](../doc_files/plugin_images/LocalContexts_assign.png)

Omeka Classic will not save the API key, and does not create a persistent connection. If you update content on the LC Hubs website, you will need to re-enter the API key to update Omeka's information from the source. Then you will need to re-apply the modified projects to your footer, items, and exhibits where applicable. 

Other users on the Omeka site can add more projects by entering in another LC API key (or by entering the same key and specifying other projects by ID). Projects from all sources will be listed together in the Items and Exhibits and can be accessed by any user. 

If you return to this page after initially inputting an API key, you will see the same form to enter in a new API key. You can ignore this and save the page if you wish to see the list of projects already imported to your site. This will appear on a "Remove" tab. 

This table will allow you to remove projects from your site. If you wish to add these projects back later, you will have to re-import them by entering the API key again. This will not change any items or exhibits - anything already assigned will need to be removed manually. 

### Apply projects to your site

A Super User can choose to have one or more projects appear in the site footer. This will display all labels and notices attached to that project (in all languages), along with a link to the project in the LC Hubs registry. 

Go to the Plugins tab, then find the Local Contexts entry in the table. Click the "Configure" button. You will see a list of projects that have been added to your site through the API. You can check one or more boxes here to display all the related notices and labels for each selected project. 

![Image](../doc_files/plugin_images/LocalContexts_footer.png)

The LC content will load below the customized footer text that can be set in the theme configuration, and after the copyright information that is set in the installation settings. 

![Image](../doc_files/plugin_images/LocalContexts_footerPublic.png)

Note that Local Contexts labels and notices are designed to apply to materials of Indigenous interest. If your Omeka site or institution as a whole does not fit this definition, we do not recommend you use the site footer. Only apply LC notices and labels to relevant items and exhibits. 

### Apply projects to Omeka items

Site users can apply LC projects to individual Omeka items, or through batch-editing a number of items. Local Contexts notices and labels are used to fill out a metadata field on the item. 

![Image](../doc_files/plugin_images/LocalContexts_itemEdit.png)

Edit an item, then go to the "Local Contexts" tab at the top of the item editing screen. You then assign a LC project to a specific metadata field. 

![Image](../doc_files/plugin_images/LocalContexts_itemElement.png)

If you wish to apply only the available labels in a specific language, choose one from this dropdown. It will display all languages supplied by the Local Contexts Project that was imported. 

![Image](../doc_files/plugin_images/LocalContexts_itemLanguage.png)

Then, select the project you wish to assign to the item's metadata field. All available notices and labels of the project will be assigned to the item.

![Image](../doc_files/plugin_images/LocalContexts_itemProject.png)

When you save these edits, you will see that each intended notice or label appears in a separate metadata entry for your chosen field. 

![Image](../doc_files/plugin_images/LocalContexts_metadata.png)

You can manually delete each of these notices or labels if appropriate, with the "Remove" button on individual metadata entries. 

LC labels and notices are applied as HTML-formatted metadata entries that call upon images on the LC website and link to the project in the LC registry. The following image shows you the source code that is loaded into a metadata field when a project is applied to an item:

![Image](../doc_files/plugin_images/LocalContexts_source.png)

If you wish to apply your LC project to all of the items in a collection, you can select them all and batch-edit them. The Local Contexts options will display in the batch-editing field. 

![Image](../doc_files/plugin_images/LocalContexts_batchEdit.png)

Similarly, you can batch-apply LC notices or labels to items based on a tag, a location, or other metadata. Run a search to bring up your desired results, then batch-edit all items in the results set. 

### Apply projects to exhibits

![Image](../doc_files/plugin_images/LocalContexts_exhibitPublic.png)

You can include Local Contexts projects in your Omeka Classic exhibits. This plugin adds a new content block to exhibit design pages, which can be added to pages and set to display a project's notices and labels in one or all languages. 

![Image](../doc_files/plugin_images/LocalContexts_exhibit.png)

To add the block to an exhibit page, edit the page and click the "Local Contexts" block, then click "Add new content block" below. Select the desired project and choose a language if applicable. 

### Remove projects 

Once a project has been added to an item, exhibit block, or the site footer, it has to be removed manually. Edit the item or exhibit and delete the content by hand. Only Super Users can remove projects from the site footer. 

You can remove a project from the list of projects displayed in the future, by returning to the Local Contexts plugin entry in the sidebar. Save the empty form that is displayed first; this will show you the list of projects that have already been assigned. You can remove individual projects by checking the boxes and saving this page. 

![Image](../doc_files/plugin_images/LocalContexts_projects.png)

Deleting a project from the list of projects in the Local Contexts plugin page **will not** remove that project from resources to which it has been added. It will only remove the option to add it to resources in the future. 
