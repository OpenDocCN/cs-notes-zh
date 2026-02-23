# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P57：15_修改 useState 钩子.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Imagine that little lemon needs a way to track the restaurant's food inventory。In this video。

 you'll work through some practical examples using an app built for little lemon to revise the use state hook and explore how the use state hook is invoked。

 You'll examine the return values of the use state hook and how it's used to update state。

You are probably already familiar with a used state hook。

 which is used to work with state in a react component with state being all the data an app is working with at a given time。

 But before moving on to use state， let's revisit the concept of array de。

Recall that array is structuring is a way to get individual items from an array of items and save those individual items as separate components。

 Now， let's explore this concept with a practical example。

 Sa you're coding an app that attracts current food reserves in little lemons pantry。

You're using a variable to keep all the veggies in an array As you continue to code。

 you realize you need to get each item from the array into its own separate variable。

For the first item in the array， you want to name the variable V1 as in VeG1， the second item。

 V2 and so on。 with array destruct， you can do this easily using a single line of code。

For more information on array destructuring， you can refer to the additional resources at the end of this lesson。

 Note that with array destructuring， you're free to give any variable name to the items that you destructure from an array。

However， when destructuring objects， you have to destructure a property of an object using that exact property's name as the name of the destructured variable。

 This makes objects a lot stricter in terms of what you can name your destructure variables。

 For that reason， Re uses the array data structure for the use state hooks return value。

 Now that you've had a sneak preview of the return value of the use state hook。

 Let's explore how it actually works。 I will demonstrate how to update state and react apps by using the use state hook to set the initial value of the restaurant name to lemon。

 and then using only the use state updating function to update it to little lemon。



![](img/e9fd08c571547a615abed01e0f609e3e_1.png)

The use state hook allows you to work with state in components。

 Let's start discussing state by revising what happens when I call the use state hook。

 I'm only returning null from here because I want to focus on the console for now。 Ining the console。

 This is what gets logged。 The console logged value is an array with the state variables value being the first item in the array。

 The second item in the returned array is the function that will be used to update the state。



![](img/e9fd08c571547a615abed01e0f609e3e_3.png)

So the U state hook invocation returns a two member array。



![](img/e9fd08c571547a615abed01e0f609e3e_5.png)

The convention is to name the state updating function using camel cases。

 Another convention is to name it by preending the word set to the variable name used for the destructured state variable。

 In other words， the correct way to work with state means that my starting code example should be improved to correctly destructure the array returned from the call to the use state hook。

 Now， the destructured restaurant name variable holds the state and the destructured set restaurant name variable holds the state updating function。

 This is an example of array deuring using the use state hook。

 you may be wondering how you can update state。 Well， when first starting to use the use state hook。

 some developers try to update the state variable in a variety of ways。

 But there is only one correct way to update state when using use state。

 and that's through the state updating function。 In other words， the only way to update the state。



![](img/e9fd08c571547a615abed01e0f609e3e_7.png)

![](img/e9fd08c571547a615abed01e0f609e3e_8.png)

Of the restaurant name variable is by invoking the set restaurant name function。In a react app。

 state changes are usually triggered through the act of a user interacting with the app。

 This means that state changes are usually triggered by user generated events。

 These events such as mouse movements， button clicks and key presses happen all the time in an app。

The role of a developer is to respond to specific kinds of events in a way that's meaningful to the app that's being coded。

 One common way users interact with web apps is through button clicks。

 So let's examine an example of changing state in response to these user generated events。

 namely button clicks。In this example code， I'm adding a button which when clicked will execute a function。

 This function is update restaurant name， which is invoked wherever a user clicks on the button。



![](img/e9fd08c571547a615abed01e0f609e3e_10.png)

Now， when I click the updated restaurantrant name button。

 that will change the H1 heading from Le to Little Le because the imvocation of the update restaurant name function triggered a call to the set restaurant name state Se function。



![](img/e9fd08c571547a615abed01e0f609e3e_12.png)

![](img/e9fd08c571547a615abed01e0f609e3e_13.png)

You should now be able to recall what the use state hook is used for and how it works in practice。

 I hope that working with the use state hook will be a fuss free task for you going forward。

 especially when working with primitive data types to track state in a component。

