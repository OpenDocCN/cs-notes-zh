# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P50：8_什么是受控组件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

When browsing the internet， theres a big chance that you'll land on a form。

 even without you realizing it， from simple email inputs and subscribing to newsletters to more complex forms such as creating an account on your favorite social media platform。

 forms are everywhere。So you'll probably find yourself implementing them in your applications regularly In this video。

 you'll learn the concept of controlled components and react and how they are used in form processes。

 The fundamental concepts of H forms and how forms can be created as react components when it comes to react applications。

 H forms work differently to other dom elements。 You may recall that the Dom is a logical treelike structure representing the H document。

 and he uses nodes to describe the various parts of the document。



![](img/4547495806f965b4513b67e8e3a84d17_1.png)

![](img/4547495806f965b4513b67e8e3a84d17_2.png)

Traditional H T M L forms keep some internal state inside the dom and have some default behavior when submitting them。

 That's normally done via the action attribute， which points to the end point that will handle the request。



![](img/4547495806f965b4513b67e8e3a84d17_4.png)

But what if you would like a more granular level of control， For example。

 customers of the little Lemon restaurant can reserve a table on the website using a form。

 Imagine if there was a function that could handle the submission of the form and access the data that the user entered into it。

That's where controlled components come in Control components are a set of components that offer a declarative application programming interface or API to enable full control of the state of form elements at any point in time using react state。

 rather than relying on the native state from DOm elements。

 the react state is made the single source of truth。

 controlling the displayed value of your form elements at all times。😊。



![](img/4547495806f965b4513b67e8e3a84d17_6.png)

![](img/4547495806f965b4513b67e8e3a84d17_7.png)

The way you perform this state delegation is via the value Pro value is a special property the react added to most of the form elements to determine the input content at any point in time during the render lifecycle so in order to create a controlled component。

 you need to use a combination of local state and the value prop。



![](img/4547495806f965b4513b67e8e3a84d17_9.png)

Initially， you assign the local stage to the value property。

 but how do you get updates from any new text character entered in the input？



![](img/4547495806f965b4513b67e8e3a84d17_11.png)

While for that， you need a second prop to complete the design of your controlled component。

 the on change callback， the on change callback receives an event parameter。

 which is an event object representing the action that just took place similar to events on DOm elements。

To get the new value from every keystroke， you need to access the target property from the event and grab the value from that object。

 which is a string。

![](img/4547495806f965b4513b67e8e3a84d17_13.png)

Finally， to have control over the form values whenever the form is submitted。

 you can use the on submitub prop in the form H element。

 The on submitubmit callback also receives a dom like event as a parameter。

There you can access your form values to perform any desired logic that must take place before submission。

 for example， validating your input values。Also， if you would like to prevent the default HTML form behavior。

 you need to call event。prevent default inside your on submitubmit callback。



![](img/4547495806f965b4513b67e8e3a84d17_15.png)

Well， there you have it。 You have discovered a technique called controlled components that enables reactact to be the source of truth for the state of your form inputs。

 React offers controlled versions of the majority of input types and recommends using controlled components for the implementation of forms。

However， keep in mind that there are still some form elements that remain uncontrolled。

 similar to their dom counterparts， so as you move forward with your learning。

 you will gain more insight into both controlleded and uncontrolled form elements。😊，In this video。

 you have learned about the concept of controlled components in react and how they are used in form processes。

You've also explored the fundamental concepts of HTML forms and how forms can be created as react components。

