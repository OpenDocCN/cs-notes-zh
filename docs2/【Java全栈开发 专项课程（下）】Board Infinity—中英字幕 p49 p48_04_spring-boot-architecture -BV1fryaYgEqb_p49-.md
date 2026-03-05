# 【Java全栈开发 专项课程（下）】Board Infinity—中英字幕 p49 p48_04_spring-boot-architecture -BV1fryaYgEqb_p49-

![](img/520dab6e3989631a9c8b2f44a6f9749f_0.png)

Hi there Today in this session I will talk about string boot architecture。

 how does this architecture works internally， so let's get started。



![](img/520dab6e3989631a9c8b2f44a6f9749f_2.png)

As I said， springboard is a module of the spring framework。

It is used to create standalone production grade spring application with very bare minimum support。

It is developed on the top of the core of spring framework and allows the layered architecture in which each layer communicates with the layer directly below or above the。

Hererical structure， which is a tree like structure。

There are four layers that you need to understand in this architecture One is the presentation layer。

 second is the business layer， third is a persistence layer。

 and the fourth one is the database layer。In the presentation layer。

 the presentation layer handles the H DP request， translates the JSson parameters to object and authenticate the request and transfer it to the business layer in short term。

It consists all the views or the front and part。Next that we have is a business layer。

 Business layer handles all the business logic， and it consists of services。

Classes and uses services provided by the data access layer and also helps in authorization and validation。

Persistence layer contains all the storage logic and translates the business objects from and an object database row。

Database layer is the actual database which helps in performing the cr operations such as create。

 retrieve， update and delete。

![](img/520dab6e3989631a9c8b2f44a6f9749f_4.png)

This is the springboard flow architecture。Once we are ready to have the validation classes view classes in the utility classes。

 Spring boot uses all the modules of spring like spring canvasbassy， spring data， etc ce。

 and the architecture of the spring boat is the same as the architecture of spring canvasbassy。

 except one thing。😊，Here we have a data access object or a data access object implementation classes in the springboard。

That we use to communicate with the database and the model itself。

It creates a data access layer and perform the grid operations client makes the HTP request which is put delete get or put。

The request goes to the controller。And controller maps。

The request and handles it after that it calls the service logic if required in the service layer。

 all the business logic performs on the data that is mapped to the Jpa。With model classes。

 And then the JSP page is returned to the user。 if no error required。 That's how your spring。

Boat flow architecture workss。

![](img/520dab6e3989631a9c8b2f44a6f9749f_6.png)

So stay tuned to learn more about Spring Iizer and the development of REest API using Springboardat。

 see you in the next session。

![](img/520dab6e3989631a9c8b2f44a6f9749f_8.png)