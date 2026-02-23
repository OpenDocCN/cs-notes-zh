# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P68：26_JSX 组件和元素.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

At this point， you may be wondering how to define what JSX actually is。

 and it may not be entirely clear how React works with JSX to describe a UI and produce a user friendly and effective app。

Well， let's explore these concepts in a bit more detail in this video。

 you'll learn how Re uses JsX to describe a U I the differences between components and elements and the general concepts behind the react declarative model。



![](img/6d7a99ade4307f3f8b2cb4209f579218_1.png)

The little Lemon restaurant owners have been happy with their original website for a long time。

 but as they have grown as a business， they now want to add more features， functionality。

 analytics and user interactivity。They are noticing that their original website was built in a way that means there are many limitations when it comes to these types of enhancements。

 After seeking some advice， they have concluded that they should develop an app using J S X and reactact。

 They want to understand more about J S X and react so that they can build a rationale into their business plan。



![](img/6d7a99ade4307f3f8b2cb4209f579218_3.png)

![](img/6d7a99ade4307f3f8b2cb4209f579218_4.png)

So let's get started with JSX JSX is a syntax extension to JavaScript that react uses to describe what the UI should look like。

 however， even though JSX looks like HTML， it's essentially a more powerful abstraction that combines both markup and business logic into an entity called a component。



![](img/6d7a99ade4307f3f8b2cb4209f579218_6.png)

![](img/6d7a99ade4307f3f8b2cb4209f579218_7.png)

![](img/6d7a99ade4307f3f8b2cb4209f579218_8.png)

So what is really happening from the moment you write JSX in your render function until react creates the desired assets for your pages？

To understand all the steps involved， you need to be introduced to the concept of elements in Re。

By now， you already have a good understanding of components and how your entire UI is represented by a tree of them。

You'll also know that the final web pages that React produces are nothing more than pure HTML。

 CSS and JavaScript。

![](img/6d7a99ade4307f3f8b2cb4209f579218_10.png)

When react analyzes your rendering methods from all your components。

 it takes the whole Jsx tree starting from the root and creates an intermediary representation。

 This representation is essentially another tree similar to before。

 but where each node instead of being Jsx is a plain object describing a component instance or dom node and its desired properties。

 This plain object is what react defines as an element。

 An element is just a way to represent the final H output as a plain object。

 It consists primarily of two attributes。 type and props。Type defines the type of node。

 such as a button and props encompasses all the properties the component receives in a single object。

 Ober how the elements can be nested， as in the button example， via the children' property。

 When react creates the entire element tree starting from the root。

 The root element specifies all the child elements as the children prop。

 and each child element does the same thing until it reaches the end of the tree。

What is important about this new structure is that both child and parent elements are just descriptions and not actual instances。

 In other words， they don't refer to anything on the screen when you create them。

 They're just objects， after all。

![](img/6d7a99ade4307f3f8b2cb4209f579218_12.png)

But these objects are easy to traverse and of course， are simpler than the actual dom elements。😊。

So far you have been introduced to an example of a tree transformation with simple dom nodes。

 like a button。In the element tree， this is specified as the type property。

 but the type of an element can also be a function corresponding to a react component。

 Imagine you have created a component to encapsulate the traditional HTML button named submitit button。

In this case， the type property of the element will point to the name of the component。

 This is the fundamental idea of react。 Both user defined components and dom nodes can be nested and mixed with each other in the elementary。

For example， if you were creating a log out process for the Little Lemon Restrant app。

 you could do this with a logout component in JSX。In this logout component。

 the JSX would translate to the following tree of elements。

That allows you to mix and match components and dom elements as the type property without worrying about whether submit button renders to a button。

 a div or something else entirely。 This keeps components decoupled from each other。

 expressing their relationships through composition。

When react sees an element with a function type like the submit button。

 it will know to ask that component what element it renders to with the given props。

 So Re will ask Submit button again what it renders to， and it will transform that into an element。



![](img/6d7a99ade4307f3f8b2cb4209f579218_14.png)

![](img/6d7a99ade4307f3f8b2cb4209f579218_15.png)

React will keep repeating this process until it knows the underlying DOm tag elements for every component on the page。



![](img/6d7a99ade4307f3f8b2cb4209f579218_17.png)

Once Re finishes the process of identifying all user defined components from the tree of elements。

 it will convert them into DOm elements。The result is what is generally known as the virtual dom。

 a jascript alternative representation of the real dom。Now。

 what are the steps involved when there is a new change in your UI First。

 react will take all your JSX and produce a new UI representation as a tree of elements。Second。

 it will compare it with a previous representation that is kept in memory。Third。

 it will calculate the difference in a tree。Recall that since each node in the tree is a JavaScript object。

 this diffing operation is very fast。And finally， based on that difference。

 it will apply the minimum number of changes to the underlying dom nodes in order to process the update。

 And that's it。 You are probably starting to appreciate the beauty of the react declarative programming model。

😊。

![](img/6d7a99ade4307f3f8b2cb4209f579218_19.png)

In this video you have learned how react uses JSX to describe a UI。

 the differences between components and elements and the general concepts behind the react declarative model。

 you have also seen the react transforms your JSX into an internal tree of elements。

 which are just ja objects， and it is that lightweight representation though let's react。

 update your UI in a predictable way while being fast enough for high performance applications。

