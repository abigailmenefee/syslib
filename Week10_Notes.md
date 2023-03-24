#Week 10
##Install Wordpress

###Objective
The objective for this week was to successfully install Wordpress as well
as explore and customize my own Wordpress library site.

To successfully install Wordpress, a few things must be completed including:

1.Requirements
It is always important to check the requirements for an installation, when
downloading software outside of `apt` in CLI. In this case, we were able
to check the requirements by utilizing the following commands:
```
php --version
mysql --version
```

1.Download and Extract
It is necessary to download and extract the WordPress software. This was
accomplished by navigating to the `/var/www/html` directory and then
running the following commands:
```
sudo wget https://wordpress.org/latest.tar.gz
sudo tar -xzvf latest.tar.gz
```

1.Create the Database and a User
At this point, it was then necessary to create a MySQL user, which was
accomplished by switching to the root Linux user and then logging in
as the MySQL root user. One question I had at this point was whether the
remaining steps required us to remain as the root user, or if we could
have changed back to our home user after creating the WordPress
database in MySQL and creating a new user for that database.

1.Set up wp-config.php
The next step was necessary so that we could create a config or a login.php.
Therefore, it was necessary to add the database name, user, password into
the wp-config.php just like what has been previously done for the OPAC that
was created.

1.Change File Ownership

1.Run the Install Script
*Wordpress Install*
`http://104.155.167.15/wordpress/wp-admin/install.php`
*Username*
`abigail`
*Password*
`4u9N*@bvBPOkbN$z$Y`

1.Finishing Installation
Installation can be completed by following the prompts which appear on the
Welcome screen once running the previous install script.

1.Customization!
