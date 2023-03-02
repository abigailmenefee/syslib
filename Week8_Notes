# Week 8 - Create a Bare Bones OPAC, Part I

1. Understanding of how data from a relational database is retrieved
and entered using various technologies.
1. All of the modules available within an ILS rely on some kind
of underlying relational databse, like MySQL (which Koha uses).
1. We use PHP to retreive data from a table within the MySQL database.

## Objective of Week 8
Utilize PHP code that will allow us to search the books table
and retreive results based on a search query.

## Tasks

### HTML Form 
First I had to develop a HTML page that contained a form for entering queries.
This form allowed me to search any text as well as a start date and end date.
The start date and end date pulled from the copyright date.
While the text field is optional, the date fields are required.
By entering information into the form on the HTML page, this information serves as the 
foundation for a search query conducted by the search.php script.


### PHP Search Script
The search php.script utilizes the information provided within the HTML page form
to conduct a specific query. By entering text and/or dates, the PHP script
allows records within the books table within the relational MySQL database to be identified
with the results echoed accordingly.


### Adding Additional Entries
On another note, I had the opportunity to add more book entries to the  books table 
within the MySQL database. As a reminder to do this, follow a format similar to below.

It is important to highlight to login to the MySQL database you need to
use information housed in login.php. You have to use the opacdb to access
the books table and add or modify entries.:

```
insert into books
(author, title, publisher, copyright) values
('Emma Donoghue', 'Room', 'Little, Brown \& Company', '2010-08-06'),
('Zadie Smith', 'White Teeth', 'Hamish Hamilton', '2000-01-27');
```
