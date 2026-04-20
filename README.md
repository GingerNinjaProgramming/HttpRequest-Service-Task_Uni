# HttpRequest-Service-Task_Uni

---

## Introduction

In this task, I was tasked to create an online service, tool or utility, utilizing PythonAnywhere, Render, or Oracle Cloud. You may alternatively choose to do this locally. Your outcome should demonstrate communication with an Unreal project using one or more of the following:

* HTTP request
* Delegates
* JSON
* CSV
* Data Tables
* Data Assets

My approach to this was to go for the Http request for a locally running python app on my PC and learning how to create a app though python and be able to request information from it from unreal.

This task is important as it gives me an avenue to learn how to request external data into unreal engine which can be used in games for things like leaderboards. Along with this it allows me to learn how to make a flask app though python which can be used to host things like leaderboards instead of something like SQL if needs be.

---

## 2. Implementation 

```py
import datetime
from dataclasses import dataclass
import flask

app = flask.Flask(__name__)

@app.route('/')
def home():
    return "This is my test flask app"
@app.route('/date', methods = ['GET'])
def date():
    return str(datetime.datetime.now())

if __name__ == '__main__':
    app.run(debug=True)


```

This tasks implementation included first making a basic flask app on python. This was done by first importing flask into python using "pip install flask" and then importing flask into the python script. Once imported you can use the flask library to create a instance of flask cached in the variable app that can then be used to interact with the system.

Then to tie a function to a Http request in the flask app above any function any function you can put the flask decorator:

```py
@_FLASK-VARIABLE_.route('_HTML_')
```

This allows a function to be tied to a certain HTML. In this configuration this will just display whatever it gets on the URL.

![](https://file.garden/aSY-yx_ZmANpQe1l/UniTasks/TestFlaskTex.png)


Now to be able to use this flask app to access data from the python side of things you need to add some more parameters onto the decorator above a function this being "Methods = []" this can include many different type of requests that you may want to make. For the purposes of this project you can use this to make a "GET" request. Now if you put a return parameter inside the function it will be returned when this request is fired.

```py
@app.route('/date', methods = ['GET'])
def date():
    return str(datetime.datetime.now())
```

For the purposes of this project I went for using the date time libary to send whatever date and time it is at that current time putting that under the "/data" html. 

![](https://file.garden/aSY-yx_ZmANpQe1l/UniTasks/TestFlaSKdATE.png)

Then after all of this and ensuring its running on my system on a local port I can access (5000 being one of the defaults for local flask development).

![](https://file.garden/aSY-yx_ZmANpQe1l/UniTasks/HTMLUnreal.png)

I can now refer to this html in unreal using the HTML extension in unreal engine and return whatever the date time is as a string that then gets set to a text UI element for easier visibility

---

## Outcome

The final result is a unreal widget that can access information from an external flask app that transmits the exact date and time as provided by the datetime python library.

In this task I have been able to create an html service hosted locally and then used that to make a html request that then sent data to unreal that was then presented in a obvious and readble qay

[Demonstration video:](https://file.garden/aSY-yx_ZmANpQe1l/UniTasks/ItworkingVideo.mp4)

---

## Bibliography

Unreal Engine 5.7 Documentation | Unreal Engine 5.7 Documentation | Epic Developer Community (s.d.) At: https://dev.epicgames.com/documentation/en-us/unreal-engine/unreal-engine-5-7-documentation (Accessed  03/12/2025).

Simple HTTP GET request within a Blueprint - Unreal Engine 5 Tutorial (2023) Directed by Geert Verhoeff - Tutorials. At: https://www.youtube.com/watch?v=Ln1Dk2pF2Bg (Accessed  20/04/2026).

---

## AI Usage Declaration

Chatgpt - Code generation for basic flask implementation before editing

