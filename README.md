# django-tutorial
Python Django tutorial learning for web development. The project that I'm currently as a Research Assitant for uses Django as web development tool. I'll be writting down notes that I learned here. The notes are mostly summarized after learning tutorial from [here](https://www.youtube.com/playlist?list=PL6gx4Cwl9DGBlmzzFcLgDhKTTfNLfX1IK)

NOTE: "first_django_website" runs on version 1.8.4; "web_django_new" runs on version 2.0.7.

## Concepts
* "App": Django calls every little part as an App, so App is simply a main part of the website. IMPORTANT RULE: each App should do ONE thing (a good criteria is that if you can explain an App in one easy sentence, then it's fine. But if cannot, then it needs to be further broken down).

* About urls.py files. Even though there's just one url.py file after creating the project and other apps, it will be messy if you put all the url links in that one files since there will be tons of url links. So it's a good idea to manually create urls.py under each app directory and then import them in the main urls.py.


## General Syntax
* `django-admin startproject project_name`: it will be needed everytime you start a new Django webpage project. Go to the directory that you want to store all your files and type this to command line. "project_name" can be set to whatever name you want, it's just a container to store all your website files. However, the files inside of the "project_name" folder are fixed

* `python manage.py runserver`: type in after go to the project_name directory and when you can see both of the other project_name directory and manage.py file. This will take you to the development web server so that you can see how your website is going. It shouldn't be the server that you hold your real website on.

* `python manage.py startapp app_name`: enter the directory that you can see the manage.py file and run the command to create a new app.


## Files
* `project_name/manage.py`: the file in the root directory. NEVER EDIT THIS FILE. It allows you to access the database, create users for your websit, etc.

* `project_name/project_name/__init__.py`: you don't need any code in there. This is just telling Python to treat "project_name/project_name" folder as a Python package

* `project_name/project_name/settings.py`: it contains the configuration options for your website.

* `project_name/project_name/urls.py`: it's like a table of contents for your website. Basically it contains the instructions of what functionality should be given to that particular URL. For example, many times an URL will direct you to a new webpage, but sometimes an URL might have the functionality to allow you to log out the webpage. So urls.py file will include the instructions to tell what that URL does.

* `project_name/project_name/wsgi.py`: it stands for "web server gateway interface". It's a special type of web server.

* `project_name/app_name/migrations`: the files in this folder connect all your source code with database

* `project_name/app_name/admin.py`: instead of creating admin functionality yourself, django has already created that for you, allowing you to have all the admin related functionalities

* `project_name/app_name/app.py` (this file is not included in version 1.8.4): similar to settings.py file which is basically configuration or setting file for this app

* `project_name/app_name/models.py`: it's basically a blueprint for your database. It's a template of how you are going to store your data for that app

* `project_name/app_name/tests.py`: where you can create test codes to make sure there's no bugs in your app

* `project_name/app_name/views.py`: it simply just contains python functions which take users' requests and give response in some way


## Python and JavaScript in Django
(The following notes is taken based on the tutorial [here](https://www.youtube.com/watch?v=ZjAMRnCu-84&list=LLJMXf6A4Uv_apa_OjWuxWrw&index=7&t=1544s)

Corresponding notes is [here](https://cs50.harvard.edu/web/notes/7/)

* ` python manage.py shell` lets you print stuff out in the terminal.

* In the `models.py`, printing out each class by default is only an object. To better represent the class, you can use a string representation by adding 
    ```
    def __str__(self):
        return f"{class_attr} blah blah {another_class_attr}"
    ``` 
This defines what the object should look like when print into the terminal or even in html page. (NOTE: this works not only for django classes, but also a regular class)

   * Settings of foreign key: For example, 
      
      `origin = models.ForeignKey(Airport, on_delete = models.CASCADE, related_name = "departures")`
      
      * `on_delete` allows you to choose how classes react when values in related classes change. `on_delete = models.CASCADE` asks system to delete related values if one value changes in one table. 
      * `related_name` allows you to access related class attributes using that name
   * `class_name.objects.first()` prints out the first item in the object
