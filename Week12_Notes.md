# Install Koha
This week I installed the Koha Library Management System, which is an open source
integrated library system (ILS).

To accomplish this installation, it was important to do the following:
1. Set up a new Virtual Machine on Google Cloud. This machine type had
more RAM to account for the requirements needed to install Koha.
2. It was necessary to update access to the staff interface through the
specialized port 8080, rather than 80. This was accomplished by creating
a firewall rule on the Google Cloud Console.
3. Before installing Koha and its repositories, it was necessary to ensure
the virtual machine was updated and upgraded, as well as autoremoval and cleaning
of dependencies and packages was conducted.
4. `gnupg2` had to be installed on this virtual machine which is used to
"Create digital signatures, encrypt data, and aid in secure communication."

Once these items were accomplished, then it was possible to add the Koha Repository!
## Add Koha Repository
For the purposes of this installation, it was more convenient to complete
commands as the root user. Therefore, `sudo su` was utilized to switch over
to the root user.

To add the Koha repository, the following command was conducted, followed by a 
command that verifies the repo:
```
echo 'deb http://debian.koha-community.org/koha stable main' | sudo tee /etc/apt/sources.list.d/koha.list
wget -q -O- https://debian.koha-community.org/koha/gpg.asc | sudo apt-key add -
```

## Install Koha
After adding the Koha Repository, it was then possible to install `koha-common`.

However, after installing `koha-common` it was necessary to configure files for Koha as well.

## Configure Koha
The configuration file updated to change the intraport information from *80* to *8080*
was the `koha-sites.conf` file.

It was also important to setup the **mysql-server**; however, this was completed
in a different manner than what was completed previously on the other virtual
machine. To install and setup mysql, the following was completed:
```
apt install mysql-server
mysqladmin -u root password bibliolib1
```

After this was completed, it was necessary to enable URL rewriting and CGI functionality by:
```
a2enmod rewrite
a2enmod cgi 
```

As reflected within the change to the `koha-sites.conf` file, it was also necessary
to update the apache2 `ports.conf` file to add `Listen 8080`. After completing
this, then the default apache2 setup must be disabled, traffic compression
using deflate should be enabled, the bibliolib site should be enabled, and the
apache2 configurations should be reloaded and the system restarted.
```
a2dissite 000-default
a2enmod deflate
a2ensite bibliolib
systemctl reload apache2
systemctl restart apache2
```

## Koha Web Installer
After completing these tasks, it is then possible to log in to the Koha
web installer with teh credientials provided in the `koha-conf.xml` file.
For my system, these credentials were the following:
```
<user>koha_bibliolib</user>
 <pass>Q3KT@^_@Kw[jY`4T</pass>
```

In addition, my personal login for Koha once installed was:
```
username: abigail
password: Z*90adA33$sz
```

It was necessary, to update the OPACBaseURL line within Koha, to view
the public facing OPAC by entering the IP address of my server:
```
http://34.70.125.230
```

## Thoughts on Koha
Although the installation process had the potential to be complex due to
the customizabiity available to libraries, for my purposes it was relatively
straightforward. I look forward to further exploring the functionalities of
Koha, and the capabilities of each of its modules!
