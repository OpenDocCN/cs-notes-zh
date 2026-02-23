# Meta《前端开发（React／UI、UX／毕业项目／code review）｜Meta Front-End Developer》中英字幕 - P69：27_性能对软件开发的重要性.zh_en - GPT中英字幕课程资源 - BV1uJ4m1e7HT

So the interesting thing about performance it's one of these things that you can make it or break it with just one line of change。

 I mean， of course sometimes it's possible that in order to improve a performance you have to rewrite an entire application and start over。

 but sometimes small changes make a big difference。🎼，う。My name is Mortara。

 I'm a software engineer at MetaA baseds in the Seattle office。At Meta。

 we really try to think about the different diversity and the different backgrounds that users come from and what technologies they might be using to access our products。

 So thinking about performance can make a big difference between gaining a user or losing a user because if the application is not performing。

 it's not responsive， it's not fast enough then people will not use it so it's a big deal for us to think about performance when we're developing these applications。



![](img/8cce78b988633def63cb97ed89bb918a_1.png)

![](img/8cce78b988633def63cb97ed89bb918a_2.png)

You know it's never that our applications are just performant out of the box and we try to look for the things that can improve their performance。

 performance is usually something that we build incrementally and we get to it by making incremental changes because we may think that this is not important and it's more exciting to build a new feature。

 it's more exciting to make something more colorful and performance is it's kind of invisible thing that you may not notice it right away。

 you may not be able to show it and brag about it， but it's actually really important and it's an underlying part of the application that without it。

 you can't really have the applications。

![](img/8cce78b988633def63cb97ed89bb918a_4.png)

![](img/8cce78b988633def63cb97ed89bb918a_5.png)

You know， one of the things that react does really well and it's kind of what has made it Excel and become so popular is that it's very efficient in building and rendering web applications。

 What react does really well is that it localizes the change such that if you need to change a small text。

 you can only have the work for changing that small text instead of having to rerender the entire page。

 which could be very costly for a computer to execute so we try to look for bottlenecks and then go dive deeper into these and see why is this component so slow。

 Why is it taking so long， How can we refactor this component to make it faster maybe we can delegate some of the computation to the backend so that we're not incurring this cost on the user and the front end。



![](img/8cce78b988633def63cb97ed89bb918a_7.png)

So the engineers and the product managers and the designers。

 they all use the application while it's being developed as much as possible to be in the shoes of a user and really feel the experience that they're going through when they're using our applications。



![](img/8cce78b988633def63cb97ed89bb918a_9.png)

And then once theres enough confidence that this application is ready after checking all the boxes in terms of its performance。

 its stability， its usability， and as well as completeness。

 then we release it in an alpha stage where there's a small number of users trying it out so we can get some feedback。

 and as we gain more and more confidence throughout the feedback cycle。

 then we crank it up to more users until it's completely released。

It's a very important part of the requirements for an application to be performant and usable and in order to achieve that there are certain design patterns and well established approaches that engineers have developed over time that have known to work really well and increase performance of application so like using memorization or delegating part of the process to the back end。

 so I encourage you to look for those and find ways that you can introduce these design patterns in your application。



![](img/8cce78b988633def63cb97ed89bb918a_11.png)