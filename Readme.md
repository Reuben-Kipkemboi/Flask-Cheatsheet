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


