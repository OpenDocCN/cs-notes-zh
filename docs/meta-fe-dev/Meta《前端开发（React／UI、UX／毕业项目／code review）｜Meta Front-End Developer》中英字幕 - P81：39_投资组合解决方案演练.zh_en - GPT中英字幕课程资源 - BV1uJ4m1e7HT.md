# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P81：39_投资组合解决方案演练.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Let's now work through what I've produced and please， if you find something that inspires you。

 don't hesitate to incorporate it into your own solution as well。 Allright， let's get started。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_1.png)

I'm using a UI library， Chakra UI that offers a preset of styles for your react components that allows me to avoid worrying too much about CSsS and focus on the business logic for my portfolio page。

 Let's have a click overview of the whole application。

 The layout consists of a header that contains links to all my relevant social media accounts and links to the different sections of the page。

 There are three full screen sections， a landing section with a profile picture and a quick description about myself。

 a project section with a list of all past projects I've worked on and finally。

 a contact me section to allow visitors to contact me by filling out a simple form。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_3.png)

![](img/5d4d391f3fe87b55bc648a06ce009ed7_4.png)

Finally， theres a footter at the bottom。This application level layout is defined at the entry point。

 the app do Js component。 Besides the two providers at the top。

 everything inside the main tag translates to the different two I boxes that I described previously。

 header， landing section， project section， Contact me section， footer and alert。

 The alert component plays the role of a global dial that I can trigger from anywhere in the application using react context。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_6.png)

Let's go into each section top to bottom， starting with the header components。

 Its rendering section begins to illustrate one of the compelling points from the Chkra UI library。

 First， Chra provides you with generic boxes like box H stack for horizontal stacks or rows and V stacks for vertical stacks or columns that use the special children prop to place their content。

 as you wish， using properties such as padding， margin or spacing。Secondly。

 Chakra uses props for all CSS styles as well as additional ones like spacing to evenly separate a group of childrens siblings or in other words。

 add similar gaps between them。I'm rendering a list of social icons using the map function。

 picking as key their URL， which is unique per item。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_8.png)

![](img/5d4d391f3fe87b55bc648a06ce009ed7_9.png)

Now， if you examine this rendering， you will find two of the core react hooks use Ref and Use effect。

 Those two are used in conjunction to achieve the smooth animation of the header。

 you can find out more about the implementation details in a further reading。Okay。

 let's now check the next component landing section。

 There is nothing particularly special about this component。

 It's just a presentational component that encompasses the whole screen height and lant image and text in the center。

 Still， there is a great component I created that uses some of the techniques you have learned the full screen section component。

 Heres a component that leverages both the children prop and the spread operator。

Its goal is pretty simple to create a full screen container box with 1280 pixels as width with a specific background color and text color。

 depending on whether the background is dark or light。

 The spread operator allows you to pass down other layout props to the vertical stack components in case you would need further customization。

Next there is project section， this is another presentational component that renders all my featured projects in a grid layout。

And finally， I will move on to the star of the show to Contact me section components。

 This is probably the most interesting component of them all since it implements a controlled form with validation and handles some aspects of internal state。

To simplify the form business logic， I have decided to use another library that is well known within the react community。

 Formic。Foric is the most popular open source form library for React and it stands out due to its declarative nature。

 allowing you to spend less time wiring up state and change handlers and more time focusing on your business logic。

Looking at the application， I have added four inputs， one text input for the first name。

 another text input for the email， I select input to pick the type of inquiry and finally a common text area。

To define the configuration of the form， you would have to use the use formic hook。

This hook takes a configuration object that is intuitive and easy to follow。

 Iitial values defines the initial state of the form On submitit is a function that will be executed once users click on the submit button and validation schema specifies the validation rules for this form on the client side。

 Formmic works very nicely in conjunction with Yup。

 A library that lets you define your validation in a declarative way using a chain of operators。

The hook returns a formic object。 That is what you have to use to wire up your inputs with the formic internal state。

 Now， let's explore the business of rendering。 I have grouped each input into a form control component。

 which is imported from chakra。 For example， the first name has a label。

 the input itself and a component to display any error messages occurring for that particular input。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_11.png)

The is invalid prop in the form control determines whether the error message is shown or not for the first name。

 it would happen if there is an error according to its validation rules， and it has been touched。

 meaning the user has already focused the input at least once。 and the input component。

 I would have to hook the state and change handlers by using formic dot get field props with a value of first name as the parameter。

 which would have to match the property name used an initial values and spreading the results。

 which is an object with all the props you need to connect from Formic。 So if I go to the form。

 Fo the first name input and then blur it an error message pops up on the bottom with the hint required。

 Nice， isn't it。The remaining inputs follow a similar patterns。 I won't focus too much on them。

 Finally， we have the form submission。 Remember the on submitubm property from the use formmic hook configuration。

 That's the function that will be called when the form is submitted。 In that function。

 an API call is performed to the endpoint to submit the form along with a form values。 Finally。

 they use effect hook listens to changes in the response value。 And once the server responds。

 it will open an alert showing a dialogue with a confirmation or an error message。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_13.png)

![](img/5d4d391f3fe87b55bc648a06ce009ed7_14.png)

This API call is just a simulation for the purpose of the exercise and is programmed in a way that has 50% chance of being successful。

If the response is successful， the form is reset and cleared using the reset form function from the formic object。

 Well， let's explore the form in action。 I will fill the form with values， click submit。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_16.png)

And wa， here is the alert， we can try again to show the opposite state。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_18.png)

So there you have it， this is one possible solution to the portfolio exercise。

 I'm really looking forward to seeing which approach you took to complete this challenge。



![](img/5d4d391f3fe87b55bc648a06ce009ed7_20.png)