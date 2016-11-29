
Install on Ubuntu using Terminal
================================



This is for installing Omeka 2.0 on a Ubuntu 12 server using only
Terminal. This can be easily adaptable for other Omeka releases. This is
based off of Bruce Fulton's
[guide](http://digin.arizona.edu/files/omeka.pdf) on installing Omeka
1.1 on a Virtual Machine.

Expected time - 10 minutes on a DSL/Cable connection.

**Step 1 - Set up LAMP server + Unzip + ImageMagick**

1\) Install Unzip

    sudo apt-get install unzip

2\) Install PHP 5

    sudo apt-get install php5

3\) Install PHP-MySQL (MySQLi does NOT work for Omeka 2.0)

    sudo apt-get install php5-mysql

4\) Install Apache

    sudo apt-get install apache2

5\) Install MySQL

    sudo apt-get install mysql-server

6\) Install ImageMagick

    sudo apt-get install imagemagick

Go to your IP. You should get a big "IT WORKS!!"

**Step Two - Download and Install Omeka 2.0 + Web User and Permissions**

1\) Download and install Omeka 2.0 (be in the home directory)

    cd
    wget http://omeka.org/files/omeka-2.0.zip
    unzip omeka-2.0.zip

2\) Move the Omeka files to your web directory

    sudo mv omeka-2.0/* /var/www/
    sudo mv omeka-2.0/.htaccess /var/www/

3\) Delete the old index.html file in www

    sudo rm /var/www/index.html

4\) Create a webuser and user

    sudo groupadd webdev
    sudo usermod -a -G webdev your_ubuntu_username
    cd /var
    sudo chown -R root.webdev www 

5\) Give permissions

    sudo chmod 775 www
    cd /var/www 
    sudo find . -type d | xargs sudo chmod 775
    sudo find . -type f | xargs sudo chmod 664
    sudo find files -type d | xargs sudo chmod 777
    sudo find files -type f | xargs sudo chmod 666

-   make sure you have permissions using ls - l
-   Archives are called files in 2.0

**Step Three – Create MySQL Db, edit db.ini and Enable Mod\_Rewrite**

1\) Create MySQL database (make sure to keep the ' ' and change password
to the password you want)

    mysql -u root -p

Enter password when asked Now that you are in the MySQL prompt, add and
edit your DB

    create database omeka;
    grant all privileges on omeka.* to 'put ubuntu username here that you defined in the permissions step'@'localhost'     identified by 'password';
    flush privileges;
    quit;

2\) configure db.ini with your MySQL settings

    sudo nano /var/www/db.ini

Edit the following

    [database]
    host = "localhost"
    username = "same username that is in the MySQL step"
    password = "password"
    dbname = "omeka"
    prefix = "omeka_"

To get out ctrl+o enter then ctrl+x

3\) Enable Mod\_Rewrite

    sudo a2enmod rewrite

Edit the other Mod-Rewrite file

    sudo nano /etc/apache2/sites-available/default

Change the "AllowOverride None" to "AllowOverride All"

    <Directory /var/www/>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride None
    Order allow,deny
    allow from all
    </Directory>

To

    <Directory /var/www/>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Order allow,deny
    allow from all
    </Directory>

4\) Restart Apache

    sudo /etc/init.d/apache2 restart

You may get an Apache error. Ignore it.

5\) Go to your IP/URL and set up Omeka 2.0! :D

