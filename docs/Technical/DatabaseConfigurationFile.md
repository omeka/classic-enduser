# Database Configuration File

Before installing Omeka Classic, users must edit their database configuration in the db.ini file. Replace the Xs in the document with your MySQL database-specific information. You must have MySQL5 installed to use Omeka. 

## Required Fields 
These fields must be filled in for any Omeka installation. Your hosting provider or system administrator should provide you with the correct values for each of these. 

`host`  
The location of your database. This is most commonly "localhost" but may vary between hosting providers and servers. Other common possibilities include "mysql" or "mysql.localdomain". 

`username` and `password`  
These are specific to your MySQL database, and often different from your FTP username and password. 

`dbname`  
Your database name. Shared hosts often will prefix these names with your username, sometimes resulting in a database name like username_databasename. 

## Additional Fields 

These fields can usually be left untouched, but some installations or special situations may require their use. 

`prefix`  
The prefix field value is "omeka_" by default. To install more than one Omeka installation on the same database, change the prefix for each installation. 

`charset`   
This should almost never be changed from its default of "utf8". Only touch this setting if you are sure you know what you're doing. 

`port`  
MySQL servers usually use port 3306, and Omeka will use that port unless you specify something different here. Your hosting provider or server administrator will tell you if you need to use a different port.
