# General Settings

Find the general site settings by clicking on the "Settings" link in the top navigation bar of the admin view. Settings are only accessible to [Super Users](../Users.md).


![General Settings screenshot](../../doc_files/Generalsettings.png "General Settings screenshot")

In the "General" Settings tab, you may edit the fields you filled in when you installed your site, and add other information.

The fields are as follows:

-   **Administrator Email**: Address entered will send emails to new users, when created. This address will be where emails appear to be from, in any administrative emails sent from the page. (This field is required)
    - Some hosting providers may require this email to match your domain (`you@yoursite.org`).
-   **Site Title**: Appears as the name of your site on the homepage.
-   **Site Description**: Descriptive text entered here appears in the website's `head` tags, but is not published on the homepage. This may be displayed when your site comes up in search-engine results. 
-   **Site Copyright Information**: Fill in this text box with authorship or licensing information about your site. Then, when configuring your theme, you can check a box to display this copyright information in the footer of each page of your site. Site copyright information is always shared in the header of each page of your site, making it machine-readable whether or not it is displayed in your footer, in a `<meta name="copyright" content="">` tag.
-   **Site Author Information**: Fill in the names of contributors to the website. This information appears in the website’s header, in a machine-readable `<meta name="author" content="">` tag, but is not published visibly on the site.
-   **Tag Delimiter**: If you wish to separate tags by a character other than a comma, specify it in the Tag Delimiter field. You can enter in characters such as spaces, dashes, or pipes (|) here.
    - Be aware that if you change the setting after tags have been created, you run the risk of splitting tags. For example, if you have tags with hyphens already in them, such as "stone-age", changing the tag delimiter to a "-" may make those items tagged with "stone" and "age" instead. 
-   **ImageMagick Directory Path**: If you are receiving ImageMagick errors, click the "Test" button here to be sure that the path to its directory is properly routed. Some hosting services may need you to enter the correct path manually after installation. 