# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P65：23_什么是 useReducer,它与 useState 有何不同.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

By now， you should have a fairly good understanding of the U state hook and be able to practically apply it to your solutions。

 However， the U state hook does have its limitations， For example。

 the U state hook may become cumbersome if you have complex state logic that involves multiple subvalues or when the next state depends on the previous one。

In these situations， the use reducer hook can provide a much better alternative。In this video。

 you'll learn more about use reducer and how it differs from use state。

 You can think of the use reducer as a super powered use state。

 The use state hook starts with an initial state， but the use reducer hook gets a reducer function in addition to the initial state。

😊，This is beneficial because the reducer function second argument is the action object。

 This object has multiple type values， and based on each of these types values。

 you can invoke the dispatch function to perform a specific operation。Now。

 say the little Lemon restaurant is growing in popularity and demand， and as a result。

 keeping track of expenses is becoming an issue。So far。

 they have been calculating the income and outgoings manually as they sell meals to their customers and by ingredients to replenish the stock。

 Little Le is looking for a solution to this using react in order to keep track of expenses in their app and reduce the burden on their staff。



![](img/cfeddea12d5c370bbabbf9227bc05af3_1.png)

Because using the use state hook would make the solution to this unnecessarily extensive。

 this is a perfect opportunity to implement the use reducer hook in order to simply keep track of the cost of buying ingredients and the income generated from selling the finished meals to the customers。

Now let's explore how to implement the Use Redr hook in a code example to reinforce your understanding。

Imagine I am coding the expenses tracking application for Little Le discussed earlier using React and Use Redr。

With this app， I can track two actions， the cost of buying ingredients to prepare the meals in the little Le restaurant and the income from selling the finished meals to the customers in the restaurant。

 for the sake of simplicity， I've only added two actions。 Bu ingredients and sell meals。😊。

The reducer function takes in the previous state and an action and returns the new state。

 The action type determines the specific action of the reducer。

 Actions can have any form By convention， It's common to pass objects with a type property identifying the action。

 It should include the minimal necessary information that the reducer needs to compute the next state。

 You can find out more about extracting state logic into a reducer in the additional readings at the end of this lesson。

Instead of using set state like the use state hook。

 you use the dispatch method of the use reducer hook。

 This accepts an object literal with a single property called type set to a matching action dot type whose behavior is defined inside the reducer function。

As I'm already serving this app in the browser， let me demonstrate how it works When I press the shopping forveggies button。

 the amount in the wallet decreases by 10， and when I press the serve a meal to the customer。

 the amount in the wallet increases by 10。

![](img/cfeddea12d5c370bbabbf9227bc05af3_3.png)

With used reducer， you can define more types as many as you need。 This way。

 you can easily work with more complex logic in your react apps。

 something that might be too difficult to rationalize when using use state。

 to explore this in practice。 Let's add another action type。 I'll name it celebrity visit。

 This action should be triggered when a celebrity visits the restaurant。

 which brings in $5000 to the restaurant when it happens。 to make this work。

 I've added another action type to the reducer function。 And then another button to trigger it。😊。



![](img/cfeddea12d5c370bbabbf9227bc05af3_5.png)

![](img/cfeddea12d5c370bbabbf9227bc05af3_6.png)

I'll save my changes and preview the updated app in the browser。There， it's all working as intended。

 clicking the celebrity visit button increases the wallet amount by 5000。 And it's as simple as that。

 Now， the little Lemon restaurant will be able to keep track of their expenses so that they have a clear view of how much profit they're making from their business。

😊，In this video， you have learned about the Use Redr hook， how it differs from the use state hook。

 and why you can be a beneficial and more efficient solution in certain circumstances。



![](img/cfeddea12d5c370bbabbf9227bc05af3_8.png)