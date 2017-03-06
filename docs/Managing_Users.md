---
title: Managing Users 2.0
---

The Users section allows the site Administrator to control who may access the admin section of the site and what they can do. You may add, delete, and assign categories of use.

![Arrow points to ](../doc_files/Usersnav.png)

Manage users by clicking on the Users tab in the top navigation of your admin dashboard.

![Browse users](../doc_files/Usersbrowse.png)

The Browse Users screen shows the number of users, as well as the
username, display name, email, and role for each user. The table
displaying users can be sorted by any of those values. From this page, you may edit user information, delete users, or search existing users.

To sort users, simply click on the column heading by which you would like to sort. If you want to sort descending rather than ascending, click twice on the heading. The small paired arrows beside the column heading indicate whether the sort is ascending (top arrow darker) or descending (bottom arrow darker).

You can search users by username, real name, or email address. Username and real name searches can include complete words or partial strings; for example, you could search for any username containing “jam.” Email searches only function with a complete email address.

User Levels and Access
------------------------------------------------------------

You may assign Users different levels of access to the admin interface.

**Super users**:
- can access all available pages in the admin. 
- are the only user role which has access to the Appearance, Plugins, Users, and Settings tabs on the top navigation;
- can add, edit, delete, and publish all content types;
- can interact with all plugins.

**Administrator** users:
- can add, edit, delete, and publish all Items, Collections, and Tags in the site;
- can add, edit, delete, and publish Exhibits;
- can interact with any plugin that adds a tab to the left-hand navigation.

**Contributor** users:
- can add items, but can only edit and delete items they created, and cannot publish any items;
- can add Collections and edit, delete, and publish any collections they create;
- may create exhibits using any item in the archive;
- may only interact with certain plugins.

**Researcher** users:
- can view all content, including items, collections, tags, maps, exhibits, and contributed items, but cannot add, edit, or delete anything.

Add a User
-------------------------------------------------------------

To Add a User, select the green button in the upper left hand corner.

![Add user form](../doc_files/Usersaddnew.png)


-   Fill in the fields for the new user. Assign a [role](/User_Roles.md) to the user, and click the green Add User button below the form. 
-   The new user will receive an email at the address you provide with their username and a link that takes them to a form to create a password. Until the new user activates his/her account, and inactive status appears after the Username.
-   To edit user information, including changing passwords, Super and Admin users may click on the "edit" button on the right side of the username.

Edit Users
----------------------------------------------------------------
To edit a user, click on the word Edit beneath the username in the Browse Users page. This will direct you to a new page with tab options labelled General, Change Password, and API Keys.

[![Edit User form](../doc_files/UserEdit.png)

On the General tab you can edit the username, display name, email, and role of the user. You can also toggle whether a user is active or inactive. Inactive users are not deleted, so the items, collections, and tags created by that user remain associated with their account, but the individual can not longer log into the site to make changes or create new data.

The Change Password tab requires you to enter a new password twice, but does not require the user’s original password.

![User API form](../doc_files/Usapi.png)

To add an API key for a user, enter text for a label for the key in the field provided and then click “Update API Keys.” An API key will be generated and added to the page. To remove a key, click the checkbox in the Rescind column of keys.

Note: you must save changes before switching tabs.

Delete Users
----------------------------------------------------------------

Find the user you wish to delete from /admin/users/browse, and click the 'delete' button found beneath the username. You will be asked to confirm the action before you permanently delete the user. Items, collections, and tags created by this user will remain in the system, but will no longer be associated with this user.
