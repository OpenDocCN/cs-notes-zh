# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P73：31_React 中的跨切面关注点.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

When building react applications， you will find yourself creating some generic functionality that is not related to the application's business logic and that is needed in many places。

 For example， think about managing different permission roles， handling errors or even logging。

 They are all required for any application， but are not necessary from the business point of view。



![](img/275fc627765b99646c642293d50c87c4_1.png)

![](img/275fc627765b99646c642293d50c87c4_2.png)

This group of functionality is what falls into the category of cross cutting concerns。 In this video。

 you are going to learn about cross cutting concerns and why components。

 despite being the primary unit of code reuse and react aren't always a good choice for this kind of logic。

 You will also discover why new patterns were introduced to solve this problem。

 excited to learn more。 Well， let's get started。😊。

![](img/275fc627765b99646c642293d50c87c4_4.png)

![](img/275fc627765b99646c642293d50c87c4_5.png)

![](img/275fc627765b99646c642293d50c87c4_6.png)

![](img/275fc627765b99646c642293d50c87c4_7.png)

Imagine that you are tasked with building the logic to display a list of live orders for the Little Lemon Restaurant app。

Let's explore how this could be achieved。 Here is a valid implementation for a live orders list where local state is used for storing the current list of orders and use effect handles both the subscription and unsubscription to the live data。

 updating the order's value as soon as a new order arrives。



![](img/275fc627765b99646c642293d50c87c4_9.png)

![](img/275fc627765b99646c642293d50c87c4_10.png)

![](img/275fc627765b99646c642293d50c87c4_11.png)

Now， imagine that little Lemon also needs a place in the application to keep track of the number of users subscribing to its newsletter in real time。



![](img/275fc627765b99646c642293d50c87c4_13.png)

![](img/275fc627765b99646c642293d50c87c4_14.png)

This could be a valid implementation for such functionality。

 Can you identify any similarities between live orders list and newsletter list。



![](img/275fc627765b99646c642293d50c87c4_16.png)

They are definitely not identical since they call different methods on data source and render a different output。

 But much of the implementation is the same upon examination。

 they both add a change listener to data source on mount。

 set new state whenever the data source changes and remove the change listener on Unmount。

 You can imagine that in a large app， the same pattern of subscribing to data source and setting local state with new data will occur over and over again。

 So far， you have seen that a custom hook to encapsulate that logic is one of the solutions at your disposal。



![](img/275fc627765b99646c642293d50c87c4_18.png)

![](img/275fc627765b99646c642293d50c87c4_19.png)

However， that introduces the issue of having to alter the implementation of each component that needs that data and thus making all of them stateful。

 So how could you define the subscription logic in a single place。

 share it across many components and keep them unchanged and stateless。



![](img/275fc627765b99646c642293d50c87c4_21.png)

Well， this is where higher order components are a perfect solution。

 a higher order component also known as a HOC is an advanced pattern that emerges from reacts compositional nature。

 specifically a higher order component is a function that takes a component and returns a new component whereas a component transforms props into UI。

 a higher order component transforms a component into another component。 In other words。

 it enhances or extends the capabilities of the component provided。



![](img/275fc627765b99646c642293d50c87c4_23.png)

![](img/275fc627765b99646c642293d50c87c4_24.png)

![](img/275fc627765b99646c642293d50c87c4_25.png)

![](img/275fc627765b99646c642293d50c87c4_26.png)

Let's go ahead and examine how the implementation of this reusable subscription logic would look with a higher order component with subscription is the higher order component that takes the wrapped component you would like to enhance with subscription capabilities。

 as well as a select data function to determine the type of data you are getting from the data source In this case。

 either orders or users with subscription then returns a new component that renders the provided component and supplies a new prop to it called data that will contain the most recent list of items from the data source of interest。

 It also passes other props through to the wrapped component， which is a convention in HOCs。



![](img/275fc627765b99646c642293d50c87c4_28.png)

![](img/275fc627765b99646c642293d50c87c4_29.png)

![](img/275fc627765b99646c642293d50c87c4_30.png)

![](img/275fc627765b99646c642293d50c87c4_31.png)

![](img/275fc627765b99646c642293d50c87c4_32.png)

![](img/275fc627765b99646c642293d50c87c4_33.png)

That's the implementation， but how about its usage？In this case。

 you would define two different components configured with custom parameters。

 one for live orders and another for newsletter subscribers。

 all without having to repeat the subscription implementation in either live orders and user list。

 making this a much more efficient solution。

![](img/275fc627765b99646c642293d50c87c4_35.png)

There is still one more pattern for cross cutting concerns that you will learn about soon。

 called render props。

![](img/275fc627765b99646c642293d50c87c4_37.png)

Great in this video you have learned about crosscutting concerns and why components are not always enough for reusing behavior you've also explored one alternative pattern to encapsulate common behavior and react applications。

 which are higher order components。