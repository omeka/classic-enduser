


Installing Omeka on OpenSUSE
-----------------------------------------------------------------------------------------------

These instructions have been tested on OpenSUSE 11.2 and 11.3. The
process should also be quite similar on other version 11.x
installations.

This guide starts with an OpenSUSE minimal server installation. If you
choose a standard installation the only difference should be that
ImageMagick is installed by default.

This guide uses the MySQL database name of **omeka\_db** and the MySQL
username of **omeka\_user** although you can use any names you like.
Just be consistent.

This guide also assumes you are installing everything on the same server
(ie. Apache and MySQL).

1\. login as root (or su to root)

2\. Install Apache, MySQL, PHP and ImageMagick from YAST

-   start YAST
-   select **Software-&gt;Software Management**
-   install the following packages if not already installed (other
    packages will be installed as prerequisites)
    -   php5
    -   php5-mysql
    -   php5-exif
    -   mysql
    -   apache2
    -   apache2-mod\_php5
    -   ImageMagick
-   configure Apache and MySQL to start at boot
    -   select **System-&gt;System Services (Runlevel)**
    -   switch to expert mode
    -   add runlevels 3 and 5 to apache2 and mysql
-   open firewalled HTTP port 80
    -   select **Security and Users-&gt;Firewall**
    -   select **Interfaces**
    -   assign the configured interface to the external zone
    -   select **Allowed Services**
    -   select **External Zone**
    -   add HTTP Server service
    -   select **Next**
    -   select **Finish**
-   exit YAST

3\. Set up MySQL

-   start MySQL:

        service mysql start

-   set root password and secure MySQL (select yes for everything; full
    output follows):

        mysql_secure_installation

``` {.de1}
NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MySQL
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!
 
 
In order to log into MySQL to secure it, we'll need the current
password for the root user.  If you've just installed MySQL, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.
 
Enter current password for root (enter for none): 
OK, successfully used password, moving on...
 
Setting the root password ensures that nobody can log into the MySQL
root user without the proper authorisation.
 
Set root password? [Y/n] 
New password: 
Re-enter new password: 
Password updated successfully!
Reloading privilege tables..
 ... Success!
 
 
By default, a MySQL installation has an anonymous user, allowing anyone
to log into MySQL without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.
 
Remove anonymous users? [Y/n] 
 ... Success!
 
Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.
 
Disallow root login remotely? [Y/n] 
 ... Success!
 
By default, MySQL comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.
 
Remove test database and access to it? [Y/n] 
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!
 
Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.
 
Reload privilege tables now? [Y/n] 
 ... Success!
 
Cleaning up...
 
 
 
All done!  If you've completed all of the above steps, your MySQL
installation should now be secure.
 
Thanks for using MySQL!
```

-   login to MySQL as root:

        mysql -u root -p

-   change to mysql database:

        mysql> use mysql

-   create the omeka user:

        mysql> insert into user(host, user, password) values('localhost','omeka_user',password('chosen password'));

-   create localhost permissions for omeka user:

        mysql> insert into db(host,db,user,Select_priv, Insert_priv, Update_priv, Delete_priv, Create_priv, Drop_priv) values ('localhost','omeka_db','omeka_user','Y','Y','Y','Y','Y','Y');

-   exit mysql:

        mysql> quit

-   create the omeka database:

        mysqladmin -u root -p create omeka_db

-   reload the database:

        mysqladmin -u root -p reload

-   set the default collation (connect to MySQL as root):

        mysql> ALTER DATABASE omeka_db DEFAULT CHARACTER SET 'utf8' DEFAULT COLLATE 'utf8_unicode_ci';

-   exit mysql:

        mysql> quit

3\. Enable mod\_rewrite

-   enable mod\_rewrite:

        a2enmod rewrite

-   edit **/etc/apache2/default-server.conf** and change the **Options**
    and **AllowOverride** directives in the **&lt;Directory
    "/srv/www/htdocs"&gt;** block as follows:


``` {.de1}
<Directory "/srv/www/htdocs">
        # Possible values for the Options directive are "None", "All",
        # or any combination of:
        #   Indexes Includes FollowSymLinks SymLinksifOwnerMatch ExecCGI MultiViews
        #
        # Note that "MultiViews" must be named *explicitly* --- "Options All"
        # doesn't give it to you.
        #
        # The Options directive is both complicated and important.  Please see
        # http://httpd.apache.org/docs-2.2/mod/core.html#options
        # for more information.
        Options FollowSymLinks
        # AllowOverride controls what directives may be placed in .htaccess files.
        # It can be "All", "None", or any combination of the keywords:
        #   Options FileInfo AuthConfig Limit
        AllowOverride All
        # Controls who can get stuff from this server.
        Order allow,deny
        Allow from all
</Directory>
```


-   restart apache:

        rcapache2 restart

4\. Configure Omeka

-   expand omeka\*.zip to **/srv/www/htdocs**
-   rename **/srv/www/htdocs/omeka\*** to **/srv/www/htdocs/omeka** or
    whatever suits your fancy
-   change ownership of the omeka directory and all files:

        chown -R wwwrun /srv/www/htdocs/omeka

-   edit **/srv/www/htdocs/omeka/db.ini** to reflect the above steps as
    follows


``` {.de1}
[database]
host     = "localhost"
username = "omeka_user"
password = "chosen password"
name     = "omeka_db"
prefix   = "omeka_"
;port     = ""
```



-   point browser to **<http://servername/omeka>**
-   fill in data and submit
-   assuming success remove **/srv/www/htdocs/omeka/install**

After all that you should have a fully functioning Omeka installation.
