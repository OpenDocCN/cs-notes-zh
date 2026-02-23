# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P70：28_带有子组件的组件组合.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

When designing react components， one of the most important properties developers tend to overlook is the children Pro。

 the children Pro， which is a special property all components have。

 is the foundation for the react powerful composition model。

Say the little Lemon restaurantrant wants to enable users to have accounts on their app。

 This would mean processes would need to be built to create， manage and delete accounts in the app。

These types of processes can be constructed simply and efficiently using component composition with children。

In this video， you will learn why component composition is so important and how to effectively use and appreciate the children prop。

You will also learn about two key features of composition。

 and you'll explore some practical examples that will help you understand how you can leverage it。

 So your components are more robust and reusable。 There are two main features that enable component composition。

 containment and specialization。 Let's break down these two main features。 Now。

 starting with containment。Containment refers to the fact that some components don't know their children ahead of time。

This is especially common for components like a sidebar or a dialogue where they de limitit a specific area in your UI to contain other elements。

 You can think of them also as generic boxes。 in case you don't know a dialogue is a type of modal window where the rest of the U I is disabled until the modal is addressed and interacted with。

For these component boxes， the recommended approach is to use the children Pro to pass children elements directly as their content Let's explore this with a dialogue example。

Here you have a dialogue component which acts as the box。

 taking care of styling the container to make it look like a modal window。By using the children prop。

 it has become a generic component to which we can provide any valid JSX as children。

To illustrate that， the confirmation dialogue component has been defined。

 which uses the dialogue component and renders as children， a title and a description。

This example also showcases the second feature of component composition specialization specialization defines components as being special cases of other components。

 In this example， the confirmation dialogue is a special case of dialogue。



![](img/697491d10bb7cd508e02666f624b63e6_1.png)

Now that you are familiar with the basics of component composition。

 let's go ahead and code an application to demonstrate what you've learned。

 This application has been created with createate React app。

Imagine little Lemon would like to offer an easy way for their users to delete their accounts if they want to。

The goal is to build a generic dialogue component that will contain a title， a description。

 and a warning button to make sure users are aware of the actions consequences。

 all using component composition。I have already created two generic components。

 a button and an alert。 The button uses the children prop to specify its text。

 and the alert is a generic box that renders an overlay in the background and a white modal in the center of the screen。

😊，The children Pro determines the content of that modal。

The first step is to create a warning button using the specialization feature of component composition For that。

 I'll define a new component named Delete button， where I'll render the button component and configure its properties to have a red color and the text delete。

Then I'll go ahead and render the alert component。

![](img/697491d10bb7cd508e02666f624b63e6_3.png)

As it stands， it's just a generic white box or container。

This illustrates the second feature of component composition， which is containment。

I can customize the content of the box in any way I would like by just providing JSX as its children to fulfill the requirements of little Lemon。

 I'll create a header titled Delete account， as well as a paragraph to inform the user about the action。



![](img/697491d10bb7cd508e02666f624b63e6_5.png)

I want to state clearly that they will miss out on the chef's delicious recipes if they delete their account。

 so I'll reflect that in the description。Finally， the last piece is to render the delete button as defined previously。



![](img/697491d10bb7cd508e02666f624b63e6_7.png)

And that wraps it up。In this video， you have learned about a react technique called component composition and why it is so important。

 you also learned how to embrace the two key features of composition， containment and specialization。

 and to explore some practical examples that help you to create components that are more robust and reusable using the special children prop。

😊。