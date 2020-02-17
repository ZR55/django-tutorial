# django-tutorial
Python Django tutorial learning for web development. The project that I'm currently as a Research Assitant for uses Django as web development tool. I'll be writting down notes that I learned here. The notes are mostly from [here](https://www.youtube.com/playlist?list=PL6gx4Cwl9DGBlmzzFcLgDhKTTfNLfX1IK)

NOTE: "first_django_website" runs on version 1.8.4; "web_django_new" runs on version 2.0.7.


## Syntax
* `django-admin startproject project_name`: it will be needed everytime you start a new Django webpage project. Go to the directory that you want to store all your files and type this to command line. "project_name" can be set to whatever name you want, it's just a container to store all your website files. However, the files inside of the "project_name" folder are fixed

* `python manage.py runserver`: type in after go to the project_name directory and when you can see both of the other project_name directory and manage.py file. This will take you to the development web server so that you can see how your website is going. It shouldn't be the server that you hold your real website on.


## Files
* `project_name/manage.py`: the file in the root directory. NEVER EDIT THIS FILE. It allows you to access the database, create users for your websit, etc.

* `project_name/project_name/__init__.py`: you don't need any code in there. This is just telling Python to treat "project_name/project_name" folder as a Python package

* `project_name/project_name/settings.py`: it contains the configuration options for your website.

* `project_name/project_name/urls.py`: it's like a table of contents for your website. Basically it contains the instructions of what functionality should be given to that particular URL. For example, many times an URL will direct you to a new webpage, but sometimes an URL might have the functionality to allow you to log out the webpage. So urls.py file will include the instructions to tell what that URL does.

* `project_name/project_name/wsgi.py`: it stands for "web server gateway interface". It's a special type of web server.
