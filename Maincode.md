# CREATING A WORDPRESS WEBSITE AND GIVING IT A SSL CERTIFICATE
### To create this - we are going to use the lamp stack
## LAMP Stack
The LAMP stack is a popular open-source solution stack used primarily for web development.<v>
 Here, LAMP stands for Linux, Apache MySQL, PHP, and Perl. It consists of 4 components for a fully functional web development environment.

## Linux: 
 Linux is the first layer. Linux is the foundation of the stack model and for all other layers. Linux is free and also it is open source os.

## Apache: 

 This is the second layer.This layer provides web server software.Web servers translate web browsers to the correct website.<v> 
 Apache’s web server processes requests and delivers web assets via HTTP on port 80 to make the application accessible through a simple URL to everyone in the public domain.

## MySQL: 
 This is the third layer where databases reside. MySQL is an open-source relational database management software for storing application data.<v> 
 MySQL stores information that can be accessed by scripting to build a website.<v> 
 MySQL can be offloaded to a separate host server in high-end configurations.

## PHP: 
the fourth and final layer is PHP. PHP is an open-source scripting language that Apache can use to create dynamic web pages.<v> 
The scripting layer is made up of PHP or similar web programming languages. This layer hosts websites and web applications.

# So, Lets start our Task....
## STEP 1 : 
## FIRST OF ALL WE HAVE TO CREATE AN INSTANCE OF UBUNTU IMAGE AMI.


Launch the instance and connect it through ssh on terminal.

```
ssh -i "your key" ubuntu@(your publicip).compute-1.amazonaws.com
```

After connecting the instance, type -
```
sudo apt update
```
## STEP 2 : 
## INSTALL APACHE2
To install apache2 type-

```
sudo apt install apache2 -y

```
Enable the apache services-

```
sudo systemctl enable apache2

```
## Copy the public ip of that instance and paste it on web browser to check if its working or not.

## STEP 3 :
## INSTALL MY SQL
To install mysql run the following command-
```
sudo apt install mysql-server -y

```
Enable MySQL-

```
sudo systemctl enable mysql

```
## STEP 4 :
## INSTALL PHP
WordPress is a PHP-based CMS.<v>
Ubuntu 20.04 defaults to PHP 7.4 so,
To install php type-
```
sudo apt install php libapache2-mod-php php-mysql -y

```
WordPress and many plugins use PHP extensions, which you will need to install manually.

```
 sudo apt install php-curl php-gd php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip -y

```
To verify that PHP 7.4 has been successfully installed type:

```
php -v

```
Restart apache2 service
```
sudo systemctl restart apache2

```
## STEP 5 :
## Install WordPress
Once we have set our LAMP environment, nOW we can begin installing WordPress.<V>
We will download the WordPress installation files and place them in the default web server root directory of /var/www/html. for this type-
Change the directory ,type-
```
cd /var/www/html

```
Download the latest WordPress install with the following command.

```
sudo wget -c http://wordpress.org/latest.tar.gz

```
Extract the files-

```

 sudo tar -xzvf latest.tar.gz

```

The extracted WordPress files will now be placed in the WordPress directory at the given location.

```
/var/www/html/wordpress

````

The user of your web server must own these files.

We are using Apache as our web server. Apache is running on Ubuntu 20.04.<v>
The following command will allow you to change the owner of these files and set the appropriate permissions:

```
sudo chown -R www-data:www-data /var/www/html/wordpress

```

## STEP 6:
## CREATE A DATABASE FOR WORDPRESS

Now we will create a WordPress database. 
Log in to your MySQL root account via Terminal by entering:

```
 sudo mysql -u root

```

Create a separate database for WordPress to manage data-
type,
```

CREATE DATABASE (your_databasename);

```

To access the new database, we will create a MySQL user account.
type- 

```
CREATE USER (your_username)@localhost IDENTIFIED BY '(your_password)';

```

New user created.
Give privileges to your user,type-

```
GRANT ALL PRIVILEGES ON (database_name). * TO (your_username)@localhost;

```

After completing the above, flush your privileges to allow MySQL to implement the changes.

```

FLUSH PRIVILEGES;

```
type exit
```
exit;

```

Allow the executable permission to be granted to WordPress folder.

```
sudo chmod -R 777 wordpress

```

Now, type-

```
cd wordpress

```

## STEP 7: 
## SETUP AND CONFIGURING OF WORDPRESS
After setting up a database for WordPress, The final step is to set up and configure WordPress.<v>
Re need to create a configuration file for WordPress.<v>
Rename the sample WordPress configuration file using the following command:

```

mv wp-config-sample.php wp-config.php

```

To Edit the wpconfig file type-

```

sudo vim wp-config.php

```

Update the database settings by replacing your_databasename, your_user, and your_password with your own details.

Save the file and close it.

Once you have done this, you can access your WordPress page to finish the installation.<v>
Open the browser and go to-

```
http://(your-ip-address)/wordpress/wp-admin/install.php

```
The next screen will open. Click on Continue and select the language.


