# Meta《后端开发（Django／APIs／全栈／毕业项目／面试）｜Meta Back-End Developer》中英字幕 - P41：40_模板.zh_en - GPT中英字幕课程资源 - BV1SZ421y7Fv

Web frameworks often need to generate dynamic content to render on web pages。

 and because Django is a web framework， it provides a convenient way to generate HTML dynamically。

Dynamic content is any data that changes according to context， user behavior， and preferences。



![](img/fa777cc2762080537915e24784c618c9_1.png)

Developers can use dynamic content and rendering to produce static HTML code。



![](img/fa777cc2762080537915e24784c618c9_3.png)

The most common approach for developers is to use templates。



![](img/fa777cc2762080537915e24784c618c9_5.png)

In this video， you will learn how to use templates in Django。

 you will also explore the concept of the Django template engine and the Django template language。



![](img/fa777cc2762080537915e24784c618c9_7.png)

Templates are text based documents， or Python strings marked up using the Django templatelate language。

 or DTL for short。

![](img/fa777cc2762080537915e24784c618c9_9.png)

Templates consist mainly of two types of content， the first is static。

This is the HTML that does not change on the webpage。The second is template language；

 this is the syntax that allows you to insert dynamic data。



![](img/fa777cc2762080537915e24784c618c9_11.png)

Let's explore an example of creating a HTML heading element using dynamic content。In this example。

 the variables， dish name and price are placed within the double curly braces。

These variables represent dynamic content。The remaining content， including the HTML heading tags。

 is static。

![](img/fa777cc2762080537915e24784c618c9_13.png)

It's important to understand that the static part defines the structure and layout of the page。



![](img/fa777cc2762080537915e24784c618c9_15.png)

And a view using the render function handles the processing of the dynamic content。



![](img/fa777cc2762080537915e24784c618c9_17.png)

You may recall that the render function takes three parameters， request， path。

 and a dictionary of variables。

![](img/fa777cc2762080537915e24784c618c9_19.png)

When you pass the dictionary object to the render function。

 the process of rendering replaces variables present with their values which are looked up in the context。



![](img/fa777cc2762080537915e24784c618c9_21.png)

While you use template language to render dynamic content。

 the concept of a template is what makes up the presentation layer of the MVT architecture。

This helps in the separation of logic because templates handle the user interface logic of a web page。

It's important to know that the dynamic content inside the static HTML is written so Django can understand the syntax and formatting。



![](img/fa777cc2762080537915e24784c618c9_23.png)

![](img/fa777cc2762080537915e24784c618c9_24.png)

Python is a dynamic object oriented programming language， while HTML is a static marker language。



![](img/fa777cc2762080537915e24784c618c9_26.png)

To bridge this gap， Django makes use of the Django template engine and the Django template language。

 or DTL is the language used for adding dynamic content。



![](img/fa777cc2762080537915e24784c618c9_28.png)

DTL can contain embedded dynamic content， such as Python code and variables that the template engine processes。



![](img/fa777cc2762080537915e24784c618c9_30.png)

DTL consists of constructs such as variables， tags， filters， and comments。



![](img/fa777cc2762080537915e24784c618c9_32.png)

Each construct has a specific syntax that helps Djangle understand the code logic。For example。

 you can use tags and comments to build a for loop to display list item elements。

The tags map the dictionary values from the context and helps to add logic to the template。

You will learn more about each of these later in the lesson， Additionally。

 Dnangle also provides an API for loading and rendering templates。



![](img/fa777cc2762080537915e24784c618c9_34.png)

You define the configuration settings for the template engine inside Settings。

pi under the project directory。It's important to note that the app directory setting must be set to true。

This setting tells Django where to search for templates。For example。

 search inside is subdirecty named templatelates for each application in the project。

You can also add specific locations inside the directory setting for Djangle to search for directories inside the DRS option。



![](img/fa777cc2762080537915e24784c618c9_36.png)

In addition to the Django template engine provided by Django。

 you can also extend the functionality by using one or more template engines。



![](img/fa777cc2762080537915e24784c618c9_38.png)

For example， Gingja2 is a popular template engine used in Python。

 and you can configure the settings for adding these extensions inside the settings。pi file。



![](img/fa777cc2762080537915e24784c618c9_40.png)

For example， you can change the default environment settings for Django to use Gingja2。



![](img/fa777cc2762080537915e24784c618c9_42.png)

Okay， so now you know about template engines， let's explore the concept of code reuse。

Jengo helps encode reuse by using templatelate with the help of something called template inheritance。

Template inheritance allows developers to build a base template containing the expected HTML elements of your site and defines blocks that child templates can override。



![](img/fa777cc2762080537915e24784c618c9_44.png)

![](img/fa777cc2762080537915e24784c618c9_45.png)

Once defined， all pages of the website can inherit the base template。



![](img/fa777cc2762080537915e24784c618c9_47.png)

This code reusability helps in saving developers time and effort and follows the principle of Dr。😊。



![](img/fa777cc2762080537915e24784c618c9_49.png)

For example， you can create a base template containing the HTML code for your site's head。

 body and main sections， then in a child web page you inherit the base template and place the specific content of the page。



![](img/fa777cc2762080537915e24784c618c9_51.png)

It's a standard best practice to place template files inside a template folder。



![](img/fa777cc2762080537915e24784c618c9_53.png)

In this video， you learned how to use templates in Django。

 you also explored the concept of the Django template engine and the Django template language。

Templates are quite a vast topic in Django， and you will learn more about them for the remainder of this lesson。

