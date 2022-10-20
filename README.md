# Django__Website_Horeku
A retail B-C website using Python-Django
![image](https://user-images.githubusercontent.com/100021707/195915859-7d75d234-f354-4b0c-ab0b-2a3e484cad84.png)
 
WHY DJANGO-FRAME-WORK?
	Fast, Scalable, Secure – Used by perfectionist with deadlines.
        Websites such as Spotify, YouTube, Instagram are created by it.


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
 ![image](https://user-images.githubusercontent.com/100021707/196840180-f6675dc6-bbe5-4c51-90b8-fe886c618105.png)
![image](https://user-images.githubusercontent.com/100021707/196840216-ca6adb18-0cbe-499e-a4f1-b22f339c160f.png)
![image](https://user-images.githubusercontent.com/100021707/196840237-85f1de55-2e94-403d-8212-dc785721515c.png)
So, as these are having completely different functionality. So, better we separate the functionality into different micro level functionality through separate app.

Each app is reusable and can be used anywhere we want.
e.g. we are using same module manage.py with different argument
python manage.py startapp product.
![image](https://user-images.githubusercontent.com/100021707/196840297-091ba5e7-6e00-4850-83e7-d2095109c400.png)

Product is a package: w can re-use it in another Django application / project.
We can publish this package to make it available to others to re-use it in their project.
I]  admin.py  : we can set the look of our admin page, how it gonna look like.
II]apps.py     : to store various configuration to our app.
III] models.py : To modelling the concepts in our app => product, category, review, rating, feedback by using various classes.
IV] test.py : we write automated test for this app.
V] view.py  : we define what should the user see when we navigate to certain page.

HOW VIEW WORKS?
Home Page Of Django :
![image](https://user-images.githubusercontent.com/100021707/196840349-9cf10c15-4987-4821-9d72-87b61da8332f.png)
When we call a view function products:
![image](https://user-images.githubusercontent.com/100021707/196840387-c99578a9-fc19-432e-93c8-c363342c2596.png)

8.	so, to create the view functionality => open the views.py inside the products app.  
![image](https://user-images.githubusercontent.com/100021707/196840432-0d6136d3-b3e5-4141-85fd-3e836f2d1a97.png)

Let’s create our first view function:
I] from django lets import HttpResponse
II]from Django lets import render
III] define a function index on request from client which will return a plain text “Hello Customer” [we can define HTML function too]
![image](https://user-images.githubusercontent.com/100021707/196840473-11f4820a-39e2-46a7-b0e4-81ae5f9a6827.png)
 
But to let django to call the function when the user send a request function.
9.	add url pyhton file inside products :
products => New Python File => name it urls [to structure our project]
  ![image](https://user-images.githubusercontent.com/100021707/196840510-27662218-059f-4280-a992-88a5537bb4fb.png)

10.	Let’s do the mapping:  Let’s Map URL with view function.
I.	In urls module we must declare module urlpatters = [] {to declare various URLS}
II.	To declare URLS we must import the PATH function. – blank string
 ![image](https://user-images.githubusercontent.com/100021707/196840533-e63f9184-dbf9-450e-90cb-5500479e4a3c.png)

III.	We need to import the view: from . import views [. :is current folder] and let’s pass the views index.
![image](https://user-images.githubusercontent.com/100021707/196840549-b3373c2d-1330-4c03-b5f9-2e40ccefc392.png)
 
11.	Let’s go to the root URL => under Pyshop folder => URLs.py
By default we found : 
 ![image](https://user-images.githubusercontent.com/100021707/196840596-edc5458b-3361-4881-844b-7c8b82904ffb.png)

So, we are telling Django wherever the admin is in url go to the URL: admin.site.urls.
12.	Let’s introduce some more keywords to Django to make our work easier :
I]  Let’s import include module into url [under Pyshop folder => URLs.py ]
II] Now, we can use the INCLUDE module and write :
 ![image](https://user-images.githubusercontent.com/100021707/196840626-7869b264-25c6-4237-a647-58bd2d3d7477.png)


13.	Let’s define new text when the user goes to the new products section.
products => views.py 
 ![image](https://user-images.githubusercontent.com/100021707/196840635-ed2ce828-7945-4b09-8af4-bca05a4a81e0.png)

14.	We need to map the same in urls:
 ![image](https://user-images.githubusercontent.com/100021707/196840666-0fcac2aa-477c-4a03-b4b5-9e707edccf9a.png)

Now let’s test our new command that is – new product.
 ![image](https://user-images.githubusercontent.com/100021707/196840707-541f3d7d-46d7-407c-8b39-db8526e9cb2d.png)

15.	Let’s Create new models: Pylab => products => models.py
I]  import models module from Django.db package, in this models module we have a class called Model. This class defines all the common characteristics in django : delete / add / read from data base.
I![image](https://user-images.githubusercontent.com/100021707/196840752-2312d4dd-6003-4d21-aad3-6865e0c853c1.png)
I] by inheriting this product class from the Model class – our Product class will have all the objectivity of Model class. We don’t need to code it from scratch.
 
III] Lets add some more attribute with 
name : charfield(max_length = 255) class, 
price: floatfield() class.
stock: integerfield() class 
& image_url : CharField(max_length=2083) class.
 ![image](https://user-images.githubusercontent.com/100021707/196840777-d80603d4-3c8e-4c61-8f14-c08de66bb461.png)

16.	Migration:
Terminal –> python manage.py makemigration.
 ERROR: no changes detected.

To Mitigate,
 Pyshop => setting.py => line33 => installed_Apps
 ![image](https://user-images.githubusercontent.com/100021707/196840821-6e5ac677-5af2-4886-83a5-5ee7bef0ce9d.png)

Lets add PRODUCTS APP into the installed Apps: 
When we go to the apps.py we found the class ProductsConfig so lets add the same into the installed apps. => products [package]. Apps[module]. ProductsConfig [Class]
 ![image](https://user-images.githubusercontent.com/100021707/196840919-db2ad144-3f29-4a4f-8e32-e493b27f65aa.png)

Now, Django knows about the product apps.
Now, If we run the same makemigration command.
 ![image](https://user-images.githubusercontent.com/100021707/196840933-e13ffc6b-e8af-4632-b793-480fe491c6c4.png)
![image](https://user-images.githubusercontent.com/100021707/196840946-6f34bc9d-92c9-47a0-893a-b68019b4e2f7.png)

New file created i.e. 0001 initial.py => initial migration
 ![image](https://user-images.githubusercontent.com/100021707/196840968-da94cbda-7aac-425c-8d86-1e8f9435da66.png)

 
Let’s dive into it : 
New database table Product has created automatically Id, Stock, Name, Image_URL
![image](https://user-images.githubusercontent.com/100021707/196841002-53d0cd6a-5895-4242-a698-0b180d5728f3.png)

17.	But, the new database has not yet migrated to our database. 
 ![image](https://user-images.githubusercontent.com/100021707/196841051-6f362776-7695-4f89-b170-b25c25c9c85e.png)

18.	Let’s migrate it. 
 ![image](https://user-images.githubusercontent.com/100021707/196841081-e0adde9a-2e9a-4fdc-874a-554fa32c8e82.png)

19.	Now. Lets import the data base from our local drive into SQLite and check the content of database.
 ![image](https://user-images.githubusercontent.com/100021707/196841110-f231a3ed-c26f-4531-ac41-af2608f30c95.png)

20.	Let’s Create an offer class  having below features :
 ![image](https://user-images.githubusercontent.com/100021707/196841141-5c15ea82-78d7-49d0-b4fa-4115273488e5.png)


PyLab=>products=>models
 ![image](https://user-images.githubusercontent.com/100021707/196841172-3622848e-bab8-4777-91b5-3bd2ebf309e9.png)

Let’s makemigration the new change i.e offer:
 ![image](https://user-images.githubusercontent.com/100021707/196841183-c8ca82c4-3c64-4bd2-82fa-c83c1c8c2dc7.png)

Let’s migrate the same:
![image](https://user-images.githubusercontent.com/100021707/196841209-650fff7a-399c-4416-87e7-077f4cd0b1cd.png)
 
Now. Again import the new_data into our sqlite.
![image](https://user-images.githubusercontent.com/100021707/196841299-34c800c7-25e0-4bf1-a934-de116bb39e37.png)
 ![image](https://user-images.githubusercontent.com/100021707/196841312-68533223-9120-4c37-b87e-002269fe4613.png)

 
21.	Built-In Autogenerated : Admin interface.
 ![image](https://user-images.githubusercontent.com/100021707/196841346-74c255ce-9ecd-4b9f-9350-e2532fa530d9.png)


22.	To create the Id and Password here. 
 ![image](https://user-images.githubusercontent.com/100021707/196841365-47fa9ebf-ff28-424b-8ba2-ad1e13edd61c.png)
![image](https://user-images.githubusercontent.com/100021707/196841422-92c7ff16-19a5-4d1b-bf1a-36deca767f9c.png)

23.	 
We need to add the products column in this admin page.
Products => admin.py => 
 ![image](https://user-images.githubusercontent.com/100021707/196841446-0e2305c4-d0fe-43ab-95fa-d3a2d16828ca.png)

We are importing the admin, the admin has an object site and an attribute register.
We are calling this method and passing Product class as an argument.
24.	To add the name, price, stock to the product on our webpage.  ![image](https://user-images.githubusercontent.com/100021707/196841560-83a2b33f-a24d-4d95-adc0-fa9c5b220f27.png)

25.	To add offer model to our website.
 
26.	HTML Templates:
Create File : 
 
Create New HTML file:     
![image](https://user-images.githubusercontent.com/100021707/196841873-dee4e8e7-9b62-42a6-bbb1-627c6a06d1d6.png)

Rendering THE objects into the template:
 ![image](https://user-images.githubusercontent.com/100021707/196841887-d19e038f-ceab-4467-90bb-b539c70c67b0.png)


Embedding the rendered objects into HTML code:
   ![image](https://user-images.githubusercontent.com/100021707/196841926-3fab4066-3a82-41e2-ba30-7591e6ab31e6.png)

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




	
















