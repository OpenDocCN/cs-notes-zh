# Meta《数据库工程师（Python／数据库客户端／高阶数据建模／毕业项目／面试）｜Meta Database Engineer》中英字幕 - P69：1_Meta的数据库工程.zh_en - GPT中英字幕课程资源 - BV1pZ421a749

There have been instances in my career， where。🎼They were interdependent。

 and I had to release them both at the same time。 And so the only solution was to release code in the middle of night when we had the lowest traffic and hope that for the five minutes。

 we were down with one while the other one was updating that only a few users ran into the issue。

 And sometimes it's the only thing you can do。🎼。Hi， my name is Maxxie Herrera。

 I youth A them pronouns， and I'm a software engineer at Meta in the Menlo Park office。

I work on donations products， so making sure that。

![](img/d7d3cad754e2614682fccd8f70f6df6f_1.png)

We are tracking who is donating to which fundraisers to which charities This is very important that we don't get this wrong。

 We want to make sure that we're storing the right data and getting the right data to display to the right user and what we mean by that is we want to ensure the data validity we want to ensure that we are making sure that we are only getting the data that the specific user should see that we are saving the right data these are very important concepts when designing a database that you want to be reliable you want to make sure the relationships make sense and we need to make sure that we're not accessing any data that a specific user shouldn't see。



![](img/d7d3cad754e2614682fccd8f70f6df6f_3.png)

The integrity and quality of a database and its design is one of the first and primary steps to ensuring that our data is protected。

 our data is being stored in a safe way， and our users can trust that their data is not being mishandled。

 This requires us to have a well- designedigned database that is thoughtfully thinking about the different relationships。



![](img/d7d3cad754e2614682fccd8f70f6df6f_5.png)

That data can have with each other， as well as having some plan for changes in the future。

The process I generally follow when designing a database is to first come up with a core data model that I need for product to work。

 I start with that because for me it's the easiest to conceptualize how we're going access the data we need from a product perspective and then after that initial data model is built I start drilling down into specific privacy and validation details that we need so should certain data be encrypted。

 should certain data be only accessible via certain servers。

 these are all different questions that we are going to have to ask then depending on the type of data you store could be credit card information could be user information there's going be even more checks that you're going to have to integrate into your database and database design in order to accommodate that。



![](img/d7d3cad754e2614682fccd8f70f6df6f_7.png)

The core considerations for well designed database on Me are to first and foremost respect user。

 privacy and user safety。

![](img/d7d3cad754e2614682fccd8f70f6df6f_9.png)

Use should know where their data is and have access to it and that they should know that it's not being used in any products that they are not comfortable with。

 the other thing we need to ensure scalability， does not matter if you have a really well thought out data model if it cannot scale up with the billions of users that meta productss see every day。

I think one of the most common challenges when you're working with a database isn't the initial time you built a database because you have this concept in your model of a relationship。

 and then something comes along and changes it。 The first thing to do is really be thoughtful about how you can change your database in the future。

 how it will scale not only with volume of users but with types of products。

 The other thing that is very important to think about is how to modify an existing database。

 This is going to be a very challenging thing。 and the majority of the work around databases is a lot of this stuff。

 We have this old data model。 it doesn't suit our needs today。 We're going to overcome this。

 and that requires just a lot of thinking and planning on your part， how to migrate the data。

 these are big tasks that take time to kind of figure out But that is some of the ways that you become better at managing database and building better data models in the first place。



![](img/d7d3cad754e2614682fccd8f70f6df6f_11.png)

As a database engineer， you're going to have access to a lot of data and you really need to keep in mind how integral that is to user trust or the trust of anyone trusting you with this data even if you think it's kind of trivial data。

 there's a lot of trust being put in you to make sure that you're being responsible I really want you to walk away knowing that database design。

 database engineering is critical to the overall product experience and integral to user trust in the product that you're building。



![](img/d7d3cad754e2614682fccd8f70f6df6f_13.png)