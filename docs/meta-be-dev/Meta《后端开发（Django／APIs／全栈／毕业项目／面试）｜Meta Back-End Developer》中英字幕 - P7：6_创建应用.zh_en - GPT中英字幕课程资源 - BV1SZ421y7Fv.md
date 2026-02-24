# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P7：6_创建应用.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

So far you've learned that a project represents the entire web application and an app acts like a submodule of the project to provide specific functionality。

Previously， you' set up the project folder and created the virtual environment inside it。

In this video， you'll learn how to create an app inside an existing Django project。

The app will contain a view to output some text to the homepage of the web application。



![](img/44b07fd9746ef4119b66cc42b5dc69a1_1.png)

So I'm NVS code with the project open first I need to create a Django app for my project and for this I use the start app command。

So I type Python M Djago start app。Then I need to give this app a unique name。

 so I'll call it something like my app。Before I move on。

 let's explore the structure of the startup command in a little more detail。

The Start command has a default syntax where you need to provide the app label and then you have the option to specify the destination。

Suppose you do not specify any destination， like in this example， in that case。

 the default destination of the current working directory is used。Okay， so my command looks good。

 so I press enter to execute it。Notice that a folder called My app is created inside the project folder if I expand the folder。

 you will notice that it contains some files for init， admin， models， tests and views。

If you're new to web frameworks and Django， I know that this can seem a bit intimidating Aly。

 the project contains folders with many different files and I haven't even started coding yet。

 Don't worry if you don't understand fully what every file and folder does It's more important to focus on the concept that you need to create apps to add different features to a project As this project has just one feature to print some text to a web page I've created one app to do this Okay。

 so now that I've created an app I want to output some text to the home page and to do this I need to work with Djago elements called routes and views When the user visits the applications homepage。

 I want to display some text。In Django， when the user navigates to a URL。

 the URL is routed to something called a view or controller。

For now you can just think of views as Python functions that generate the content that makes up the web page。

 they can receive a request and return a response。And because this request and response will take place over the web。

 it'll use two objects called HTTP request and HTTP response Once again。

 don't worry if you don't understand all of this you'll learn more about routes。

 views HTTP requests and responses later。For now， just know。

 this is what you need to use for Dngo to display some dynamic text on a web page。 Okay。

 so first I want to create the view function， I open the file view Pi in the app folder and notice that it already contains some code。

It's a good idea for now not to modify the code that's automatically created by Django。

 I just need to add to it。Okay， so I've added three lines of code， let's explore it now。

The first line is an import statement which is required for the request response to work。

Then the code to create a function named home。This function returns an HTTP response object containing the text。

Hello world。It's important to know that creating the function that returns an HTTP response will not do anything on its own。

This is just the logic that will be executed when a user goes to the project's homepage。

So to make this work， I need to map the view function to a URL。

The URLs you will use in your Django project are stored as a URL configuration in a file called URL dopi。

 which is located in the project directory， The Django documentation or your fellow developers may also refer to this as URL Comf。

You will also explore the concept of URL configuration and its code in more detail later。For now。

 just know that it acts like a mapping chart that Django uses to determine which view functions are associated with a specific URL。

If I open this file， I notice already contains some code by default。For example。

 some import statements from the Co Django package and a list labeled URL patterns。

So it's in this file that I need to add the code to map the URL of the homepage to its corresponding view function。

First， I import the view file by typing from my app import and then View file from that app。



![](img/44b07fd9746ef4119b66cc42b5dc69a1_3.png)

Next， I need to add the file path to the list， so let me copy and pasteline 22 and edit it。

I want the view function to execute on the home page so I can just replace the word admin with an empty string。

Next， I need to specify the view function so let's change this to views。

 home and add a name such is home。You can think of name as an attribute used for naming the URL patterns which can be useful sometimes。

Okay， so my code looks good now all I need to do now is save my changes and run the development server。

 recall that I use the command run server to run the development server。

So you type the command Python， manage。 Pi run server。

Notice that the development server starts at the default IP address。

 which can also be called Local host on your device。

You will also likely receive a warning message stating that you have unapplied migrations。

 and Django gives you a command to run to fix this warning。I'm not going to do that right now。

 but don't worry， you'll learn how to do this when you explore migrations later in this course。

Success if I open the web page at the default address， notice that the text Hello world displays。

 this text is returned as an HTTP response from the view。



![](img/44b07fd9746ef4119b66cc42b5dc69a1_5.png)

If I change this， let's say remove the word world and resa， check the webage， refresh it。

 notice that the page gets updated again。

![](img/44b07fd9746ef4119b66cc42b5dc69a1_7.png)

It's important to know that while the content of the view is quite basic。

 this is the process by which every web page uses Django to create and update content in this video。

 you learn how to create an app inside ci an existing Django project containing a view to output some text to a webp page。



![](img/44b07fd9746ef4119b66cc42b5dc69a1_9.png)

![](img/44b07fd9746ef4119b66cc42b5dc69a1_10.png)