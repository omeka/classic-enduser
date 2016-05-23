---
title: Managing Users 2.0
---

The Users section allows the site Administrator to control who may
access the admin section of the site and what they can do. You may add,
delete, and assign categories of use.

[![Usersnav.png](https://omeka.org/c/images/e/e8/Usersnav.png)](https://omeka.org/codex/File:Usersnav.png)
</div>

Manage users by clicking on the Settings button in the right corner of
your dashboard, or go to /admin/users.

[![Usersbrowse.png](https://omeka.org/c/images/c/cc/Usersbrowse.png)](https://omeka.org/codex/File:Usersbrowse.png)


The Browse Users screen shows the number of users, as well as the
username, display name, email, and role for each user. The table
displaying users can be sorted by any of those values. From this page,
you may edit user information, delete users, or search existing users.

To sort users, simply click on the column heading by which you would
like to sort. If you want to sort descending rather than ascending,
click twice on the heading. The small paired arrows beside the column
heading indicate whether the sort is ascending (top arrow darker) or
descending (bottom arrow darker).

You can search users by username, real name, or email address. Username
and real name searches can include complete words or partial strings;
for example, you could search for any username containing “ja.” Email
searches only function with a complete email address.

User Levels and Access
-------------------------------------------------------------------------------------

You may assign Users different levels of access to the admin interface.

-   Super users can access all available pages in the admin. Supers are
    the only users with access to the Settings panel, choosing and
    configuring themes; adding and editing users; changing
    general settings.
-   Administrator users can access and edit Items, Collections,
    and Tags.
-   Contributor users can add items and edit items they have created.
    They may create exhibits using any item in the archive, and have
    permission to view any public exhibit from the administrative side.
-   Researcher users can see all of the Items, Collections, and Item
    Types pages--public or private, but cannot edit any content.

Add a User
-------------------------------------------------------------

To Add a User, select the green button in the upper left hand corner.


[![Usersaddnew.png](https://omeka.org/c/images/f/f8/Usersaddnew.png)](https://omeka.org/codex/File:Usersaddnew.png)


-   Fill in the fields for the new user. Assign a
    [role](https://omeka.org/codex/User_Roles "User Roles") to the user,
    and click the green Add User button below the form.
-   The new user will receive an email at the address you provide with
    their username and a link that takes them to a form to create
    a password. Until the new user activates his/her account, and
    inactive status appears after the Username.
-   To edit user information, including changing passwords, Super and
    Admin users may click on the "edit" button on the right side of
    the username.

Edit/ Delete Users
------------------------------------------------------------------------------

### Edit Users

To edit a user, click on the word Edit beneath the username in the
Browse Users page. This will direct you to a new page with tab options
labelled General, Change Password, and API Keys.

[![Useredt.png](https://omeka.org/c/images/1/18/Useredt.png)](https://omeka.org/codex/File:Useredt.png)

On the General tab you can edit the username, display name, email, and
role of the user. You can also toggle whether a user is active or
inactive. Inactive users are not deleted, so the items, collections, and
tags created by that user remain associated with their account, but the
individual can not longer log into the site to make changes or create
new data.

The Change Password tab requires you to enter a new password twice, but
does not require the user’s original password.

[![Usapi.png](https://omeka.org/c/images/b/bd/Usapi.png)](https://omeka.org/codex/File:Usapi.png)

To add an API key for a user, enter text for a label for the key in the
field provided and then click “Update API Keys.” An API key will be
generated and added to the page. To remove a key, click the checkbox in
the Rescind column of keys.

Note: you must save changes before switching tabs.

### Delete Users

Find the user you wish to delete from /admin/users/browse, and click the
'delete' button found beneath the username. You will be asked to confirm
the action before you permanently delete the user. Items, collections,
and tags created by this user will remain in the system, but will no
longer be associated with this user.
