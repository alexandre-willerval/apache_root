# apache_root

How to setup my personal Apache2 conf

## Getting Started

If you want to recreate the same full dev environment as I have, there are a few steps to follow:
```
sudo apt-get update
sudo apt-get install dist-upgrade
sudo apt-get install apache2
sudo apt-get install php
sudo apt-get install libapache2-mod-php7.0
sudo apt-get install mysql-server
sudo apt-get install phpmyadmin
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-apache
mkdir apache_www
git clone https://github.com/alexandre-willerval/apache_root/ apache_www
cd /etc/apache2/sites-available
sudo vim 000-default.conf
  - edit the "DocumentRoot" option: DocumentRoot /home/cloud/apache_www
  - save and quit with: :wq
cd /etc/apache2
sudo vim apache2.conf
  - change the line "Directory /var/www" into: Directory /home/cloud/apache_www
  - add at the end of the file the line: Include /etc/phpmyadmin/apache.conf
  - save and quit with: :wq
sudo service apache2 restart
sudo dpkg-reconfigure locales
  - select "fr_FR.UTF-8" with SPACE and valid with ENTER
  - select "fr_FR.UTF-8" as default locale and valid with ENTER
sudo certbot --apache
```

## Built With

* [Apache](https://httpd.apache.org/) - 
The Apache HTTP Server Project is an effort to develop and maintain an open-source HTTP server for modern operating systems including UNIX and Windows.
* [PHP](http://www.php.net/) -
PHP is a popular general-purpose scripting language that is especially suited to web development. Fast, flexible and pragmatic, PHP powers everything from your blog to the most popular websites in the world.
* [MySQL](https://www.mysql.com/) - The world's most popular open source database.
* [phpMyAdmin](https://www.phpmyadmin.net/) - phpMyAdmin is a free software tool written in PHP, intended to handle the administration of MySQL over the Web.
* [certbot](https://certbot.eff.org/) - Automatically enable HTTPS on your website with EFF's Certbot, deploying Let's Encrypt certificates.


## Authors

* Alexandre Willerval - [alexandre.willerval.net](http://alexandre.willerval.net/)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
