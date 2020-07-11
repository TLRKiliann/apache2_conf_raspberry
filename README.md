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
+ php
+ MySQL
+ phpmyadmin

APACHE2 :
=========

sudo apt update

sudo apt upgrade

sudo apt install apache2

sudo chown -R pi:www-data /var/www/html/

sudo chmod -R 770 /var/www/html/

wget -O verif_apache.html http://127.0.0.1

cat ./verif_apache.html

sudo apt install php php-mbstring

sudo rm /var/www/html/index.html

echo "<?php phpinfo(); ?>" > /var/www/html/index.php

sudo apt install mariadb-server php-mysql

sudo mysql --user=root

DROP USER 'root'@'localhost';


I will also cover the specifics of apache2 and give you some useful commands
to check and test your configuration.

I will also show you what the configurations of apache files are, such as :
+ apache2.conf
+ sites-available.conf
+ ports.conf
+ /etc/hosts
+ etc...

The ssl configuration files will soon come in the directory "apache2-ssl".

Enjoy it and hope to be helpfull !

ko@l@tr33

========================================================================================
