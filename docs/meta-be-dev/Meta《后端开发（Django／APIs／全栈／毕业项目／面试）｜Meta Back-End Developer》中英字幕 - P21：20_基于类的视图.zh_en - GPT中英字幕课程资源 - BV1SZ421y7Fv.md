# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P21：20_基于类的视图.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Organizing your code in a clean and easy to use manner is essential when working on a project。

As the project grows， keeping code organized and well structured can be a challenge for developers to help overcome these challenges。

 developers often use frameworks and design patterns such as MVT。For example。

 with the Jngle framework， you can use views to present data to the end users。

You have already learned that you can respond to a web request in Django by creating a view function to return data using the HTTP response object。

In the background， the framework passes that HTTP request to your function。

 expecting the HTTP response back。

![](img/5e674d5865ec8dad951145d38d3e5359_1.png)

While this works for some use cases， developers often need a more robust solution for implementing more complicated application logic in a view。

To help with this， Django provides something called a class based view。



![](img/5e674d5865ec8dad951145d38d3e5359_3.png)

In this video， you will learn about the concept of class based views。

You will also explore how developers can simplify their views by using object oriented techniques。

 such as the concept of inheritance to create views from inherited classes。

Let's begin by exploring some of the features of class based views。

Class based views allow you to use views as objects and offer an alternative to function based views。

Remember that a view is callable in that it can take a request and return a response。

This process works great for the HTTP protocol。When dealing with HTTP。

 you use specific methods for the different types of requests such as get， post， Po， and deletete。

And these are the core crude operations for any webpage。



![](img/5e674d5865ec8dad951145d38d3e5359_5.png)

If you use a function based view， you need to perform some conditional logic on the request method。

 like an if else statement。

![](img/5e674d5865ec8dad951145d38d3e5359_7.png)

But class based views uses a different approach than function based views instead of using conditional branching such as if else statements。

 class based views respond to HTTP requests using class instance methods。

Instance methods are default Python methods defined in classes that can access objects or instances of a class。



![](img/5e674d5865ec8dad951145d38d3e5359_9.png)

In a class based view， this can be simplified by adding different instance methods for the get and post requests。

And these methods will implement the view logic independently。😊。

Class based views respond with different class instance methods to HTTP requests in place of writing conditional branches such as using F statements inside the same function。

The advantage of using a class based view in this scenario is that it allows you to remove the conditional logic to check the incoming request for the type of method。

This simplifies the code and separates the logic， making it easy to understand。

Another helpful aspect is the ability to have object oriented techniques such as mix ins or multiple inheritance。

 which factor code into reusable components。In Django。

 you can extend the functionality of class based views using mixings。

Mix ins are class based generic views that are flexible compared to their function based view equivalent。

It can help to think of a mixing as a form of multiple inheritance。😊。



![](img/5e674d5865ec8dad951145d38d3e5359_11.png)

Recall that inheritance is one of the core concepts of object oriented design， our OOP。

It allows you to derive one class from another for a hierarchy of classes with similar attributes。



![](img/5e674d5865ec8dad951145d38d3e5359_13.png)

For example， suppose you have a class called Food。Other classes that can inherit from this class could be appetizers。

 entree， and desserts。They are all types of food and would share a lot of common attributes。

Some common mixings developers use are create， list， retrieve， update， and delete。

Let's explore these briefly now。😊，Use Create to create a model instance。Use L to list a query set。

Use retrieve to retrieve a model instance。Use update to update a model instance。

And use delete to delete a model instance。It's important to note that when using mixins。

 they can't be all used together。And in some cases， it can make your code harder to read。

 so it's best to use them wisely。

![](img/5e674d5865ec8dad951145d38d3e5359_15.png)

In this video you learned about the concept of class based views。

 you also explored how developers can simplify their views by using object oriented techniques。

 such as the concept of inheritance to create views from inherited classes。

