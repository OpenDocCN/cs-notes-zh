# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P72：30_传播属性.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

![](img/69e9661183e218d7e3758de21ec35e70_0.png)

The spread operator is one of the coolest additions to the jascript language。

 Thanks to the spread operator， which is represented by three dots。

 common operations that previously required a bit more code， like cloning an object or array。

 are now so much simpler。So in this video you will learn how to use the spread operator and objects。

 how to spread native properties to dom components。

 how to design flexible components at about the caveats when using the spread operator。

Imagine that the little Le restaurant wants to have a simple welcome screen where users can sign up or log in。

 depending on whether they have an account or not。 The sign up and log in buttons are in nature。

 very similar with differences in the text and the action taken when they are clicked to achieve this implementation。

 you could define a button component that encapsulates the native H button element and uses the same props as its native counterpart。

However， a button presents dozens of different properties for customization。

Instead of having to specify each of them manually。

 the spread operator can be used to forward all of them without typing each one manually。

React embraces this operator at its core when it comes to props。But before digging deeper。

 let's refresh what this operator enables for objects in pure JavaScript。

The spread operator can be applied to different data types in JavaScript， such as arrays。

 objects and even strings。 Since react props are just objects。

 this lesson is going to be focused strictly on the object type。

Copying and merging objects are the two main operations you may perform with these operators。

For a simple copy of an object， this is the syntax required。

 curly braces and the three dots preceding the object to copy。In this example。

 order amend represents a last minute change to the type of pizza ordered by the customer。

For merging， first， you need to spread the properties from the original object and then provide the new properties to be added or to replace original properties。

 The property called itemem has been replaced with the new order information。 Great。

 now that the preliminaries are covered。 let's explore how react uses the spread operator。

This order list component example renders an order component。

 Each order component expects four props， an I D， username， item and price。

 This first example shows how you might usually do it passing all the props in the return statement explicitly。

However， this can be simplified if you'll already have the props your order component needs in an object。

Here you can see that only the spread operator is required in the return statement。

 saving us time by just spreading all the props and avoiding having to type them manually。

This pattern allows you to create flexible components。

But there are also some caveats you need to keep in mind when using the syntax。

 Let's explore this in more detail， with an example demonstration。In this application。

 I have created a simple welcome screen for Little Lemon Restaurant where users are able to sign up or log in depending on whether they have an account or not。



![](img/69e9661183e218d7e3758de21ec35e70_2.png)

At the top， I have defined a button component that wraps the native button from the dom。

 This component expects the same props as its native counterpart with the addition of the type prop。

 which is a custom prop that determines the background of the button based on the theme provided。

 Here is a clear example of using the spread operator to group all the props that belong to the native button and explicitly extract the custom props I have defined for this component and are react specific。

 type and children。This implementation is clean for developers。

 since they can provide all the props a native button would expect。

The second example is a login button component that renders the custom button component I have created itself。

This login button does some preconfiguration by fixating some of the props from the button component。

 In this case， type and on click while still passing the native button props down with the spread operator。

 Now， the app component renders the two buttons and uses the button component for the sign up and the login button component for login。

 The buttons are both configured here to send the user to the sign up page。

 unless they have an account in which case the login button components's original onclick function will send them to the login page。

 I have also provided both with an onclick handler to show an alert about the intended action when the button is pressed。

 However， observe how I have mistakenly provided the same alert message that is used for sign up on the login button component。

 Hence， overr the onclick handler that the login button already defines。Now。

 can you guess what the message of the alert will be when I click on it？

I'll give you a few seconds to think about it。

![](img/69e9661183e218d7e3758de21ec35e70_4.png)

Well， if you guessed logging in， you guessed right。

 The reason is that even though I have overriden the onclick prop in the login button component。

 its implementation is done in a way that prevents that overriding from happening。



![](img/69e9661183e218d7e3758de21ec35e70_6.png)

Why is that because of the order of the spread operator？

If I go ahead and spread the props at the end instead， right after on click。

 the behavior is different and signing up is output instead。



![](img/69e9661183e218d7e3758de21ec35e70_8.png)

So what are the main takeaways from this lesson？The spread operator is a great tool that enables the creation of more flexible components。

 especially when forwarding props automatically to other components that expect them。

 as well as providing your consumers with a nice component API。However。

 keep in mind that depending on the order of the spread， the behavior may differ。

 so you need to be conscious about your decision when it comes to component design。😊。

In the example of the login button before， it may make sense to prevent the override of the on clickick property。

 but it may not be the intended case for other props。Well done。

I hope you're getting an idea of the multiple benefits that can be gained from using these react tools。

