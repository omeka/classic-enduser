# Backing up an Omeka Classic Database

WordPress has terrific documentation on their website about [Backing up Your Database](https://wordpress.org/support/article/backing-up-your-database/){target=_blank} that will help guide you through this process. You can go ahead and do this one of two ways: directly executing mysql commands on the command line, or using PHPMyAdmin.

## mysqldump

Using `mysqldump` to back up from the command line is simple, though you will need to know your host name, database name, and user name/password. A full explanation for using `mysqldump` to back up a database can be found at [MySQL.com](http://dev.mysql.com/doc/refman/5.5/en/mysqldump.html){target=_blank}.

Log in via the command line, and change directories to the directory where you want to save your database file. To create a file called `omeka_db_backup.sql` with your database, use the following.

    mysqldump -h localhost -u username -p omeka_db_name > omeka_db_backup.sql
