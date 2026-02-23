# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P11：10_视图.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

If you are building a basic static website， all you need to do is upload your website files to a web server。

 however， if you are building a dynamic website using a framework。

 you may need to get or retrieve data and render it to the browser this data could be anything like the user's name or a list of information。

In Django you use something called a view to create the logic to present data to the end users In this video。

 you will learn about views in Django and how developers use them to process HTTP requests and return an HTTP response in Django。

 a view is a function designed to handle a web request and return a web response such as an H document。



![](img/326ac432ff421292e15325ee1eac5c76_1.png)

![](img/326ac432ff421292e15325ee1eac5c76_2.png)

![](img/326ac432ff421292e15325ee1eac5c76_3.png)

To demonstrate this， let's explore an HTTP request response scenario using an example of a static file and a dynamic file。

For a static file with no dynamic content， the HTTP request just needs to map to where the file is located and return that page for rendering as the static page does not change。

 nothing else is needed。

![](img/326ac432ff421292e15325ee1eac5c76_5.png)

Suppose the page is at the address of littlelemon。com forward/index。htm。



![](img/326ac432ff421292e15325ee1eac5c76_7.png)

The web server would process the request and return a response containing the page index。

htm to the browser， which then renders the content。



![](img/326ac432ff421292e15325ee1eac5c76_9.png)

![](img/326ac432ff421292e15325ee1eac5c76_10.png)

You may recall that this process is known as the HTTP Re response cycle， however。

 if you want to do the same thing with Django， you need to write a Python function to create something called a view。



![](img/326ac432ff421292e15325ee1eac5c76_12.png)

You create the function inside the views。pyy file and return the HTML。



![](img/326ac432ff421292e15325ee1eac5c76_14.png)

Let's explore this concept further now and step through the code one line at a time First。

 you import the class HtTP response from the Django dot HttP module Next you define a function called home。

 and this is known as the view function each view function takes an HtTP request object as its first parameter named Re。

As this is a Python function， it's possible to define more parameters and pass arguments and you will learn about that later in this course。

It's important to know that the name you give the view function doesn't matter。

The function doesn't need to be named in a certain way for Django to recognize it。

In this example it's called home because defining a function name that clearly indicates what the function does is good practice Next。

 you create a variable and use it to store a string containing the HTML to be returned Once again you can name this variable anything you want In this example it's called content。

Finally， you need to return this variable containing the code and you do this by using the return statement with the HTTP response object。

Inside the HTTP response， you place the variable， you can also perform other programming logic inside of view functions。

 such as processing data for emails and forms， retrieving data from a database， transforming data。

 and rendering templates。

![](img/326ac432ff421292e15325ee1eac5c76_16.png)

![](img/326ac432ff421292e15325ee1eac5c76_17.png)

It's important to know that you create view functions inside the viewss。pyy file as a best practice。

You can theoretically name the file anything that you like。

 but it is a good practice to keep it as views。pyy as it makes it easier for your fellow developers working on the same project。

😊，It's important to note that creating a view function is not enough to make the request response work。

The view function needs to be mapped to a URL， so when the request to the URL is made。

 the view function gets called。

![](img/326ac432ff421292e15325ee1eac5c76_19.png)

This process of mapping a URL to a view function is known as routing。



![](img/326ac432ff421292e15325ee1eac5c76_21.png)

To set up this routing to map URLs to views， you will need to create a new file inside your project app。

 create a new file called URLs。pyy。You may recall that the project has a file with this name also。

 you will learn about the difference between them later。



![](img/326ac432ff421292e15325ee1eac5c76_23.png)

Inside the URLs。pyy file of the app， you first import the path function。Then。

 from the app directory you import the viewss。pyy file notice that both files are in the same directory。

 you only need to place the period symbol after the import statement Next to create a route and map a URL to a view。

 you need to create a list sequence using the variable URL patterns。

This variable is assigned to a list that contains the URL paths that you want to create inside the app。

The URL Pat list can contain multiple paths， and each path is created using the path function。

 the function can accept arguments and two are required。The first argument is the route。

 which is a string that contains a URL pattern， and the second argument is the view。

 which contains the relative path and the name of the view function。In this example。

 the view function is called for the homepage of the app， so for now it's set to an empty string。

You will learn more about how to populate the route argument with URLs represented as strings later in this video you learned about views and view functions and how developers use them to process HTTP requests and return an HTTP response。



![](img/326ac432ff421292e15325ee1eac5c76_25.png)

You also learned that view functions are mapped to URLs using the path function in the URLs。

pyY file of the app。