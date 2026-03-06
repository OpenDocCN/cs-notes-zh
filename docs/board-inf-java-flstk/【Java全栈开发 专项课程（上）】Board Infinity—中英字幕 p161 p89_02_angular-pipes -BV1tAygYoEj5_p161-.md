# 【Java全栈开发 专项课程（上）】Board Infinity—中英字幕 p161 p89_02_angular-pipes -BV1tAygYoEj5_p161-

I did。In this video， we will learn angular pipes。So let's get started。

So pipes in angular are a way to transform and format data for display in the template。

 They are used to perform common data manipulation tasks such as filtering。

 sorting and formatting value。 pipes are marked using this character in the template syntax。

 So let's try to understand this using an example。

![](img/7b3959651cb694d45cd997cc1504171c_1.png)

So let's go to the VS code here I have a basic angular project ready。

And currently I am in app dot component or Ts5 So inside the app component。

 I will create a bunch of variables。Let's say we create a value variable that would take the value string。

And let's provide the value as hello。Angular， in this case。

Then let's also create a variable current date。And this would be taking a date。And left。

Call the new date constructor like this。And this will hold the new data object。

Lets also have one more variable amount。 And in this case， this would be number。And initially。

 let's give it 99。99。Now again， this is connected with our template URL that is app dotcomp。 HTMLml。

 so let's make changes there。So let's go to this file Ab dot component dot html and lets。

Write some template here。So inside this， let's create a P tag and let's say， original。Value。To be。

 let's use interpolation。And value。Next， we can say uppercase。And what case would be。Again。

 we can use interpolation and we can say value。And using this pipe symbol。A bugs。Next。Let's set date。

And again， let's use interpolation。And we can see。Current date。And let's use this， set Ds。

And it to be medium。Let's have one more P tag for a amount。And this， again， lets use interpolation。

And let's say， amount。And currency。So it should be， let's say， USD。And let's also put true here。

So in this example， we have a component here with three properties value current and amount。

 Now these properties hold the values to be transformed using angular pipe。

 So lets see the transform values。 lets click on save。



![](img/7b3959651cb694d45cd997cc1504171c_3.png)

And you can see we have uppercase， the date and amount。



![](img/7b3959651cb694d45cd997cc1504171c_5.png)

And the template。So the value property is being transformed to uppercase using the uppercase pipe。

 as you can see here。The current property is formatted as the date using the date pipe with the medium format。

 and the amount property is displayed as a currency value in USD using the currency pipe。



![](img/7b3959651cb694d45cd997cc1504171c_7.png)

So these transform values are displayed then here in the template。

And this is how you can use angular pipes to format and present data in a desired way。

 So this is all for this video in the next video， we will learn about angular forms。

 See you in the next video。 Thank you。

![](img/7b3959651cb694d45cd997cc1504171c_9.png)