# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P100：33_03_04_什么是微服务.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/5304c0c9942bd3d5902f73880fe3c961_0.png)

So what is a microservice， Well， it has a few different characteristics that we can take a look at one in terms of the traits of a microservice。

 it's small， so a microservice does one thing does it very well。

 It's also autonomous so a microservice isn't making connections to let's say the database and making connections to the O serviceice and tying it all together。

 it does a particular task and it does that one task very well so each microservice could。

 for example， talk to independently the authentication system more independently to the database system。

They're also specialized so these microservices can do a particular task in a way where they're not going to fall down if theres a connection that fails between another service。

 they could gracefully handle that error。 So those are some of the key characteristics of a microservice。

 So what about the benefits Well， in terms of benefits。

One of them is just the speed to develop the application a lot of times if you're dealing with a larger application。

 you have to go back into pages and pages of code and figure out where something interacts with another。

 but if it's a small microservice， you can instantly look at it。

 let's say it's 100 or 200 lines of code and you know what it is that it does。

That also ties into simplicity so likewise， because the service is so small。

 you know exactly what's happening when it runs and you can isolate things into a particular service。

 so the authentication service or the database service or the business logic service。In a nutshell。

 what that's doing is it's mapping the logic of your microservice into a particular URL。

 so really at its smallest form， what a microservice is is it's a function。

 let's say in Python or in go or some other language that maps to a URL or to an event。

Now what does that actually mean for us， well， what it means is that there is a high degree of reliability because of the fact that that microservice does one thing and it does it well。

 so in a nutshell a microservice is a huge advancement in software engineering architecture because of these traits and these benefits。



![](img/5304c0c9942bd3d5902f73880fe3c961_2.png)

![](img/5304c0c9942bd3d5902f73880fe3c961_3.png)