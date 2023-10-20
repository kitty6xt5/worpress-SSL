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
## INSTALL APACHE2.
To install apache2 type

```
sudo apt install apache2 -y

```
Enable the apache services-

```
sudo systemctl enable apache2

```
## Copy the public ip of that instance and paste it on web browser to check if its working or not.

## STEP 3 :
## INSTALL MY SQL.
To install mysql run the following command-
```
