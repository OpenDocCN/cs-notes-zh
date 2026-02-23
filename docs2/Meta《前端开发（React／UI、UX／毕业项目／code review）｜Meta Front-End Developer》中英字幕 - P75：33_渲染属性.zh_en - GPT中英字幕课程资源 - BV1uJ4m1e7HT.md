# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P75：33_渲染属性.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

So far， you have learned about a technique called higher order components that is used to encapsulate common functionality。

But it's not the only one available to you。 For example。

 you can choose between different eating utensils， depending on the type of food you're eating。

 some chopsticks for your favorite sushi dish or a fork for a delicious carbonara。

 But there's nothing wrong with using a fork for eating sushi。 After all。

 not everyone has learned how to use chopsticks。 And it's the tool that makes the job easier。

 That matters。Well， this is also the case when it comes to code reusability。

 There are several tools you can use to share code between react components。 And in this video。

 you are going to be introduced to a new one， the render props pattern。

Say the little lemon restaurant is looking for a way to keep count of all the items it has on the menu。

 They would like to display this information in the application so they know when they need to replenish stock and to make it easier for customers to see what is or isn't available at any given time。

That information is stored on a server， so we would have to be fetched first prior to displaying it。

There are various ways to define the fetching logic like a higher order component。 However。

 render props is also a powerful technique you can leverage to reuse common code。

The render prop technique is so appropriately named that it's almost self explanatory。

 It's about using a prop called render with a particular attribute that it has to be a function。

To be more precise， a component with a render prop takes a function that returns a react element and calls that function inside its render logic for example。

 a meal provider component could use this pattern。If you remember。

 a higher order component enhanced a component by providing new props into it with render props。

 However， the new props are injected dynamically as the parameter of the function。

 You may already have recognized some similarities between the two。

 The end goal is the same to enhance components without modifying their original implementation。

 The way in which they inject those new props or enhancements is what differs。



![](img/9b0fb28a7cb513fa006d89bf5e785f4a_1.png)

To better illustrate this point， let's explore an application that showcases the implementation of a component that uses a render prop。

In this example， the little lemonmon restaurant would like to keep account of all the desserts and drinks that it has in the menu。

That information will need to be fetched from a server that they control and displayed in the application with a single piece of text。

 The logic for fetching data is one example of a cross cutting concern。

 Multile components may depend on data that live somewhere else。

 but you don't want to implement the same fetching logic over and over in every component that needs it。

 right。This is a good place to use the render props pattern to abstract this functionality。

To showcase how it works， I have created a component called data Fecher。

 whose only purpose is to fetch data based on a URL。 This is one of its props。

 but it's the second one that should catch your attention。 And that's the render prop。

 I'm not fetching real data in this example。 but I have created a mock if L statement that will return either a list of all desserts or drinks available based on the URL path。

As usual， this fetching logic is a side effect that should be placed inside use effect。Finally。

 let's move to the return statement。This is the unusual part。

 The component is returning the result of calling the render function and has no other rendering business。

 This is what makes it very flexible。 Data fetchcher only has one purpose， Feing data。

 And the way they receive it， is via the argument in the render function。

 which is the local state used to store the list of desserts or drinks。

 It's then up to the developers to decide how they would like to present that data on the screen。

 Finally， let's explore the two presentational components I have defined to show the number of desserts and drinks available in the menu。

😊，The desserts count component uses a particular end point to fetch desserts and uses a paragraph element as the render prop。

 displaying the number of desserts as a single text。 The same applies to the drinks count component。

 with the difference being that it utilizes another URL。

 and instead shows a header element reflecting the number of drinks。



![](img/9b0fb28a7cb513fa006d89bf5e785f4a_3.png)

Finally， the app component renders both of them， and the results are displayed on the screen。



![](img/9b0fb28a7cb513fa006d89bf5e785f4a_5.png)

You have learned about another technique you can use in addition to higher order components。

 which is the render props pattern。Hopefully， now that little lemon keeps a live count of drinks。

 they can replenish their fridge with your favorite refreshments。😊。

