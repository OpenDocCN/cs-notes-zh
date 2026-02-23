# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P9：8_组件 props 原则.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

By now you should be familiar with the concept of functional components in react they are reusable blocks of code that act much like a JavaScript function。

Recall that in JavaScript， you can make your functions more flexible by declaring them with parameters that allow you to pass in values as arguments when you call the function。

Well， in Re you can perform a similar action using something called properties。

 which are represented as props。

![](img/567c6b6e645653c91aa8100448faa589_1.png)

In this video， you'll learn about the propps object and how developers use it to pass data from one component to another。

Then you'll explore component hierarchy and learn why components are said to have a parent child structure。

Before you begin your journey with props， let's revisit another piece of JavaScript functionality that will help you understand how props work。

It's called the JavaScript object recall this in JavaScript。

 an object is a special type of variable that can contain many values。

You use objects when you need to store groups of related data of different types。

 and each data type is known as an object' property。For example。

 suppose you create an object called fruitruit that contains properties for type。

 quantity and colour。Remember that these properties consist of name value pairs and you can access the object's properties using dot notation。

In React， you can use a similar technique to pass data from one component to another using the property's object or simply props。

Propss allow you to pass data from one component to another it's helpful to think of props as arguments that components can accept and are passed using JSX syntax much like HTML attributes Inside a function you use the keyword props。



![](img/567c6b6e645653c91aa8100448faa589_3.png)

Okay now that you're familiar with the concept of props。

 let's explore an example to send some props to a component and print them out in a react app。

 supposeuppose you have the default code for the react app open in the index dot JS file you call the app component inside the app component you return an H1 heading with some static title text while this code works you can make this heading dynamic by using props。

Let's now explore the syntax involved to create this in the root component index。jS。

 you send the value you want to pass to the app component as an argument in the form of an HTML attribute。

Next， in the app component you accept this argument using the propps object to do this。

 you add the keyword props to the function declaration inside of the parentheses Finally to access this object's properties。

 you use dots notation to reference the name of the object property that was passed as an argument by the HTML attribute。

Once again， remember to enclose your code inside curly brackets so react to knows that you want to work with a prop object and not static text。



![](img/567c6b6e645653c91aa8100448faa589_5.png)

Because props is essentially a JavaScript object， it can accept many data types ranging from simple types such as strings and integers to more complex types such as functions。

 arrays and objects。As a result， props allow developers to have greater flexibility when creating and working with components。

 especially when you want the flow of data in your app to be dynamic。



![](img/567c6b6e645653c91aa8100448faa589_7.png)

While you just explored a basic example to dynamically print a heading。

 you'll get a chance to practice with more complex data structures using props later。



![](img/567c6b6e645653c91aa8100448faa589_9.png)

Okay， so now you're familiar with how props work by sending data between components。

Let's explore this data flow in a little more detail。When two components communicate with each other。

 the components sending the propPS data is known as the parent and the components receiving the propPS data is known as the child and as you've just learned with the example earlier。

 this parentchil relationship allows parent components to pass data down to child components using props it's also possible for a parent components to send the same data to multiple child components however it's important to know that this communication is a one directionional data flow。



![](img/567c6b6e645653c91aa8100448faa589_11.png)

It's not possible to communicate from the child component back to the parent components using props instead developers use other approaches。

Don't worry about that for now， you'll learn more about them later。



![](img/567c6b6e645653c91aa8100448faa589_13.png)

Although props are a very powerful tool and react， they do have some limitations。For example。

 you just learned about how it's not possible to send data from the child component back to the parent component using props。

Another important limitation has to do with something called pure functions In programming。

 a pure function is a function that will always return the same outputs for the same argument values that are passed in Don't worry too much about pure functions for now just keep in mind that it in react when you declare a component using props it must never modify its own props。



![](img/567c6b6e645653c91aa8100448faa589_15.png)

![](img/567c6b6e645653c91aa8100448faa589_16.png)

In this video， you learned about how props are used to pass data to components。

You discover that a prop is a special react object that works in a similar way to a JavaScript object and that its properties can be accessed by dot notation。

You also learned why developers use props in order to make their apps more dynamic and flexible。

Finally， you examined some of the limitations about using props in that you cannot use them to send data back to a parent component and that functions using props must never modify its own props。

