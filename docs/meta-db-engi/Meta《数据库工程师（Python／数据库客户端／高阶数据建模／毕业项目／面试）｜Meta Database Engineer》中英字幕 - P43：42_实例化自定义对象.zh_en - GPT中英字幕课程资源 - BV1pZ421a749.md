# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P43：42_实例化自定义对象.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

Code reusability is the use of existing code to build new software。

 Reusability is a core programming concept By the end of this video。

 you'll not only be able to create a class and instantiate it with variables and methods。

 but you'll also discover how referencing the same variables and methods in separate instances can produce different outcomes。

 meaning that the code is reusable， I'll start by creating a new file called recipes do Pi。

 where I'll also create a class called recipe。

![](img/9a6de63664709365506af2447dfafdee_1.png)

Before continuing， let's also explore two special methods in Python。The first one is the new method。

 which is responsible for creating and returning a new empty object。To write it。

 I start with the deaf keyword， followed by double underscore new。It then appears as a suggestion。

 so I click on it to fill out the rest。The CLS here is not a keyword， but rather a convention。

 it acts as a placeholder for passing the class as its first argument。

 which will be used for creating the new empty object。The second method is the Ini method。

 which is similar to what is known as a constructor in some other programming languages。

It takes the object created using the new method， along with other arguments。

 to initialize the new object being created。I write it with the de double underscore in knit。

 and then choose the first suggestion that pops up。

The init method takes the new object as its first argument。

 The self keyword here is another convention。It has no function itself。

 but serves as a placeholder for self reference by the instance object。

So let's delete the two example methods and then write some code that demonstrates how to use the state of the object to your advantage。

I begin with an init method， which I then use to initialize a few values。

I do this for the value D by typingse dot D equalsD。I then do the same for the values， items。

 and time。Before moving forward， I want to check that the arguments in the initializer will match those of my instances to do so。

 I add dish， items and time after self。Imagine a real world scenario where a restaurant chef wants information about the recipes they have been using。

 So let's write a class that will help them with that。

 I have the variables dish items and time And which items will hold the recipe ingredients。

 I now write a function to produce a string out of this information。

 I type de contents and then self in parentheses on the next line。

 I write a print statement for the string the plus self dot dish plus has plus self dot items plus and takes plus self dot time。

Plus， min to prepare。Here we'll use the backslash character to force a new line and continue the string on the following line。

For this to print correctly， I need to convert the self dot items and self dot time references to strings by appending STR at the beginning and encasing each reference in parentheses Now that I have a class set up。

 let's use it to create a pizza instance。I write this as pizza equals recipe， opening parenthesis。

 the string pizza comma。Opening square bracket， cheese， comma， bread， comm， Tomato。

 closing square bracket， comm， and 45 to represent the time followed by the closing parenthsesis。

I also want a pasta object， so let's copy and paste the code for the pizza object and change the object name to pasta。

 the ingredients to panet and sauce， and the preparation time to 55 Now that I have a class in two instances。

 let's see if I can access the instance attributes and methods。

I write two print statements for pizza dot items and pasta dot items。When I run the code。

 I find that despite passing the same function and variable items。

 the two instances produce different contents。So next。

 let's try printing the instance method contents over pizza。Before we move forward。

 let's clear the terminal so we can more clearly see what the output will be。

I type another print statement for Pa doc contents and empty parentheses。I run the code once more。

 and the output uses the class method to print a line stating。The pizza has cheese， tomato。

 and bread， and takes 45 minutes to prepare。

![](img/9a6de63664709365506af2447dfafdee_3.png)

That's a demonstration of creating a class and instantiating it with variables and methods。

 then referencing the same variables and methods in separate instances to yield different outcomes。



![](img/9a6de63664709365506af2447dfafdee_5.png)