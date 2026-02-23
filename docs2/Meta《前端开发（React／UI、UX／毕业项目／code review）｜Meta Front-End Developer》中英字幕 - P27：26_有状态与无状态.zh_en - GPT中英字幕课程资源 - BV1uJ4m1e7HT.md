# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P27：26_有状态与无状态.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

In life， there are rarely perfect solutions that suit every need。For instance。

 this concept applies when it comes to selecting a vehicle。

A small car is usually more fuel efficient， but has limited space。On the other hand。

 an SUV can handle many passengers but burns fuel quickly。😊。

Making the best choice start with identifying your specific needs。

This is no different when it comes to choosing stateful or stateless component in programming。

By the end of this video， you'll be able to describe the differences between types of state and choose the best types to suit a given need and explain how the dynamic nature of react causes structured decisions to influence complexity。

The distinction between stateful and stateless components is that a stateful component holds state as internal data and it states changes based on the way that the app is built。

 often as a result of user actions。A stateless component， however。

 doesn't store state and any changes must be inherited through props。

When deciding if a component should be stateless or stateful， you can refer to the following rules。

Use stateless components when your component doesn't need to maintain its own state in order to work。

 use state components when your component does need to maintain its own state in order to work。



![](img/cadff5b6a617de6b6017f04149d2c302_1.png)

This might sound like an oversimplification， but let's explore why this general rule is enough。

A common approach for organizing components in react is to have a stateful component as the parent。

 which then sends its state down to several stateless components that then receive the state and render it on the screen。

The children components are stateless because they don't have their own state and only receive their parent state when passed down by using props。

Keep in mind that you should never change the values of props in children components as they are immutable。



![](img/cadff5b6a617de6b6017f04149d2c302_3.png)

Now that you know the basic logic， let's break down a specific example of this approach in action。

 starting with two components， the app component and the child component， which returns a message。

In the app component， the use state hook defines and keeps the states that will be passed to the child component as the props object。

The app component renders the child component and passes the date to it in a string format as a prop named message。



![](img/cadff5b6a617de6b6017f04149d2c302_5.png)

One thing to keep in mind and something that is often overlooked by react beginners is that a prop doesn't always have to pass state。

In addition to states， JavaScript values and functions can also be passed to the child component。

 it's still data， but it's prop data rather than state data。



![](img/cadff5b6a617de6b6017f04149d2c302_7.png)

In the child component， there is an H1 element。The content of this element will be the message prop that is passed into the component。

Note that props are not changed or updated in the components as they are immutable。

 meaning they can't be changed。Since the child's component doesn't store any state。

 it is a stateless component。All of its data comes from the props passed into the component。

The app component stores these states which can be changed through events and functions and is therefore a stateful component。



![](img/cadff5b6a617de6b6017f04149d2c302_9.png)

In this video， you learned why and when to utilize stateful or stateless components in your react apps based on your specific needs。

You also observe that although a stateless component can't directly pass state。

 it can still trigger actions that will update the state of other components。

