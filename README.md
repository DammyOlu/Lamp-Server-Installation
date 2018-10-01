### Lamp-Server-Installation

Step-by-Stem guide on how to install Lamp-Server and wordpress on Ubuntu 16.04

#### The fisrt step was to update my system. i.e Ubuntu , this is to ensure the repositories were updated with the latest versions made 
sudo apt-get update 
#### Its time to Install Lamp-server. i.e Apache,Mysql,PHP, after the install i got a propmt to give my permission for the installation to proceed. Enter y.
sudo apt-get install Lamp-server^ #### apt-get is used to install a package 
#### I then had to initialize the database for my wordpress 
sudo mysql -u root -p  #### With this code i am able to log in as root user with password
#### I then had to create a database
create database wordpresssdb; #### My data base is called wordpressdb
#### I also had to create a user on this database
create user wordpressuser@localhost identified by 'password'; #### creates user that will be recognised on this server by the password 'password'
#### I also had to grant the user all the privileges on the database
grant all privileges on wordpressdb.* to wordpressuser@localhost;
####I then had to load the privileges
flush privileges;
The last step was to exit before installing wordpress
exit

Step 4
####Installing wordpress
####change directory into the tmp directory
cd /tmp
#### download wordpress using wget
wget http://wordpress.org/latest.zip
#### I had to unzip the the file i just downloaded into /var/www/html/
unzip -q latest.zip -d /var/www/html/   #### The -q allows the operation to be performed quietly
chown -R www-data:www-data /var/www/html/wordpress
chmod -R 755 /var/www/html/wordpress
mkdir -p /var/www/html/wordpress/wp-content/uploads ### mkdir creates a directory and -p creates subfolder and parents folder even when the parents folder does not exist
chown -R www-data:www-data /var/www/html/wordpress/wp-content/uploads

Open web browser
http://ipaddress/wordpress
or
localhost/wordpress/
