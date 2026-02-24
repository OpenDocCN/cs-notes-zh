# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P46：4_在 JavaScript 中转换列表.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

How many times have you found yourself browsing apps？ Maybe you've used an app to order food。

 scrolling through different menus， hoping to find what you'd like。 Well。

 lists like this are common to almost every app， which is why it's important that you know how to manipulate them in jascript。

 Chances are you'll need to transform various elements before displaying the final list to your users。

 So in this video， you'll learn how to use the map method in jascript to transform lists of data。

 Let's imagine that a restaurant called Little Le would like to display a list of its popular desserts。

 Remember that a list is a simple collection of elements， which translate it to jascript terms。

 represents an array。😊，These arrays can contain any type of data。

 but the most common type you'll encounter per element is an object。 Now。

 say little Lemon uses an external service to query a list of its most requested desserts by users。

 However， when fetching data from a third party like this。

 you are generally provided with more data than you need。

 and the data will be provided in a format or shape that is determined by the third party。



![](img/80029ca35eb563512505422b0c781c94_1.png)

This means that you may need to write more code to handle the data in order to retrieve just the information you need。

 That's where the map method comes in as a way to ignore everything that you do not want displayed on screen and extract only the data that your users care about。

 So let's explore how to transform this list of dessert items using the map method in ja。

In JavaScript， when you deal with lists of items of any kind。

 you need to use the array type JavaScript offers different methods that you can use with arrays to perform various operations in order to perform a transformation operation。

 you must use the map method。Coming back to little lemon。

 imagine you have a list of its top requested desserts encompassed in a variable called data。

 Each dessert has the following properties。 I D title， image， description and price。 In this case。

 you would like to show a very simple list of desserts with a property called content。

 which you can create by merging together the title and description。

 and the price of the delicious dish。😊，First， I'm going to define a new variable since the map method always returns a new array let's call this new array top desserts。

Next I'm going to apply the map method to the original data array for now I'll return the data as it is。

 so you can examine the basic structure of a map transformation。

I would like the new items to have two properties， the first is content。

 which is going to be a combination of title and description。

Let's use a dash character to separate the two。

![](img/80029ca35eb563512505422b0c781c94_3.png)

Secondly， there's the price， which I will pass as it is。



![](img/80029ca35eb563512505422b0c781c94_5.png)

Last， I will console log the result to demonstrate that the new list I have created contains the shape or format that I originally intended。

And here's your transformed list。You just learned how to transform data in JavaScript with a map method This is a simple。

 yet powerful tool you will find yourself using quite often when dealing with data from an external provider。

😊。

![](img/80029ca35eb563512505422b0c781c94_7.png)

Your users will thank you when they experience how easy it is to navigate and consume information in your apps。

