## PYTHON FLASK CHEATSHEET

### Author

- *Reuben Kipkemboi*

## Table of Content

+ [Introduction](#introduction)
+ [Concepts](#concepts)
+ [Technology Used](#technologies-used)
+ [License](#license)
+ [Authors Info](#authors-info)

## Introduction

Flask is a web framework that has tools that allow us to create web applications.

It belongs to a category of web frameworks known as a micro-framework. This means Flask contains very few dependencies out of the box

**Main Dependencies**

- Werkzeug - This provides flask with _routing_,_debugging_ and _web server_ capabilities.

- Jinja 2 - This provides template support for flask.

### Setting up Flask

The most convenient way to install Flask is using a virtual environment.

**Creating a virtual Environment**

```
python3.8 -m venv --without-pip virtual
```
or *If you have pip installed globally*

```
python3.8 -m venv virtual 

```
*Remember virtual is the name of our virtual environment but you can choose another name*
**Activating and Deactivating the virtual environment**

```sh
source virtual/bin/activate
```

**Deactivating**
```sh
deactivate
```

**Updating pip to the latest version if you don't have it installed globally**

```sh
curl https://bootstrap.pypa.io/get-pip.py | python

```

### Installing Flask
```sh
pip install flask
```

## Concepts

### Template Inheritance
Jinja allows for template inheritance. That is we can inherit some properties of a template in other child (or derived) templates.

looks like this;
create a `base.html` file

```py

<!DOCTYPE html>
<html>
    <head>
        #You can have your styles linked here ......
        <meta charset="utf-8">
        {% if title %}
        <title> {{ title }}</title>
        {% else %}
        <title> Welcome to flask cheatsheet </title>
        {% endif %}
    </head>
    <body>
        # Content block
        {% block content %}

        {% endblock%}
        #end of block content
    </body>
</html>
```
Inside the body tag we have the block control block that defines elements that can be changed by the derived template.

The `block content` is what we will be replacing in our other templates.

**Adding Bootstrap**

```
pip install flask-bootstrap
```
[ Full List of Flask-Bootsrap available blocks](https://pythonhosted.org/Flask-Bootstrap/basic-usage.html#available-blocks)

### WTF Forms

Flask-WTF extension is a flexible form rendering and validation library.

It provides a lot of out of the box functionality Like security against
CSRF(Links to an external site.) Cross site Request Forgery. And also offers validation.

**Installing WTF Forms**

```
pip install flask-wtf 
```

To enable CSRF protection one needs to create a Secret Key that will verify authenticity of requests with form data.

*simple form class*

```py
class ExampleForm(FlaskForm):

    title = StringField('Field title or label',validators=[Required()])
    fieldname2 = TextAreaField('Field label', validators=[Required()])
    submit = SubmitField('Submit or any text to appear e.g LOGIN')
```

## Running Flask Applications

A flask extension called Flask-Script that is a command line parser that allows us to create startup configurations.

*Installing flask script*
```
pip install flask-script
```


# Databases
**Categories**

+ **SQL** -Structured Query Language databases
+ **NOSQL**- Non Structured Query Language databases.

## Postgres
This is a type of SQL database
<ol>
<li>Installation</li>

### Ubuntu

- First update by running the command:

```sh
sudo apt-get update
```

- To Install progress

```sh
sudo apt-get install postgresql postgresql-contrib libpq-dev
```
*when prompted enter option `Y` to continue and wait for installation to complete*

- Defining a user Role

*Postgres uses "roles" to aid in authentication and authorization. By default, Postgres creates a Postgres user and is the only user who can connect to the server.*

Now run the commands below respectively (If working on an elementary Os)

```sh
sudo service postgresql start
```

```sh
sudo -u postgres createuser --superuser $USER
```
*Provide a password if prompted to provide one*

```sh
sudo -u postgres createdb $USER
```

```sh
touch .psql_history
```
*creates the .psql_history in order to save your history*

- Now connect to the postgres server
```
psql
```

*[for other versions of Operating systems psql installations](https://www.postgresql.org/docs/current/)*

<li>SQL Basics</li>


Common SQL commands

```sh
CREATE DATABASE database_name; # From the $USER database.

CREATE TABLE table_name (id serial PRIMARY KEY, some_column varchar, another_column int);
ALTER TABLE table_name ADD column_name boolean;

ALTER TABLE table_name DROP column_name;


SELECT * FROM table_name WHERE id >= 3;
SELECT * FROM contacts WHERE NOT id >= 5;

UPDATE users SET name = 'Reuben' WHERE id = 2;
DROP TABLE table_name; # From the database that holds the tab
```

- psql commands

- List all databases: \l.
- Exit psql shell: \q
- Connect to database: \c database_name
- List tables in current database: \dt
- Describe a table such as a column, type, modifiers of columns, etc: \d table_name
- List columns in a table: \d table_name
- See a list of all psql commands: \? (Press the down arrow to scroll through, or q to exit list.)
- Execute the last command again : \g
- Display command history: \s
- [More commands](https://www.geeksforgeeks.org/postgresql-psql-commands/)
</ol>




[Go Back to the top](#python-flask-cheatsheet)




[Go Back to the top](#python-flask-cheatsheet)


## Technologies Used

- Python3.8
- Flask
- HTML
- Bootstrap

## License
[MIT License](LICENSE)


## Authors Info
* Email - [Reuben Kipkemboi](https://gmail.com)

[Go Back to the top](#python-flask-cheatsheet)


<p align = "center">
    &copy; 2022 python Flask Cheatsheet
</p>


