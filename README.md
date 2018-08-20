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
```

## Authors

* Alexandre Willerval - [alexandre.willerval.net](http://alexandre.willerval.net/)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
