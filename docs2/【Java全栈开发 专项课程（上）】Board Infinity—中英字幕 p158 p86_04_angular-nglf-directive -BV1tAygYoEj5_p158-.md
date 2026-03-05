# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p158 p86_04_angular-nglf-directive -BV1tAygYoEj5_p158-

Hi there。In the previous video， we learned about angular structural directives。 Now in this video。

 we will understand N G IF directive。So let's get started。

The N GF directive is used to conditionally render elements in the dom based on a particular condition。

It evaluates an expression。 And if the expression is truthy， the element is rendered。

 and if the expression is fy， the element is removed from the dot。

 Let's try to understand this with the help of an example。

So let's go to the Vs code here I have basic angular setup readyy and I am currently in my app dot component dot Ts5。



![](img/b83f4db66538c0ac3c35f15ea838b074_1.png)

So first of all， inside the app component， let's create a variable show message。

And the show message would be bullolean。And let's give it the value as initially true。Next。

 we can create a method。 Let's call it as struggle message。And this method。

 what it will do is it will just。You can say change the value of the shoe message variable。

So we can see this thought show message to be the opposite of this thought show message。

 so that means if the show message is true， it will make it false and if it is false it will make it true。



![](img/b83f4db66538c0ac3c35f15ea838b074_3.png)

So let's click on save Connect you can see we do not have any output here because these are just logical part。

 So let's actually try to use this using Nng F directive。



![](img/b83f4db66538c0ac3c35f15ea838b074_5.png)

So let's go to app。tcompent。html。An inciitive。Let's say we have an H2 here。

 and let's also create a pre tag。Now here we will mention the NGIF directive like this using atray。

So we can say N G I F。Equals to show。Message。Based on this variable。

 it will evaluate the condition and then it will execute the code。So here we can see this。

Message is rendered。Conditionally， something like that。

And then we can just have a button for the toggle effect。 So for now， let's test this out。

 So if I click on save， you can see that we have show message here。 right。

 The message is rendered conditionally， Why， because we have set show message22。

 if I make this show message initially as false。😊。

![](img/b83f4db66538c0ac3c35f15ea838b074_7.png)

![](img/b83f4db66538c0ac3c35f15ea838b074_8.png)

![](img/b83f4db66538c0ac3c35f15ea838b074_9.png)

Then that line would not be visible。 So this is how you use an N GF paded。



![](img/b83f4db66538c0ac3c35f15ea838b074_11.png)

然后。Lets make it true only and lets have a button to togg that functionality。

 We already have a function written for that。So we can go here and let's create a button。

And on this button， we can attach or click even。And on this click event， we can just one。

About toggle。Message。Methodd like this。And then you can say toggle message as the。



![](img/b83f4db66538c0ac3c35f15ea838b074_13.png)

Text。So if I click on save， let's test this out。 you can see toggle message。Gos， it comes again。

 goes and comes again。

![](img/b83f4db66538c0ac3c35f15ea838b074_15.png)

So in this particular example， we have。This P element。

 we can say paragraph element that is conditionally rendered based on the value of this show message。

Property in the component。 Initially， it was set to true。 So the paragraph element is displayed。

Then we attach the click even on the button that is bound with toggle message method which toggs the value of the show message property between true and false。

When the button is clicked， it triggers the method and changes the value resulting in the paragraph element being shown or hidden based on the updated value of show message。

So this is how you can use NGf directive that allows you to conditionally render elements based on dynamic conditions providing control over the visibility of content in your angular application。



![](img/b83f4db66538c0ac3c35f15ea838b074_17.png)

This is all for this video In the next video， we will understand about Nng style directive。

See you in the next video。 Thank you。

![](img/b83f4db66538c0ac3c35f15ea838b074_19.png)