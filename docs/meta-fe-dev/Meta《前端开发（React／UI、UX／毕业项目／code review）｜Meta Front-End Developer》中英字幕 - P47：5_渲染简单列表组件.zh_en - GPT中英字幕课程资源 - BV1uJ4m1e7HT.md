# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P47：5_渲染简单列表组件.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

Did you know that with React， you can transform any list of items into a collection of react components？

So drawing upon the previous example of Little Le's list of desserts。

 imagine the restaurant would like to go one step further by providing its online visitors with a sneak peek at the best desserts in a dedicated section to encourage them to order。

 Well， in this video， you will learn how to display a collection of elements like this with react by using the map function and JsX syntax。

 recall that JsX is a special syntax extension to jascript The react uses to describe user interfaces or UIs and that a component is a function that returns Jsx。

😊。

![](img/d1d104a8cab791a80caf6e17823c5ef4_1.png)

Now， let's explore how to render a list of elements with Re。In this demonstration。

 I will use the list of little lemons best desserts again。 each one having the following properties。

 I D， title， image， description and price。 The aim is to display a simpler version of this collection of top desserts by displaying just the title and the price。

 The first step is to create a new variable called list items to store the result of the transformation I am going to perform。

For that， I am going to loop through the array of desserts using the JavaScript map function。😊。

You may be wondering what it should return inside the map function。 Traditionally in jascript。

 you would return any data type when you were working with lists in JsX。

 you can also return a react component as the transformation applied to each element。

 You will discover how that's useful later on since you will be able to embed the result directly into the return JsX。

Recall also that all HTML tags are components by default。

 so you can leverage all the semantic tags you already know from HTML。For list items。

 your best choice is the list item or LI semantic tag。

I am going to return an empty list item for now。Because the goal is to display the title of the dessert and its price。

 I am first going to create a new variable for the text named item text。

I will use a dash to separate title and price， as well as the dot notation to access the needed properties from the dessert object。

 which are title and price。 Since this is a JsX transformation that will be part of the render method of this component。

 you have to use curly braces to wrap your data。 In this case， the text for each list item。

 which is the value of our variable item text。 The last step is to go to the render method and embed list items into the Hm list wrapper component。

 unordered list or U。

![](img/d1d104a8cab791a80caf6e17823c5ef4_3.png)

And that's it。 The desserts are displayed in a simple and concise way。

This edition will certainly help Little lemonmon restaurants to increase its orders， so well done。



![](img/d1d104a8cab791a80caf6e17823c5ef4_5.png)

You have learned how to transform collections of elements with react by using a combination of the map function and JSX curly braces。

 with lists being one of the core building blocks of app development。

 you're now one step further in your journey to creating great apps。😊。

