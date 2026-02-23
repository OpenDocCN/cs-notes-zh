# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P59：17_什么是副作用.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Before moving on to using another hook known as the use effect hook。

 let's take some time to consider its name。 The name of the use effect hook is closely related to the concept of an effect or more precisely。

 a side effect。 in this video you will learn what side effects within a react component are。

 including what pure and impure functions are and their relation to side effects。

 as well as how use effect is used to perform side effects within functional components。

So what is a side effect， a side effect is something that makes a function impureure。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_1.png)

Did you know that functions can be classified as pure and impure？



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_3.png)

Simply put， pure functions don't have side effects and impure functions。 do。

 Let's unpack the concept of pure and impure functions in relation to side effects some more。

 A pure function should a receive specific input。 that is a specific parameter will always return the exact same output。

 no matter how many times it gets invoked。 to illustrate。

 let's explore a function that uses the year little lemon was established。 In this example。

 the established ear component accepts a props object That is a props parameter。

 It also returns a value that is a heading that outputs the words established year followed by a colon space and the value of the year prop。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_5.png)

![](img/9af2429182a0e4e8aa37136f4d5cbf1d_6.png)

![](img/9af2429182a0e4e8aa37136f4d5cbf1d_7.png)

As long as the value of the year prop is 2003， regardless of how many times the established year function is evoked or it is rendered from the app component。

 the output will remain unchanged。 This is an example of a pure function。

 The established year function has no side effects。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_9.png)

![](img/9af2429182a0e4e8aa37136f4d5cbf1d_10.png)

By contrast， an impure function will perform a side effect that means it will do things such as invoke console log。

 invoke fetch or invoke browser's geolocation functionality。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_12.png)

![](img/9af2429182a0e4e8aa37136f4d5cbf1d_13.png)

In this context， a side effect can be thought of as something external to or outside of a function。

 Consider the example of a shopping cart function built for the little lemon app。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_15.png)

![](img/9af2429182a0e4e8aa37136f4d5cbf1d_16.png)

It is an impure function because of the line that reads console log To。

 The console log call makes the function impure as it's a call to a browser application programming interface or API。

 The shopping cart function now depends on something outside of itself and even outside of the react app to work properly。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_18.png)

![](img/9af2429182a0e4e8aa37136f4d5cbf1d_19.png)

So how should you deal with the issue of Iure functions in react Well。

 it's all about containing the impure actions inside their own special areas。To do this and react。

 you need to use the Use effect hook。Let's update the shopping cart component with a use effectect hook to properly deal with the side effect caused by the console log First you need to import the Use effectect hook for react。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_21.png)

The use effect hook works by accepting two parameters。 The first is a callback function。

 The second parameter is an array。 This array can be kept empty， which is perfectly valid。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_23.png)

![](img/9af2429182a0e4e8aa37136f4d5cbf1d_24.png)

While the syntax is valid， it's common to use an arrow function as the first argument of the invocation of the use effect hook。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_26.png)

Note that the use of effect has been simplified to a single line of code。

 It usually spans several lines of code。 That's because it typically needs to do something more meaningful than just console logging the value of a component's variable。

 In this video， you learned about pure and impure functions and their relation to side effects。

 exploring what side effects within a react component are。

 And briefly how use of effect is used to perform them。



![](img/9af2429182a0e4e8aa37136f4d5cbf1d_28.png)

You can look forward to applying this knowledge by using the Use Effect hook introduced in this video to perform side effects。

