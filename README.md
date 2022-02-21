# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Desing your website for calculation using wireframe work.



### Step 2:
Then to execute the wireframe work desing use html,css



### Step 3:
Use views.py to execute the coding in serverside.


### Step 4:
Mention the path of the website in urls.py.


### Step 5:
Publish the website in the given URL.
<br/>
http://vinuthna.student.saveetha.in/

## PROGRAM :
### HTML PAGE :
```
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Area</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
    <style>
        .container{
            display:block;
            width:1080px;
            height:600px;
            margin-right: auto;
            margin-left: auto;
            background-color: aqua;
        }
        h1{
            text-align: center;
            font-size: larger;
        }
        .content{
            display:block;
            background-color: rgb(100, 218, 163);
            text-align: center;
            height: 200px;
            padding-top: 10px;
            margin-left: 100px;
            margin-right: 100px;
            font-size: x-large;
        }
        .content2{
            display:block;
            background-color: rgb(186, 55, 212);
            text-align: center;
            height: 265px;
            padding-top: 10px;
            margin-left: 100px;
            margin-right: 100px;
            font-size: x-large;
        }
        footer{
            display:block;
            text-align:center;
            background-color: burlywood;
            font-size:xx-large;
            text-decoration: darkblue;
            padding-top: 50px;
            margin-top: 50px;
            margin-left: 100px;
            margin-right: 100px;


        }
    </style>
</head>
<body>
    <div class="container">
        <h1>SERVER SIDE PROCESSING</h1>
        <h1>CALCULATION</h1>
        <div class="content">
            <h1>AREA OF A RECTANGLE</h1>
    <form method="POST">
            {% csrf_token %}
        LENGTH=<input type="text" name="length" value='{{l}}'></input> <br/>
        BREADTH=<input type="text" name="breadth" value='{{b}}'></input> <br/>
        <input type="submit" value="calculateArea"></input><br/>
        Area=<input type="text" name="area" value='{{area}}'></input>`<br/>
    </form>
         
</body>
</html>

```
### VIEWS.PY Page:
```from django.shortcuts import render

# Create your views here.

def areacalculation(request):
    context = {}
    context["area"]="0"
    context["l"]="0"
    context["b"]="0"

    if request.method == "POST":
        l = request.POST.get("length","0")
        b = request.POST.get("breadth","0")
        area = int(l) * int(b)
        context["area"] = area
        context["l"] = l
        context["b"] = b
    return render(request,"mathapp/area.html",context)
```
### URL page:
```
from django.contrib import admin
from django.urls import path
from mathapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaofrectangle/',views.areacalculation,name="areaofrectangle"),
    path('',views.areacalculation,name="areaofrec")
]
```

## OUTPUT:

### calculation Page:
![output](111.png)



## Result:
Thus, a website to perform mathematical calculations in server side is created.

