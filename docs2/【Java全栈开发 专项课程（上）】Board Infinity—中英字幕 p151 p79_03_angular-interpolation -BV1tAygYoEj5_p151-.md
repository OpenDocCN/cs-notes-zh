# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p151 p79_03_angular-interpolation -BV1tAygYoEj5_p151-

Hi there in the previous video we learned about angular data binding and specifically we discussed on one way and two way data binding。

Now， in this video we will understand about angular interpolation。So let's get started。

So interpolation is a type of one weight data binding in angular that allows you to bind component properties or variables directly into the template markup。

It is noted by double curly brace， as you can see here。Interposition can work in multiple ways。

 So the first way that it can work with is kind of binding component properties。So in this case。

 you can bind component properties directly into the template using interpolation。

 the property value will be evaluated and displayed in the template。😊，Let's create an example。



![](img/86d4045322a5afe70ccbf45c79bdeb4d_1.png)

So I am here in my angular application inside the file app dot component or Ts。

So here rather than template URL， lets pass a basic template。And here in this。

You can use this backts。Let's put up comma。 And then what we can do is let's put a template here。

So let's say we have an H1， and we want to。Render a title here。So where is this title？So。

 what we can do is we can create a title variable at this point。So we can say welcome to angular。

Next， what we can do is we can also have a message if you want， So let's create a message variable。

And this would be， this is an example。Of interpoition。

So how to render this in the UI here we can use this interpretations。C the braces。

 and you can pass title here。Similarly， we can say P。And let's close the speed tag。

And let's put up message here。So if I click on save， lets go here。

 you can see that both of the things have been rendered in the HTMLM。



![](img/86d4045322a5afe70ccbf45c79bdeb4d_3.png)

So， in this example the title and message properties are defined here in the component and within the template the properties are enclosed here in double curly braces。



![](img/86d4045322a5afe70ccbf45c79bdeb4d_5.png)

![](img/86d4045322a5afe70ccbf45c79bdeb4d_6.png)

The value of these properties will be dynamically interpolateulated and displayed here in the SM page。



![](img/86d4045322a5afe70ccbf45c79bdeb4d_8.png)

Next type of interpolation is。You can say expression evaluation。

So in this case interpretationpo allows you to evaluate expressions also in the template。

 you can perform simple operations or include method calls within the input interpolation synax。



![](img/86d4045322a5afe70ccbf45c79bdeb4d_10.png)

For example。We have your let say message。As welcome to Angular。And here in the template。Let's say。

 the length。哦。The message。This， we can say message dot length。

 So this is evaluating the length of this particular string。You can also have something like。

 we can say。The result of。2 plus 2。Is， and then we can evaluate the expression。 that is 2 plus 2。

And lets close the pret which will evaluate into this interpolation。So if I click on save now。

 you will see that we have the result of two plus2 is 4 and the length of the message is 80。



![](img/86d4045322a5afe70ccbf45c79bdeb4d_12.png)

![](img/86d4045322a5afe70ccbf45c79bdeb4d_13.png)

So in this example， again， we use interpolation to perform arithmetic operation and access the length of the message。



![](img/86d4045322a5afe70ccbf45c79bdeb4d_15.png)

These expressions within the interpolation are evaluated and the results are displayed here in the template。

😊。

![](img/86d4045322a5afe70ccbf45c79bdeb4d_17.png)

So interpoulation is a convenient way to display dynamic data in the template。

 It allows you to seamlessly incorporate component properties， variables and expressions into the UI。

 making your application more interactive and responsive。

 Remember that interpolation is a one way data binding。

 meaning that it only displays the component data in the UI。

 It does not update the component data if changes are made in the Ui。

🎼This is all for this video In the next video we will learn about Angular property binding。

 See you in the next video。 Thank you。

![](img/86d4045322a5afe70ccbf45c79bdeb4d_19.png)