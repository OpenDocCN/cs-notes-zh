# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P51：9_在 React 中创建表单组件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Forms may look simple， but there are many different features and functionality to forms。

 And for developers， there is an art to constructing forms。

 React makes constructing and customizing forms much easier for developers。

 And that's why it's such a popular choice。 Would you like to master the art of building forms with react。

 Well， there are some key concepts and features that you will need to learn to truly unlock the versatility and effectiveness of controlled components and forms using react。

The Little Lemon Restrant Online webage was created some time ago。

 while little Lemon were happy with the results for some time。

 they started realizing their users were having issues with their old contact form。

After receiving some advice， they concluded that it needs to be rebuilt and they have chosen React as the most suitable framework for the task due to the ability to easily apply the features。

 functionality and control that they require from the form。In this video。

 you'll learn how to help little lemon by creating a controlled component and react。

 using local state and the onchan event to update form inputs。

 avoiding the default behavior of the form submit event and disabling the submit button when the form is not valid。

 recall the controlled components and react are those in which form data is handled by the components state。

 whereas uncontrolled components are those in which the form data is handled by the Dom itself。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_1.png)

To gain more insight into creating form components in Re。

 you will now examine the code of a basic form example。

I am going to demonstrate the creation of form components in react using an app I constructed previously。

In this example， the project has been created with createate React app。

 The return method of this functional component essentially has a form that contains two elements。

 a text input to type a username and a submit button。This form resembles a classic HTML version。

 so it'll work the same way whether you're using React or not。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_3.png)

To test the application， I type John as the name and click on the submit button。By doing so。

 the default action of the form kicks in， which is a get request to the root and a page refresh。

In react， this currentt implementation is considered an uncontrolled form。

 having all the states living in the dom。 Let's work through the necessary steps to transform this form into a controlled version。

 First， I need to create some local state for the text input， which I am going to call name。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_5.png)

Secondly， I need to hook up that stage to my text input via two props。

 the value prop to turn the input into a controlled one。

 and on change to receive all the changes per keystroke and thus update the state of my input。Last。

 to control the submission of the form， I have to use the on submitubmit Pro in the form tag。For now。

 I'll log a basic message stating that the submission was successful to the console。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_7.png)

Now let's check if the form still works as before， I'll type a name and click Submit。😊。

And it's working My message was logged to the console and the default behavior of the form has continued on。

Although this is great， I'd actually like to have more control on the submission of the form in particular。

 I'm not interested in the default behavior of calling the root of the server and refreshing the page。

😊，You may be wondering how I can prevent that from happening。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_9.png)

In traditional forms， you would do this by returning false from the unubmit attribute。 However。

 in react， the way to do it is by using the event property you get as a parameter in the un submitubmit callback and calling preventvent default on it。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_11.png)

Now， when I submit my form again， no refresh happens and no server is hit with a request。

Let's go one step further and clear out the input after submission for that。

 I call the state setter with an empty string inside the on submitm callback。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_13.png)

Great， my form is taking shape to demonstrate even more benefits of controlled components。

 Let's perform an additional improvement by only allowing the user to submit the form when the text input is not empty。

 Disabling the button is as easy as using the disabled attribute。 In this case。

 if name is an empty string。 This expression would be evaluated as true。

 and the button would be disabled。😊，So in the app， I can't click on the button if there's no name provided。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_15.png)

Finally， for best accessibility practices， let's connect the label with the input I set an ID for my input called name and now I will connect the label。

😊。

![](img/459d8c5f2f53567ce37ba7f4ef81ea64_17.png)

In traditional HTML forms， you would have to use the four property， but in Re，4 is a reserved word。

 so you must use HTML4 and pass the ID of the input。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_19.png)

Now if I click on the label， its corresponding input is focused。



![](img/459d8c5f2f53567ce37ba7f4ef81ea64_21.png)

And that's it regarding the basics of controlled forms in react。

 you have learned how to transform an uncontrolled form into a controlleded version using local state and the on change event。

 as well as the on submit prop and some of the benefits of doing so。In terms of form submission。

 you also learned how to avoid default behavior and disable the submit button when the form is invalid。

 Well done。 You're making great progress。