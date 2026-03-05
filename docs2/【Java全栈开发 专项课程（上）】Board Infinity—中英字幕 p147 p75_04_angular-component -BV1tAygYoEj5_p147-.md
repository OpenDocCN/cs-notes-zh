# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p147 p75_04_angular-component -BV1tAygYoEj5_p147-

Hi there in the previous video we learned about Angular eivavators now in this video we will learn Angular component。

So let's get started。In Angular， a component is a fundamental building block of an application。

It represents a specific part of the user interface and encapsulates the associated logic。

 data and UI template。In other words， a component combines a template。

 a class and metadata to define a reusable and self contained unit that represents a part of the user interface。

The template represents the visual part of the component and defines how the component Ui should be rendered。

It can be defined using HTML markup and angular template syntax。

The template can include data binding， even handling directives and other angular features to make it dynamic and interactive。

The class representss the logical part of the component and contains the code and business logic associated with it。

It is written in Typescript and typical uses object oriented programming principles。

The class is responsible for defining properties， methods and handling component specific behavior。

The metadata provides information about the component to angular。 it is defined using decorators。

 The main decorator used for components is the component decorator。

The component decorator takes an object as an argument and provides metada such as the selector。

 template， styles and more。Let's try to understand this with the help of an example。



![](img/57d6b7abb19b7e4e2d429302cfa8b352_1.png)

So let's go to the VS code and here I have a basic Angular project ready。

You can see we have all the files listed here and this is the root module that is a dot module ort P and we have the root component that is Ab dot component dot P。

To create a new component， we can open up a terminal。

And let's import let's open up a new terminal and let's run a command。Anng。

 anng that stands for global and see for component and then the component name。

 So here we are using an angular CI so make sure that you have installed it already。

So Ill just name the component as test and if I click on enter。

You will see that a couple of things happen here。It created these many files and updated app。

 moduleule dotpss。You will notice here that we have a folder inside this we have all these files。

We only gave the name as test。So this is the default structure when you are using anglengs C。

 it adds start component to it。We have Css for the CsS file。

 and we have HTMLml for the markup where we have test works here。

 and then these are some specs we do not require this， so let's click on delete。

And then we have test dot component dot Ts。Here you can see in the decorator we have a selector that is app test。

And we have a template URL， and we have style URLs as well。Next， what we can do is。

We just have to include this in the main HTMLl file。So we can go here to app component do HTMLml。

And we can add or remove multiple things from here。 So this is the default output。

Let's go and delete everything from。Here to here。You do not require this。

And you only have at this point this welcome here。 So let's just leave a pan tag as it is。

And then we can remove the image as well。And this is our main a component or HTMLml here。

 let's use this a test。So。Lets click on save and let us go here。

 we get there that and expect it losing depth track so we have to remove this as well。



![](img/57d6b7abb19b7e4e2d429302cfa8b352_3.png)

Now you can see welcome and test works and we have this class as well， so let's remove it。



![](img/57d6b7abb19b7e4e2d429302cfa8b352_5.png)

And here we can change this to wavevo again。

![](img/57d6b7abb19b7e4e2d429302cfa8b352_7.png)

So now you will see that we have test works and this is how you can create a component。



![](img/57d6b7abb19b7e4e2d429302cfa8b352_9.png)

So you can see we have a template here in the decorator。So lets go to component or Ts。

 we have a selector， this is a selector， or you can see this is a element that selects。

And this app test is the element that we created in the app dot component dot HTMLtml page。

And in the component decorator， that is this component。You can see that we have selector。

 so it defines the HTML selector used to identify and render the component。In this case。

 it is app test。Which means we can use app test in our estimate to render this component。

Then we have this template or you can say template URL。It defines a component you white template。

In this case， we have a just a pay tag with a text of text works。

So this is how you can create a component using this angular CI otherwise you have to create these files manually you can do that as well。



![](img/57d6b7abb19b7e4e2d429302cfa8b352_11.png)

So that it， you have created an angular component and used it within your application。

Components are reusable， modular and enable you to build complex UI structures by combining and nesting them。

They encapsulate their own logic， data and UI， making it easier to manage and maintain your application score base。

This is all for this video in the next video we will understand about Angular module See you in the next video。

 Thank you。

![](img/57d6b7abb19b7e4e2d429302cfa8b352_13.png)