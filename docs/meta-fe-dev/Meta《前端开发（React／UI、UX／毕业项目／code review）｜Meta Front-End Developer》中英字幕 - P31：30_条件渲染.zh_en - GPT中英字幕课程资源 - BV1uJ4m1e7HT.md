# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P31：30_条件渲染.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

By now you should be familiar with a concept that react dynamically changes webage content。

For example， you discovered that when a react website changes from homepage text to about me text。

 it isn't going to a new page， it's rendering one component instead of another。While this is useful。

 you need to give react very specific instructions about what and what not to render。

 and when you have components that are responsive to events such as clicks。

 this can add another layer of complexity。

![](img/c4b73e5993c72276a22da45b0124761a_1.png)

![](img/c4b73e5993c72276a22da45b0124761a_2.png)

Fortunately， there are several approaches for writing the logic to ensure that this process goes smoothly and requires less work from you。

By the end of this video， you'll have a high level understanding of conditional rendering and know how to set it up using ternary operators。

😊，Recall that state is a component's internal data。

 which that component can control or change as opposed to props。

 which the component receives but cannot alter。

![](img/c4b73e5993c72276a22da45b0124761a_4.png)

In an app， you can render components conditionally based on whether a specific state data has specific values。

In other words， when you write the rendering logic in the main app component。

 you'll need to reference the state of the other components for example。

 suppose you have a component that contains code for a button that shows a sidebar。



![](img/c4b73e5993c72276a22da45b0124761a_6.png)

The button controls the state of the toggle sidebar variable。

 which is set to false When the button is clicked， the state of the toggle sidebar variable is updated to true。

 and the sidebar component is displayed。

![](img/c4b73e5993c72276a22da45b0124761a_8.png)

To make this possible， React works with conditional concepts and syntax that are already available in JavaScript。

😊，For example， recall the conditional FL statement in JavaScript。

 developers use it to run code conditionally based on whether something is either true or false。



![](img/c4b73e5993c72276a22da45b0124761a_10.png)

To illustrate conditional rendering in action， let's first consider an example productivity app。

Based on the device's date at the time of access， the app displays one of two messages。

 four workdays， the messages get it done。For weekends， it displays get and rest。



![](img/c4b73e5993c72276a22da45b0124761a_12.png)

As a developer， there are a few ways you can achieve this functionality in react。

But in this video you'll focus on using the Ternary operator to write simplified if else conditions you start by creating a component calledCurrent Me This component uses the builtin date function in JavaScript along with the get day method to store the day of the week as a number where Ze represents Sunday and6 the following Saturday。



![](img/c4b73e5993c72276a22da45b0124761a_14.png)

Next， you create the two components that each hold one of the messages to be displayed。

 let's name these components， workday and weekends。



![](img/c4b73e5993c72276a22da45b0124761a_16.png)

The current message component needs to render the appropriate component based on the value returned from the get day function call。



![](img/c4b73e5993c72276a22da45b0124761a_18.png)

Let's set up the conditions to make that happen。

![](img/c4b73e5993c72276a22da45b0124761a_20.png)

Recall that the Eernary operator takes three commands。

First is the condition which in this example uses the logical and operator。

The condition checks if the value stored in the day variable is greater than or equal to one and less than or equal to5。

Then the question mark symbol， followed by the expression to execute if the condition evaluates is true。

In this example， the component workdays is rendered next is the colon symbol which represents the code to be executed if the condition evaluates as false and if this happens the component weekends is rendered using the logical and operator in the condition means that both expressions have to return true in order to render the workdays component otherwise the weekends component will be rendered while using the ternary operator is a common pattern that you'll see in react code if you are new to react it may be difficult to understand what's happening。



![](img/c4b73e5993c72276a22da45b0124761a_22.png)

So let's refer to a simpler version that uses Boolean values。In this example component。

 is it summer yet the variable summer is set to a value of true。

 a ternary operator returns to the expression after the question mark if the condition before the question mark is true。

Otherwise， it returns to the expression after the colon symbol。

 so since the variable summer evaluates to true， rendering this component will return the string。

 let's go to the beach。

![](img/c4b73e5993c72276a22da45b0124761a_24.png)

In this video， you learned about conditional rendering and how to implement it within dynamic apps by using turnernary operators。

