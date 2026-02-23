# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P76：34_为什么使用 React 测试库.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

As the developer for Little Lemon's restaurantrant application。

 how could you guarantee that the app you created works as intended。 Well。

 you may choose to rely on your methodical ability to manually interact with all the different parts of the application yourself。

 ensuring the app is fully functional。 However， manually testing every new incremental change it'd like to make。

 is likely to be tedious。 error prone and time consuming， especially as your app grows in complexity。

That's where automation tests come in。So in this video。

 you will learn how to write tests properly for your react components。

 You will achieve this by exploring why testing is important and best practices when creating tests being introduced to the tools just and react testing library for structuring your tests。

 as well as working through a practical example of testing a component using these tools。

 just like factories perform testing of the products they build to ensure that they work as expected。

 developers need to do the same with their code。 A well designed suite of automation tests is particularly effective in allowing you to discover defects or bugs before delivery to the client。

 In doing so， testing is important for guaranteeing the quality of the software you develop。😊。

Further， by catching bugs before they find their way into a live application。

 testing reduces the number of user complaints and can ultimately save an organization time and money。

Now that you have an idea of why testing is important。

 what are the best practices you need to keep in mind when writing your tests？

The first is that your tests need to avoid including implementation details of your components。

 React is just a tool， and your final users will have no notion that react exists at all。

 So rather than dealing with instances of rendered react components。

 your test should work with actual dom nodes。Secondly。

 the more your test resemble the way your software is used， the more confidence they can give you。

Finally， you'll also want your tests to be maintainable in the long run。

 So as long as you're not changing functionality， any changes in the implementation of the component won't break your tests and slow you and your team down。

Now let's explore the two tools that Re endorses to structure your tests， Jest。

 and the React Test library。Jest is a jascript test runner that lets you access an artificial Dom called JS Dom。

 While JS Dom is only an approximation of how the browser works。

 It is often good enough for testing react components。Jest provides a good iteration speed。

 combined with powerful features like mocking modules。

 so you can have more control over how the code executes。

 recall that mocking refers to something made as an imitation and enables you to replace complex functions from your code with others that are simpler and simulate the same behavior。

 Moing features can be used to make sure that your unit testing is standalone。

 If you'd like to revisit the concept of mocking in greater depth。

 you can check out the additional resources at the end of this lesson。😊。

The second tool is React Test library， which is a set of utilities that let you test react components without relying on their implementation details React testing library has been designed to fulfill all the best practices highlighted before so that you get a well configurefigu testing environment out of the box and are able to focus on the business logic your tests need to run assertions on。



![](img/1bd652d2dad780b49bd180b579df3eaa_1.png)

With a theory covered， let's go ahead and implement a test from scratch using Jest and React Test library。

When you start a new project with Cate React app， you already get both Jest and React testing library preinstalled by default。

 plus both tools are already preconfigured and there is an example test file in your root folder called app。

test。jS。Imagine that little Lemon has made an agreement with a popular restaurant aggregator to have its web page included as a new URL in its listing。

In the app。 JS file， the app component renders a link in the page that points to Little Lemon's webp page。

Let's go through the test I created to automatically verify that the link is always present。

The first thing I need to do is to import both render and screen from the reactact testing library。

The render function is used to render the component you would like to test and perform assertions against because querying the entire document dot body is very common。

 React testing library also exports a screen object。

 which is a reference to that object and has every query prebound to it。

 meaning that it will automatically ask the whole document when running a search。Now。

 to wrap the test scenario， Jest provides the global test function。

 which takes a text description as the first argument and a function to compose all the steps your test needs to go through as a second argument。

 This function does not need to be imported since jest injects it automatically in all your test files。

The first step is to render the app component in the artificial DOM environment。Secondly。

 I use the screen object to create a query against the document dot body。 In this case。

 I am using the get by text utility to ask the body tag of the document if it can find an element inside with a string called Little lemon restaurant and store the result of that finding in the link element object。

 If the search is successful， get by text will return the found element。 Otherwise。

 it will return null。Finally， to complete the test。

 I perform an assertion asking whether the link element from the query above is present in the document。

 meaning whether it's currently visible on the screen。For that， the Global Exp function is used。

 this is another utility that Jest incorporates globally without the need for an explicit import。

The expect function receives the result of a query and appends a specific match。 In this example。

 the match refers to an element visible in the whole document。 If I run the test， it fails。Okay。

 let's check the output logs to try to understand what has gone wrong。

 It states that it was unable to find an element with a text， little lemon restaurant。Interesting。

 let's go ahead and check the app dot JS component again。Aha。

 I had made a mistake and typed orange instead of lemon， something that the test was able to catch。😊。

That's exactly what you want to see when a failure occurs。 Also。

 you might have noticed how straightforward it is to write your test assertions。

 Everything you see in code translates nicely to how a real user would interact with your app and respond with the behavior that you would expect。

Let's run the test again now that the issue is fixed。Great。

 the test passes and little lemons online exposure is about to grow even more。



![](img/1bd652d2dad780b49bd180b579df3eaa_3.png)

In addition to the importance of testing and testing best practices。

 you have now learned how to test your react components using Jest and the React Test library stay tuned because soon you will discover how easy it is to write more complex tests。

