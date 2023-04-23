# Installing Apache HTTP Server

## Review Apache Getting Started

### Clients, Servers, and URLS
1. URL - Uniform Resource Locators
1. Client - i.e A Web Browser
1. Server - i.e. Apache HTTP Server

### Hostnames and DNS
1. Domain Name System (DNS)

### Configuration Files and Directives

### Web Site Content

### Log Files and Troubleshooting

## Install Apache2
After ensuring virtual machine is updated,
install apache2:

`sudo apt install apache2`

## Basic Checks
1. By utilizing `cd /var/log`, I am now able
to identify the apache2 directory. After utilizing
`cd apache2` and conducting `ls`, I now have access
to an **access.log** and **error.log**.

## Creating a Web Page
1. Install `w3m`, a command line web browser.
1. Once installed, I can now run:

`w3m 127.0.0.1` or `w3m localhost`

1. By utilizing `ip a`, I can identify my NIC, and use
this to conduct `w3m [NIC IP Address]`
1. By utilizing, the NIC IP Address, the Loopback IP
Address (LocalHost), I can visit default site. I can
also utilize the External IP Address for my VIrtual Machine
to access a graphical version of this Apache 2 Ubuntu
default page.
1. Apache2 by default utilizes index.html. If I customize
the index.html file, then I can control what appears when
access the NIC IP Address, the Loopback IP Address 
(LocalHost), or the External IP Address.
1. It is important to note that since I am not in my
personal directory, I have to utilize `sudo`.

# Installing and Configuring PHP

## What is PHP?
PHP is a server-side programming language, which means it must
be installed on the server in order to be used. The main use of
PHP is to interact with databases in order to create data-based
page content.

### Install PHP

`sudo apt install php libapache2-mod-php`
`sudo systemctl restart apache2`
`systemctl status apache2`

### Basic Configurations
Remember how earlier I said Apache2 utilizes index.html
as default to a file? Since we are using PHP, we now want to
use index.php as default to a file. To do this, we need to edit
**dire.conf** file in the **/etc/apache2/mods-enabled/** directory.

1. You can check a configuration by running `apachectl configtest`.
1. You can reload the Apache2 configuration by running
`sudo systemctl reload apache2`.
1. You can restart Apache2 by running `sudo systemctl restart apache2`.


# Installing and Configuring MySQL
It is important to understand that a relational database, is named
such because they deal with tables of data related by a common
field.

## Install and Set Up My SQL
## Create and Set Up a Regular User Account
## Create a Practice Database
## Logging in as Regular User and Creating Tables
## Adding  Records into the table
## Testing Commands
Within this section, I had the opportunity to create my own
tables within MySQL. For additional guidance please refer to 
[Installing and Configuring MySQL](https://cseanburns.net/WWW/systems-librarianship/16-installing-configuring-mysql.html)

## Logging into MySQL
To log into MySQL, I need to do the following:

`mysql -u opacuser -p`

Enter the Password: lkajaoiua32

