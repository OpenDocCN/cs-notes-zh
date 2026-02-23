# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P52：10_创建受控表单组件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Have you recently bought a product through an e-commerce sites。

 or maybe you booked a table at your favorite restaurant？ Well， if so。

 you may have received a friendly email afterwards。

 providing a link to a specific page to provide feedback about the experience。

 This is an example of a feedback form。Now that you're familiar with control components in react。

 I'm going to demonstrate how you can build this functionality yourself。

You will also be using a range input and custom validation as part of building a feedback form。

 Imagine little Lemon， one of the best restaurants in town would like to send their customers a feedback form。

 So let's go ahead and implement a feedback form with react。 Note that in this example。

 the project has been created with C reactact app。 I have also added some initial code that is a form with just a header and a submit button。



![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_1.png)

The requirements for this example are an interface that allows users to provide a score from 0 to 10。

 and an additional comment to tell the chef how delicious the food they enjoyed a few days ago was。

The first step is to implement a control for the score。 There are different ways you can do this。

 but I'm going to go and choose a range input for this use case as it provides the user with a simple slider to do this。

 let's go ahead and create a new diff to wrap the component。

 This will consist of a label that I will name score。

 as well as an input whose type is going to be range。 Ra inputs offer two props to define the range。

 min and max。For this example， I will set the minimum to 0 and the maximum to 10。

The application is now displaying a user friendly slider to provide the score。



![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_3.png)

To wrap up the range component， I need to do two more things。

 turn the input into a controlled component and visually show the numeric value that represents the slider selection For that。

 I will define a new piece of state called score that I will initialize to 10。

 because I know the chef's recipe is usually unbeatable。

 enabling the user to reduce the score down from 10 when they interact with the slider if they want to。



![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_5.png)

Now in the range input I have to use the value prop to hook the state up and use on change to receive the changes and update the state accordingly。

Since I also want the numerical score to be displayed with this slider。

 I'm going to add that information to this score label along with a star so the user interface or UI is clean and concise。



![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_7.png)

Great， the feedback form is starting to take shape。 Now。

 let's implement the second element from the form a widget to provide an additional comment。

 although I could use a text input here， a comment could be very large。

 So a more suitable choice is a text area。

![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_9.png)

For that， I will declare another state variable named comment that will be initialized to an empty string。

For the UI I will create a newD with a label and a text area component for any additional feedback。



![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_11.png)

Now that that is rendered well， I need to hook up the state to the value prop and update the changes via on change。

 And with that， the U I for the feedback form is finished。



![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_13.png)

The last thing I'd like to implement is some validation to ensure a comment is required when the score is equal to or lower than 5。

 and that it should have at least 10 characters。 So the chef receives honest feedback from users that can be used to improve his recipe for that。

 I'm going to use the unsubmit callback on the form component。

 I will call prevent default first to avoid the default Hl form behavior。

 Then I'm going to write an if statement to check if the score is equal to or less than5。

 and the comment has less than 10 characters。 If that's the case。

 I will show an alert to inform the user about the requirement and return from the function。

 Otherwise， the user is good to go， and I will log a message to confirm the successful submission of the feedback。

 It's also a good practice to reset the form values after submission。

 So I'll set both pieces of state to their initial values。



![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_15.png)

And there you go， everything is working well and the submission message is logged into the console。

 You have learned how to build a feedback form with react using controlled components and custom validation to make sure users have a seamless experience。



![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_17.png)

![](img/9f856ffbafdb8e4eeb0689dc7a691c5b_18.png)