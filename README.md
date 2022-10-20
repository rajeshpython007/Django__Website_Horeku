# Django__Website_Horeku
A retail B-C website using Python-Django
![image](https://user-images.githubusercontent.com/100021707/195915859-7d75d234-f354-4b0c-ab0b-2a3e484cad84.png)
 
WHY DJANGO-FRAME-WORK?
1.	Fast, Scalable, Secure – Used by perfectionist with deadlines.
2.	Spotify, YouTube, Instagram
WHAT IS THIS DJANGO FRAME_WORK? 
1.	A library having re-usable modules(building blocks) – can be used using 
I]     HTTP-URL
II]   SQL – other database server.
III] HTML
2.	We don’t need to code it from scratch – Everything is inbuilt here.
3.	It defines a structure for application – what folders and files we must have in our project.
4.	It provides consistency as we move to Django various different projects.
STEPS:
1.	Create projects: Pylab
2.	Install Django: pip install Django == 4.0 [@terminal]
3.	Create Django Project: Django-admin startproject pylab .
4.	Pylab => 
I] __init__.py : it’s a package and we can import various modules into other modules.
II] settings : we will define various settings to our applications.
III]Url module: what should the user would see on the webpage.
IV]WSGI module : web server gateway interface : to provide an interface between the webserver and Django web application.
5.	Venv [virtual environment]=> manage.py => we can manage the Django application => with this we can start our web-server, data base etc.
6.	python manage.py runserver [running an argument runserver] => created the link to our address => 127.0.0.1:8000
7.	django project => various function is divided into micro function
 
 
 
So, as these are having completely different functionality. So, better we separate the functionality into different micro level functionality through separate app.

Each app is reusable and can be used anywhere we want.
e.g. we are using same module manage.py with different argument
python manage.py startapp product.

  
Product is a package: w can re-use it in another Django application / project.
We can publish this package to make it available to others to re-use it in their project.
I]  admin.py  : we can set the look of our admin page, how it gonna look like.
II]apps.py     : to store various configuration to our app.
III] models.py : To modelling the concepts in our app => product, category, review, rating, feedback by using various classes.
IV] test.py : we write automated test for this app.
V] view.py  : we define what should the user see when we navigate to certain page.
HOW VIEW WORKS?
Home Page Of Django :
   

When we call a view function products:
 

8.	so, to create the view functionality => open the views.py inside the products app.  

Let’s create our first view function:
I] from django lets import HttpResponse
II]from Django lets import render
III] define a function index on request from client which will return a plain text “Hello Customer” [we can define HTML function too]
 
But to let django to call the function when the user send a request function.
9.	add url pyhton file inside products :
products => New Python File => name it urls [to structure our project]
  
10.	Let’s do the mapping:  Let’s Map URL with view function.
I.	In urls module we must declare module urlpatters = [] {to declare various URLS}
II.	To declare URLS we must import the PATH function. – blank string
 
III.	We need to import the view: from . import views [. :is current folder] and let’s pass the views index.
 

11.	Let’s go to the root URL => under Pyshop folder => URLs.py
By default we found : 
 
So, we are telling Django wherever the admin is in url go to the URL: admin.site.urls.
12.	Let’s introduce some more keywords to Django to make our work easier :
I]  Let’s import include module into url [under Pyshop folder => URLs.py ]
II] Now, we can use the INCLUDE module and write :
 

13.	Let’s define new text when the user goes to the new products section.
products => views.py 
 
14.	We need to map the same in urls:
 
Now let’s test our new command that is – new product.
 
15.	Let’s Create new models: Pylab => products => models.py
I]  import models module from Django.db package, in this models module we have a class called Model. This class defines all the common characteristics in django : delete / add / read from data base.
II] by inheriting this product class from the Model class – our Product class will have all the objectivity of Model class. We don’t need to code it from scratch.
 
III] Lets add some more attribute with 
name : charfield(max_length = 255) class, 
price: floatfield() class.
stock: integerfield() class 
& image_url : CharField(max_length=2083) class.
 
16.	Migration:
Terminal –> python manage.py makemigration.
 ERROR: no changes detected.

To Mitigate,
 Pyshop => setting.py => line33 => installed_Apps
 
Lets add PRODUCTS APP into the installed Apps: 
When we go to the apps.py we found the class ProductsConfig so lets add the same into the installed apps. => products [package]. Apps[module]. ProductsConfig [Class]
 
Now, Django knows about the product apps.
Now, If we run the same makemigration command.
 
New file created i.e. 0001 initial.py => initial migration
 
 
Let’s dive into it : 
New database table Product has created automatically Id, Stock, Name, Image_URL
 





17.	But, the new database has not yet migrated to our database. 
 

18.	Let’s migrate it. 
 
19.	Now. Lets import the data base from our local drive into SQLite and check the content of database.
 
20.	Let’s Create an offer class  having below features :
 

PyLab=>products=>models
 
Let’s makemigration the new change i.e offer:
 
Let’s migrate the same:
 
Now. Again import the new_data into our sqlite.
 
 
21.	Built-In Autogenerated : Admin interface.
 

22.	To create the Id and Password here. 
 
23.	 
We need to add the products column in this admin page.
Products => admin.py => 
 
We are importing the admin, the admin has an object site and an attribute register.
We are calling this method and passing Product class as an argument.
24.	To add the name, price, stock to the product on our webpage.  
25.	To add offer model to our website.
 
26.	HTML Templates:
Create File :
 
Create New HTML file:      
	Rendering THE objects into the template:
 
Embedding the rendered objects into HTML code:
   
27.	Creating Cards : 
https://getbootstrap.com/docs/4.1/components/card/
Starter template: copy the code 
Create the base.html file and paste the code.

Card Title : copy the code
 Paste the code in base.html 
And make some changes in index.html : <div class="row">
    {% for product in products %}
      <div class="col">
 By this command, We are creating multiple columns in a row.
28.	Creating Navigation bar: 
https://getbootstrap.com/docs/4.1/components/navbar/




	
















