# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P4：3_项目和应用概述.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

When learning web development， it's important to understand what is required to build a website by now you should be familiar with the basic structure of a website。

 It contains web pages consisting of HTML for the page structure。

 CSS for the look and style and JavaScript for client side interaction。

Suppose you are creating a static website， the project structure may only need some CSS。

 JavaScript and image folders。

![](img/bbec1bc0bb313858e249d272ad557269_1.png)

This approach may work fine for a simple static website。

The purpose of the project structure is to lay out the files in a way that makes them easy to update。

However， when dealing with web applications requiring more complex functionality。

 such as the need to hold state or access and store data， things need to be set up differently。

Using a framework， developers can focus on creating functionality unique to the projects instead of repeating the repetitive coding tasks associated with building a web application。

 Django was created by developers who have followed best practices。

It allows you to set up your web application in a structured way for easier development。

 In this video， you will learn about the core concepts of projects and apps in django and how they provide a structure for a developer to work from。

 Okay so before you explore the structure of the django framework。

 It's good to fully understand what is usually required to create a dynamic web application。

 This can involve working with internet protocols， web server configuration and data retrieval or storage。

 Let's recap these concepts quickly。 regarding internet protocols recall that HtTP is used to get。

 send and render web content。 Under HtTP is essential in web development As every action is always tied into a HtTP request pointing to some URL。



![](img/bbec1bc0bb313858e249d272ad557269_3.png)

![](img/bbec1bc0bb313858e249d272ad557269_4.png)

A web server is required to get the page users want and return it to them via HTTP Django comes with its own development server。

 which is written in Python。 This will save the developer a lot of time and avoid any messy configurations。

Recall that the web is stateless， meaning it does not store anything for future reference。

 so a database is required to keep and retrieve the data associated with the website。



![](img/bbec1bc0bb313858e249d272ad557269_6.png)

For example， every time a user submits a form on a site。

 this data will need to be stored so it can be retrieved and rendered later so now you have learned about how a framework provides a structure for a developer to work from。



![](img/bbec1bc0bb313858e249d272ad557269_8.png)

Let's explore the structure of a Dngle project。

![](img/bbec1bc0bb313858e249d272ad557269_10.png)

In Django， a project represents the entire web application。



![](img/bbec1bc0bb313858e249d272ad557269_12.png)

Jiango provides a set of commands that auto generates a project structure that contains the configuration and setting related to the entire web application。

You will learn more about this project structure later for now。

 just know that it's a way to organize your Python files and folders。



![](img/bbec1bc0bb313858e249d272ad557269_14.png)

This allows developers to focus on code rather than configuration Okay so now you know about projects。



![](img/bbec1bc0bb313858e249d272ad557269_16.png)

Let's learn more about apps。In Django， an app is a sub moduleule of a project。

It is typically used to implement functionality for some specific purpose。Apps can be self contained。

 meaning they do not rely on other apps to function。 As a result。

 they can be used or reused in many different projects。

 This leads nicely to the don't repeat yourself Dr principles right at once， but use it many times。



![](img/bbec1bc0bb313858e249d272ad557269_18.png)

As an aspiring developer in Django， this might seem confusing when you encounter the termsA and apps。

Just remember that a Django web application is a project that contains many apps。For example。

 suppose you are creating a social media application。Well， in Django。

 the social media application would be the project。

 and the different features would be represented by the different apps。

So you could create separate apps for the newsfeed， the comments， the Fris list， the user page。

 and so on Apps are added using the Start app command。



![](img/bbec1bc0bb313858e249d272ad557269_20.png)

And like with a project， Django also automatically generates a self contained directory and its associated files inside the project structure。



![](img/bbec1bc0bb313858e249d272ad557269_22.png)

For Django to recognize an app in a project， it must be added to the installeds apps setting。



![](img/bbec1bc0bb313858e249d272ad557269_24.png)

Additionally， a Django app is a set of code that interacts with various parts of the framework。

There are a few places where Django needs to interact with installed applications。

This is mainly for configuration and introspection。

That's why the application registry maintains metadata in an app config instance for each installed application。

Applications usually include some combination such as models， views， templates， template tags。

 static files， URLs， and middleware。

![](img/bbec1bc0bb313858e249d272ad557269_26.png)

Don't worry if you do not understand all these terms yet。

You learn about them all later in this course。For now， just know that as a developer。

 you will spend a great deal of time working with apps as they contain all the projects's different parts。

And as a developer， deciding what constitutes an app in a project can be subjective。

 and you may encounter various approaches to app design。



![](img/bbec1bc0bb313858e249d272ad557269_28.png)

For now， it's best to think that an app should be feature targeted and is best suited to one thing and one thing only。

And throughout this course you will be working with a project that contains only one app in this video。

 you learned about the core concepts of projects and apps in Django and how they provide a structure for a developer to work from。



![](img/bbec1bc0bb313858e249d272ad557269_30.png)