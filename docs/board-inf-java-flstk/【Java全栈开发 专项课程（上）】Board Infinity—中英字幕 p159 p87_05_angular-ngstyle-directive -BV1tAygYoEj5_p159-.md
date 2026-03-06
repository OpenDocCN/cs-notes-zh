# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p159 p87_05_angular-ngstyle-directive -BV1tAygYoEj5_p159-

H there In the previous video， we learned about Angular N G IF directive。 Now， on this video。

 we will understand Nng style directive。 So let's get started。

The Nng style directive is used to apply inline CS styles to an element based on the expressions in the component。

It allows you to dynamically set the style properties of an element based on specific conditions or data values。

Let's try to understand this， using an example。

![](img/96e34e555263f47cf5aa12296c6d0d3e_1.png)

So let's go to the VS code。 I have here the basic angular project ready。

 and you can see I am currently in app dot component or Ts file。An inside。The app component。

 you can see we have template linked here。So how to add Nng style directive is lets go to app dot component dot Sml and let's say we have a div here。

So you can just add N style like this and whatever the style that you want to add。

 you can add it here。Like this。So this is kind of the syntax of using an Nng type。Here。

 the Nng style directive is applied to an element using this square brackets。

 and it accepts an expression that evaluates to an object containing the CSS style。

 so this styles is an object。The expression is then evaluated in the component。

 and the resulting object is used to apply the corresponding styles to the element。

The styles object can be dynamically generated based on conditions。

 calculations or data values of the component。 So let's create an example here。

So we have a div of N style， and here let's give an object。And into this object。

Let's give it some styles。So first， let's say font。Size， and let's give it。Dot p，x。

let me make it to double quotes because we are using single quotes inside。After this。

 we can again say font size。And then， we can see color。So this color would be coming from。对了。

And now we can see inside the stiff。So here we have color and font color。 And here we only want one。

Gs。So now we can see this。Next is。Style dynamic。And now what we can do is where are these font color and font size coming from。

So lets go to add dot component dot Ts and let's create the font size here。

So let's say font size is a number。And let's view the number as 16。 So that would be 16 pixels。

And then we can say font color。And font color would be a spring。 And let's give it a black color。

So let's stay on save now， and let's go here。You can see that this text is styled dynamically。

 Let's try to give it a green color。

![](img/96e34e555263f47cf5aa12296c6d0d3e_3.png)

And now you can see the color has been changed。

![](img/96e34e555263f47cf5aa12296c6d0d3e_5.png)

So you can see that we have used here the N D style directive。

And you can make it more enhanced by using multiple things here。 So let's say。After this div。

 we can have a label and into this label， let's just say font size。And after this。

 we can create a input。And let's give it a type of number。And to this input。

 we can connect it with our engine model。And， let's give it。Fn size。And then， we can say。Liban。

And here we can see font color。Let's give some spacing。 And then。Let's go here。

 Let's create input of type。Next。And again， let's use N model。That would be inside parentheses。

 and let's make it equal to font color。Now， when we use N model， let's see we have your form as well。

 So lets go to Abt module。 So we have forms module already imported here so make sure that it is importanted。

So now let's test this out。 if I go here and if I change this to。



![](img/96e34e555263f47cf5aa12296c6d0d3e_7.png)

20， you can see it is getting bigger。Right， let's give 100。 the text has become bigger。

 And if we change it to black。It takes the black color， red， It takes the red color， right。

 So this is now a working example that we have created。



![](img/96e34e555263f47cf5aa12296c6d0d3e_9.png)

So in this example， we have a de element that is styled dynamically using this Nng style directive。

 The font size and color styles are set based on the font size and font color properties in the component。

 So we have created these properties in the component。

And then we have these two input fields that are provided to allow the user to change the font size and font color dynamic。

Here we have also used the Nng model directive。For two way data binding。

 ensuring that the component properties that is font size and font colour。

Are updated with the user's input。So as the users enter the p numeric value in the font size input and a value CSss color value in the font color input。

 the styles of element will be updated dynamically here， as you can see。

So this is how you can use N G style directive and。



![](img/96e34e555263f47cf5aa12296c6d0d3e_11.png)

Render the inline styles dynamically。 This is all for this video。 See you in the next video。

 Thank you。

![](img/96e34e555263f47cf5aa12296c6d0d3e_13.png)