Plugins/Contribution
====================


[Plugins](../Plugins.1.html "Plugins")


The Contribution plugin provides a way to collect stories, images, or other files from the public and manage those contributions in your Omeka archive as items. The form can also automatically add a reCAPTCHA box at the bottom of each form to prevent spam-bots from spamming your website.


 If you are using Omeka.net, go to the [instructions in the help section of Omeka.net](http://info.omeka.net/build-a-website/manage-themes-and-plugins/contribution/).

reCAPTCHA
-----------------------------------------------------------

Since the Contribution form allows anonymous users to add content to your site, it is highly recommended that you enable reCAPTCHA to help protect the form from spammers.

For information on how to configure and enable reCAPTCHA support in Omeka, see [ReCaptcha](https://omeka.org/codex/ReCaptcha "ReCaptcha").

Customizing the Contribution Form
-----------------------------------------------------------------------------------------------------------

Once installed, a tab called “Contribution” will appear in the site’s Dashboard navigation. Click on the Contribution tab to go to the plugin’s own Dashboard for managing the form, contribution settings, and the public contributors.

A basic contribution form is installed and ready to ask users to submit a Story or Image type, and to include their name and email address. If you want to modify the form, follow the steps below.

### Modify the Item Types Collected

- Click Contribution Types tab
- Click “Add a Type” to choose item types you wish visitors to share.
      - Story (document) and Image are pre-selected, but you may delete these or add new ones. These types will appear in a dropdown menu for visitors to this website. You may choose any item type available (moving image, sound, oral history, et al). Or you may create a new item type (See, Managing Item Types), which will then be available to select for the public form.
    - Once the item type is chosen, you may rename it for the form in the “Display Name” field, and also decide whether you want visitors to upload files (Allowed, Disallowed), or if you want to require them to upload files (Required). Click Save Changes.
    - For each item type you chose, pick the fields you want users to complete by clicking the edit button to the right of each item type.
- In the Contributed Elements section, click Add an Element and an empty text box will appear for you to add in a public prompt to help visitors answer the question related to a specific element (such as description, date, or subject) you have selected from the dropdown menu.
    - If you wish to offer users a choice of pre-determined answers for a specific element, you may install the [Simple Vocab plugin](SimpleVocab.html "Plugins/SimpleVocab") and create a set of controlled vocabulary for that element.
- When finished adding elements, save changes.

### Create Questions about Contributors 

- Click Contributor Questions to add questions about your
site’s contributors. You will notice that the name and email address fields are required and are not editable.
- To create a new question, click Add a Question. Write your question in the first box, and then choose the size of the field to be displayed on the public form. 
    - For a short answer, no more than one line, choose “tiny text.” 
    - For a longer answer, choose “text.”
- Click Submit Changes.

### Configure Settings for Submitting Contributions

- If you would like to send an email message to each contributor confirming their submission, enter an email address in “Contribution Confirmation Email”. Leave this field blank, if you do not want to sent an email.
- If you would like to receive an email notifying you of a new contribution, enter one or more email address(es) in “New Contribution Notification Emails” to receive a notification. Leave this field blank if you do not want anyone to be alerted of contributions by email.
- Select a custom slug, or URL, that is a relative path to the contribution form. If left blank, the default path will be named “contribution.”
- Set the terms of service or consent requirements for contributing to the site by entering text in the “Text of Terms of Service” box. All contributors to the website must agree to these terms in order to submit their contribution.
- If you choose, you may specify a collection where new contributed items will be organized. This is not required. Collection designations can be changed, and will only affect new contributions submitted after the collection is changed.
- Save Settings.

### Contributor Information

Click the Contributors tab to browse contributors’ names, emails, and items they submitted.

### Other Plugins

The Contribution plugin can allow other plugins to add and process additional questions on the public form.

- [Geolocation plugin](Geolocation.html)provides an option to add a map to the form to allow users to submit a location for their item.
- [Simple Vocab](SimpleVocab.html): allows you to create a list of controlled vocabulary for metadata fields that are then available to users filling out the contribution form.