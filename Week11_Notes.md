# Install Omeka

To install Omeka, I completed the following steps:

1. Check prerequisites and Install ImageMagick and mod_rewrite. After
installing the Apache module it is important to restart Apache.

```
sudo apt install imagemagick
sudo a2enmod rewrite
sudo systemctl restart apache2
```

1. Also install `unzip` as this will be used when unzipping the file.

```
sudo apt install unzip
```

1. First I needed to retreive the Omeka Classic Zip file and extract it. To
do this:

```
cd /var/www/html
sudo wget https://github.com/omeka/Omeka/releases/download/v3.1/omeka-3.1.zip
sudo unzip omeka-3.1.zip
sudo cp -r omeka-3.1 omeka
```

When looking at the above script, it is important to note that I chose to
copy the omeka-3.1 directory and rename as omeka, rather than just rename
the omeka-3.1 directory to omeka. I did this just in case I made a mistake!

1. Now that I am set up, it is necessary for me to create a new user and a     
new database in MySQL for Omeka. To do this:

```
sudo su
mysql -u root
create user 'omeka'@'localhost' identified by 'XvBj94a13';
create database omeka;
grant all privilegeson omeka.* to 'omeka'@'localhost';
show databases;
\q
```

1. Now that I created the user and database in mySQL, next it is necessary to
update the db.ini file located at `/var/www/html/omeka`.

```
sudo nano db.ini
host = "localhost"
username = "omeka"
password = "XvBj94a13"
dbname = "omeka"
```

1. Then I navigated to `/var/www/html/omeka/files` and changed file ownership.

```
sudo chown -R www-data:www-data *
```

1. Lastly, I restarted Apache2 and mySQL.

```
sudo systemctl restart apche2
sudo systemctl restart mysql
```

Once I completed these steps, I was able to navigate to http://104.155.167.15/omeka/
and complete the installation process. Now I can play around with the
customization functionalities for Omeka!
