# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P71：29_在 JSX 中动态操作子组件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

React children is one of the special props all your components have implicitly。That。

 along with the react composition model， enables a new paradigm of component design。So far。

 you have discovered how to leverage this special prop and read modede only。

 meaning that your components consume it as it is provided。

 But what if I told you that you can go even further and transform your children's elements in any way。

 shape or form。To illustrate， say the little lemon restaurant wants a away to visualize a summary of live orders as they come in from customers。

 What would be really useful for the chefs working in the kitchen is to display each customer order in its own separate row with the name of the dishes。

 the amount of each dish， the total price， the time of submission and the full name of the customer。

Well， by using a set of new react APIs that will enhance your component design skills。

 you will be able to solve this problem for little lemon with a smart and efficient solution。

 Let's start by exploring two of these powerful react APIs Re dot clone element and react dot children In this video。

 you'll learn how to use both of these react APIs and how they can be used to manipulate the render output dynamically。

 Let's explore the first of these As Re dot clone element in more detail。😊。

This is part of the reactact top level API， and it's used to manipulate and transform elements。

Top level API refers to the way you would import those functions from the react package。

 You can either import， react as a global object in the top of your file and access them as methods on that object or alternatively as a named import。

Recall that elements are just plain jascript objects the react uses internally to describe what you want to appear on the screen。

 React dot clone element effectively clones and returns a new copy of a provided element。

 The first argument is the react element you would like to clone。

 And the second argument is the props that will be added and merged with the original props passed into the component。

Remember that props in react are immutable objects。

 so you must create a copy of the element first and perform the transformation in the copy。

That's exactly where react。t clonene element allows you to achieve。

This API is useful to allow a parent to perform the following operations， modify children properties。

 add to children properties and extend the functionality of children components。For example。

 you could add another prop dynamically to the submit button element illustrated before。

Another important top level API useful for children manipulation is React dot children。

 which provides utilities for dealing with the Pros dot children data structure。

The most important method is the map function React dochil do map is very similar to the map function from array raises and invokes a function in every child contained within its children prop。

 performing a transformation and returning a new element。



![](img/04b18597ad51f7451ef346423b2d4f3d_1.png)

Don't worry if those As still sound a bit confusing。

 Let's get into some code to give you a better picture。

 The little Le restaurant is busy receiving live orders to visualize a summary of those orders。

 I have been tasked to display each one of them in a row。

 having a fixed horizontal spacing between each piece of key information In this application。

 There is an order that has been submitted for a client requesting a pizza margarita。

Each order contains the name of the dish， amount， total price， time of submission。

 and full name of the client。I have created a row component that will handle the separation per item。

At the moment， it just returns the children as they are provided。

 so all the items on screen are cramped with no separation。Let's go ahead and use both Re。

t cloneone element and Re。children。map as the implementation to solve the separation problem。

The first thing I'll do is use the children dotm function to iterate through each child。



![](img/04b18597ad51f7451ef346423b2d4f3d_3.png)

So far， I am returning each child as it is。 So still no changes on the screen。

 to implement even horizontal spacing。 I am going to add some custom style that will set some left margin in each child。

 except for the first one in order to specify the amount of space。

 I will create a new prop called spacing。 There will be the number of pixels and will use string interpolation to set the margin style properly in pixels。



![](img/04b18597ad51f7451ef346423b2d4f3d_5.png)

Now that the style is defined， I need to attach it as the style prop in each element。

 So in the map function call back， I'll return a new copy of the element using react dot clone element。

 The second argument is what lets you specify the new props。In this case。

 I'd like to add a new style prop that will merge the previous style。

If the element is not the first child， then I'll also merge the child style object that contains the margin left statement。

Great， the last step then is to use the spacing property in the row component。

 Let's set it at 32 pixels。😊。

![](img/04b18597ad51f7451ef346423b2d4f3d_7.png)

And there you go， each live order now presents all the information clearly so that chefs don't make any mistakes and cook the wrong pizza。



![](img/04b18597ad51f7451ef346423b2d4f3d_9.png)

In this video you have learned about two new APIs， React。 cloneone elementement and React。children。

map， providing you with a powerful tool set to manipulate children dynamically with ease。

