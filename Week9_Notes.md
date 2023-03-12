# Week 9 Notes
## Creating a Bare Bones Cataloging Module

### Objective
Previously I entered records within the
MySQL database; however, by creating a
cataloging module, I will be able to
create a graphical user interface.
This allows me to enter records into
the MySQL database via the graphical user
interface.

#### Creating the HTML Page and PHP Cataloging Page
It is important to note, the bibliographic
data which I can enter into the graphical user
interface, must mirror the **books** table within the MySQL database.

Within the PHP script, one thing I noticed was that
the return to cataloging page link referenced 11.111.111.111/cataloging.
Therefore, when I added a record, it would not go back to the cataloging page. I updated this
to include the external IP for my server and it worked smoothly.

The index.html script dictated the this graphical interface.
Through this HTML page, I was able to enter the
Author, Title, Publisher, and Copyright date. However,
for this to work, it referenced the insert.php script.

The insert.php script, established a connection with
the MySQL database, opened the database, and prepared the information to be entered into the books table within the
MySQL database, after which the connection was closed

Lastly, login information had to be generated
to ensure only those with the correct username
and password were able to access the MySQL database from
the HTML pagae. To do this, the apache2.conf file had to be updated from Allow Override None to 
AllowOveride All.




