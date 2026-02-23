# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P25：24_管理状态.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

As react applications grow in complexity， so too can the complexity of managing states across components。

As a result， developers need a way to manage state in their application in this video you'll learn how to describe the concept of managing state and explore some of the solutions to managing state in react applications。

😊，To illustrate a scenario in which states needs to be managed。

 consider a small react app that helps promote a healthier lifestyle by allowing the user to monitor their food intake。

This app tracks a daily meal plan and the user can click on each individual meal as they've consumed it。

The app then updates to show how many meals that are still left to be consumed for the day。

The app consists of three components。A root component called app dot JS。

 and then two child components， Me list and counter。

Let's explore each component in a little more detail。First。

 the app component imports the Me list and counter component and renders them on the screen。Next。

 the Me list component uses Use State to hook to list a day's meals which are stored in an array。

The array elements are saved inside the today's meals variable。

 then the Me state variable is initialized to hold this value。In other words。

 the meal state variable holds the array。😡，Finally。

 the counter componentent tracks the number of meals that a user is allowed to eat today。

While this coding component structure may look good， there is a bit of a problem。

The counter componentent needs to get state information from the Me list component。

 but both components are rendered by the app component。In other words。

 the meals list and the counter components are siblings and not in a parent's child's relationship。

This brings up a question。How can you pass the state information from the meals list component to the counter componentent as the counter componentent is not a child of a meals list component？

Let's explore a possible solution。First， you can simplify the meals list component by extracting the returned value into its own component。

Then you can work with the separate components to display different meal items。

So let's call this new component Me item。To do this。

 you can use the practice known as liftfting state up。

This means that you move the state from meals list up to the app component。😡。

Then you can pass state through props using the Me list component as a sort of bridge to the meal item component。

And then you just have to count the data available in the counter components。

The state has now moved up to the app component and my Me list component becomes a conduit for the state data to be passed to its destination。

 the meal item component。

![](img/fa1aea144413c627549160d1c529fb5d_1.png)

The question you must now ask is what is wrong with prop drilling？

Prorop drilling is a commonly used term to describe having to pass state through props in several layers of components from the parent to the child to that child's child and so on。



![](img/fa1aea144413c627549160d1c529fb5d_3.png)

Note that if the source data changes， you will have to transfer those changes across the entire prop drilled structure。

This complicates things because state updates go to all the child's components and their siblings。

 which then need to be updated to reflect this state's change。Additionally。

 the problem gets bigger as the app grows and you'll potentially have a huge amount of states being kept in the app component。



![](img/fa1aea144413c627549160d1c529fb5d_5.png)

Keep in mind that most of that state is not really supposed to be in the app component。

That is because that state is about components such as the meal item component。

There's another way to phrase this problem through the viewpoint of global state。

Whenever I have states that might have to be used in various places in my app。

 that's a global state issue。

![](img/fa1aea144413c627549160d1c529fb5d_7.png)

An elegant solution for this issue is Re context API。

One way to think about the context API is that it cuts out the middleman。

There's no need for prop drilling and lifting state up。😡，Instead。

 the component that needs the data simply gets it from the context API。



![](img/fa1aea144413c627549160d1c529fb5d_9.png)

The way that this is achieved is by extracting the state into a separate file that holds the states in context。

Then any file that needs it simply imports it and uses it Great job。

 you should now have a great understanding of managing state in react。😊。



![](img/fa1aea144413c627549160d1c529fb5d_11.png)