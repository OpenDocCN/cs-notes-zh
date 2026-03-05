# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p150 p78_02_angular-data-binding-one-way-and-two-way-data-binding -BV1tAygYoEj5_p150-

Okay。Hi there。 In this video， we will learn about angular data binding。

 and we will also see one way and two way data binding in Angular。 So let's get started。

So angular data binding is a feature that establish a connection between your application data and the user interface。

It basically allows you to automatically synchronize data between the component and the view that is your HTMLml。

Ensuring that changes in one are reflected in other。There are two types of data mining in angular。

We have one way data binding， so data flows in a single direction。

That means either from one component to the view or from the view to the component。

There are actually three types of one way data binding。

So we have interpolation that binds the component properties or variables directly into the template using double curly brackets。

Then we have property binding， it sets the value of an HTMLl property。Based on a component property。

 using square packages。Then we have attribute binding。

 It sets the value of an HTMLtml elements attribute using A Ttr prefix and square brackets。

Next is two way data mining。So data is synchronized in both directions in this case between the component and the view。

 it uses Nng model directive to bind the value of an input element to a component property。So。

 let's see how we can。Create or use both one way and to be binding。



![](img/805f9d0d0e9863ae8bc129d7a386e0b6_1.png)

So here I am in my Angular project。And let's create a basic variable。

 and let's first focus on one way binding。So， lets say we are creating a status variable and it is currently a project status you can assume and the status is pending for now。



![](img/805f9d0d0e9863ae8bc129d7a386e0b6_3.png)

So if you want to display it in the view， currently we don't have anything here。



![](img/805f9d0d0e9863ae8bc129d7a386e0b6_5.png)

So what we can do is we can go to our HTML Ml page and we can use this interpolation。

And we can pass the variable that is status in this case。 and then we can say。Project。Status is。This。

 and let's include it inside a paragraph tag。

![](img/805f9d0d0e9863ae8bc129d7a386e0b6_7.png)

So now if I click on save you will see that the data that is status spending has flow from the component or Ts to the Sm。

 so this is one way data binding。

![](img/805f9d0d0e9863ae8bc129d7a386e0b6_9.png)

Let's see two way data binding at this point。So assume that we have input。

Or lets say we are giving user an option to enter the country name。So in that case。

 we can offer an input。And the type， let's give it text。And here we can use engine model like this。

So， we can say N G。Model。And we can make it equal to the country。

 So this is the variable name that we will create in the component part。And then， we can say。

On change。I want to。Invoke a function。 So let's call the function as displayed。Country。

And let's call it here。And now we want to create this variable and this function。

 So lets go to our app component or Ts。And here we can create our country variable so we can see country。

And， let's give it。US。And then what we can do is we can say display。Country， that is the function。

 and we are declaring it here。And let's just say。Consue dot lock。This taught country。So now。

 if I click on save。

![](img/805f9d0d0e9863ae8bc129d7a386e0b6_11.png)

You can see that we have opening tag is not terminated。

 so we have to go here and close this input as well。



![](img/805f9d0d0e9863ae8bc129d7a386e0b6_13.png)

![](img/805f9d0d0e9863ae8bc129d7a386e0b6_14.png)

Okay， so to solve this error。 First of all， it is parentheesis here normal。



![](img/805f9d0d0e9863ae8bc129d7a386e0b6_16.png)

And still， you will see we get this error because we need to import another module。

 and that is forms module。So make sure that you import it here as well。And now if I click on save。

Let's go to our HTMLml and let's try to run this again。 You can see it compiled successfully。



![](img/805f9d0d0e9863ae8bc129d7a386e0b6_18.png)

And here we have the output here by the default value of US。So if I go to console。And here。

 let's try to try something。Whatever we type。We should get this。



![](img/805f9d0d0e9863ae8bc129d7a386e0b6_20.png)

And this function should run here。 That is display country in this case。

So this is what is2 way binding and let's summarize this。



![](img/805f9d0d0e9863ae8bc129d7a386e0b6_22.png)

So by leveraging the data binding， you can easily update and reflect changes in your applications data in the UI and vice versa。

It simplifies the development of dynamic and interactive applications。

 making it easier to manage and manipulate data within your angular application。

This is all for this video In the next video， we will learn about angular interpolation。

See you in the next video。 Thank you。🎼。

![](img/805f9d0d0e9863ae8bc129d7a386e0b6_24.png)