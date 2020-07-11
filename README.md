=======================================================================================

		APACHE2 SERVER CONFIGURATION PHP, MYSQL, PHPMYADMIN AND MORE...

=======================================================================================

Hello,

I thought it would be nice to make a guide to configure apache2 on a rapsberry
(pi 3 B) with PHP and MySQL.
Also, you can find another directory I made to configure a self-signed ssl
certificate with openssl called "apache2-ssl".
In this tutorial, I will show you how to install successively :

+ apache2
+ PHP
+ MySQL
+ PHPMyAdmin

INSTALL APACHE2 :
=================

sudo apt update

sudo apt upgrade

sudo apt install apache2

sudo chown -R pi:www-data /var/www/html/

sudo chmod -R 770 /var/www/html/

wget -O verif_apache.html http://127.0.0.1

cat ./verif_apache.html


INSTALL PHP :
=============

sudo apt install php php-mbstring

sudo rm /var/www/html/index.html

echo "<?php phpinfo(); ?>" > /var/www/html/index.php


INSTALL MySQL :
===============

sudo apt install mariadb-server php-mysql

sudo mysql --user=root

>DROP USER 'root'@'localhost';

>CREATE USER 'root'@'localhost' IDENTIFIED BY 'password';

>GRANT ALL PRIVILEGES ON *.* TO 'root'@'localhost' WITH GRANT OPTION;

>exit

INSTALL PHPMyAdmin :
====================

sudo apt install phpmyadmin

select apache2 server
select "no" for question relating dbconfig-common

sudo phpenmod mysqli

sudo ln -s /usr/share/phpmyadmin /var/www/html/phpmyadmin

Allow port 80 to fire-wall :
For example with ufw :

sudo ufw allow 80/tcp


The ssl configuration is coming soon in the directory "apache2-ssl".

I will also cover the specifics of apache2 and give you some useful commands
to check and test your configuration.

I want also show you how to configure apache files, such as :
+ apache2.conf
+ sites-available.conf
+ ports.conf
+ /etc/hosts
+ etc...
to the directory : /etc/apache2/


Enjoy it and hope to be helpfull !

ko@l@tr33

========================================================================================
