

Install on Ubuntu
=================



Install on Ubuntu (8.10) or [Run a Virtual
Machine](Run_a_Virtual_Machine.html "Run a Virtual Machine")

How to install Omeka on Ubuntu (8.10, 9.04, 10.04 LTS) 
-------------------------------------------------------------------------------------------------------------------------------------------------------------

*This message originally appeared on the \[Ubuntu forum
<http://ubuntuforums.org/showthread.php?p=6156244#post6156244>\] by Tom
Hohenstein. Edits by Shane Landrum to include Ubuntu 10.04*

I've used Ubuntu and the forum for over a year and a half now and I've
never posted a how to, mostly because I've never done anything new
before. I recently installed Omeka at home and I couldn't find a guide,
so I thought I'd share (because I've been extremely thankful for all the
guides I've used). This my first guide so it might not be perfect. Check
the Omeka documentation and post your comments as needed. I may not be
able to help, but in my experience, there is always another friendly
Ubuntu user who can.

I'm not a programmer and I know virtually nothing about server security.
This guide is for installing Omeka on your own computer for testing and
development. I also assume you're as stupid as me.

Please read the entire guide before beginning (I've learned that one the
hard way)

Step 1 – Select LAMP server for installation

-   Open your Synaptic Package Manager
-   Under Edit, select “Mark Packages by Task”
-   Check LAMP Server

Step 2 – Select phpmyadmin for installation

-   With the Synaptic Package Manager open search “phpmyadmin”
-   Mark phpmyadmin for installation

Step 3 – Select ImageMagick for installation

-   With the Synaptic Package Manager open search “imagemagick”
-   Mark imagemagick for installation

Step 4 – Install Packages

-   click Apply in the Synaptic Package Manager and install
-   You'll have to set a root password for you mysql database
-   Select Apache2 for the type of server to configure phpmyadmin to.

Step 5 – Create mysql database for Omeka

-   Open Firefox (or your preferred open source web browser
-   Type in localhost/phpmyadmin as the url
-   Insert root as your username and type in your password
-   Click on Privileges (roughly the 7th link under Create a new
    database
-   On the next screen click Add a new User
-   Type in a username, select localhost as the host, select a password
    and retype it.
-   On the same screen under Database for user select Create a database
    with same name and grant all privileges
-   hit Go and check for the new database

Step 6 – Enable mod\_rewrite in Apache2 (the hardest part)

-   Open the terminal, and login as root (sudo -i and then enter your
    root password)
-   Enter the command: a2enmod rewrite
-   Next command nautilus
-   This will open up the Nautilus – which is probably easier than the
    command line for rookies like myself.
-   Navigate to the filesystem, then etc, then apache2-/etc/apache2/
-   Open the apache2.conf file (you really should back it up first)
-   At the bottom of the file copy in
``` {.de1}

Enable mod_rewrite
-------------------------------------------------------------------------
RewriteEngine On
</IfModule>


-   Save the file and close it.
-   Next go to sites-enabled
-   open 000-default (again backup to be safe) and under

&lt;Directory /var/www/&gt;

change "AllowOverride None" to "AllowOverride All"

-   Save the file and close it.
-   Leave Nautilus open.

NOTE: for 10.04, you'll also need to do this in a terminal window, to
enable mod\_rewrite:


``` {.de1}
cd /etc/apache2/mods-enabled
sudo ln -s ../mods-available/rewrite.load rewrite.load
```


Step 7 – Download Omeka to your Desktop

Step 8 – Extract Omeka to your Desktop

Step 9 – Navigate back to your file system, then to var, then www (i.e.,
navigate to /var/www/)

Step 10 – Drag and drop the extracted Omeka folder into the www folder
(I also recommend renaming it to something simple like Omeka).

Step 11 – Right click on the Omeka folder and select Properties.

Step 12 – Go to the Permission tab and under Others change Folder access
to Create and delete files

Step 13 – Configure db.ini and config.ini

-   Open the Omeka folder and select the db.ini folder
-   Replace all the XXXX with the proper information
    -   host = “localhost”
    -   username = “whatever user you created in step 5”
    -   password = “whatever the password you gave the user in step 5”
    -   name = “whatever username you created in step 5”


-   Open the Omeka folder, go into application/config, and
    select config.ini.changeme.
-   Rename it to config.ini
    -   Edit the mail-sending options if you wish.

Step 14 – Close the db.ini and config.ini, close Nautilus, and switch to
the terminal to restart Apache.

-   Enter the command /etc/init.d/apache2 restart

Step 15 – Switch to your browser and navigate to
<http://localhost/whatever_you_named_the_omeka_folder/*>

Step 16 – Start playing with Omeka.

Hope this helps someone and let me know if I missed anything along the
way.
