# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P22：21_什么是钩子.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

By now， you've probably already learned about some important and useful core concepts in Re。

At this point， you're ready to learn how to add interactivity。

 maintain state within a react component， and explore hooks。😊，In this video。

 you'll be introduced to what hooks are， how they can be used， and why they are useful。😊。

As you progress as a react developer you'll likely soon use complex components with stateful logic keeping track of state across components can become quite a task and this is where react hooks can help one key benefit of hooks is that they solve the problem of unnecessary code reuse across components Let's find out how they do that hooks are functions that were introduced in react version 16。

8 They let you hook into react state and lifestyle features from components Let's observe an example hook specifically you'll examine an instance of the use state hook as it's the most commonly used one This hook is used to manage the state within a component and keep track of it and it's built directly into react。



![](img/a07589298daaffa5f60f932cc5f6b553_1.png)

![](img/a07589298daaffa5f60f932cc5f6b553_2.png)

![](img/a07589298daaffa5f60f932cc5f6b553_3.png)

To use it the first thing you need to do is import the U state from react so that it's available for use The next step is to declare a state variable within a component you can provide any name to the state variable and the set state function For this example let's call the state variable Show menu and the set state function set Show menu。

If you've learned JavaScript， this syntax may feel somewhat familiar to you。

You are probably wondering what exactly this code does。😡。

When it's actually doing something that you've likely encountered before。

 notice that the convention is to name the state variable and the setta function using arraystruct。😊。

When you declare a state variable using the use state。

 it returns a pair which is an array with two items without array destructuring。

 the code would be long and cumbersome， since it's more confusing and tedious to access the array items by index。

 array destructuring is preferred and it significantly simplifies the code。

You now have a new state variable called show menu。

The U states then sets the initial value of show menu as false。

So to summarize calling the U state hook does two things it creates a state variable with an initial value that represents the current state which in this example is show menu and it creates a function to set that state's variable value which in this case is set show menu the function set show menu is used to update the value of show menu by passing the Boolean value to it it does not matter what names you use for the state variables you can define them based on your component and use case the U state hook should be called at the top level of your component In this example notice that the U state hook was used to track the Boolean state value you can use the U state hook to track any type of data it could be strings numbers arrays。

 Boolean or objects。

![](img/a07589298daaffa5f60f932cc5f6b553_5.png)

For instance， you can even track the number of times a button is pressed。😊。

In addition to the hooks that come out of the box with react。

 you can also build your own hooks which will let you extract custom component logic into reusable functions。

This is an excellent feature and benefit of using hooks the biggest benefit of hooks is the readability and simplicity that they provide to the code。

😊。

![](img/a07589298daaffa5f60f932cc5f6b553_7.png)

![](img/a07589298daaffa5f60f932cc5f6b553_8.png)

In this video you learn the basics on react hooks and explore the Use state hook you now understand the benefits of using hooks and how you can use them within your react applications。

