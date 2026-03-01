# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P53：53_05_06_DevOps最佳实践.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's dive into the Devops best practices that your organization should look at。

 You can think of this as a checklist。 First up， we have continuous integration。

 continuous integration is the process of automatically testing bugs making sure that you are able to improve the software quality and reduce the time to let's say validate release a new software update so that's a critical thing to put into your checklist Next up is this concept of continuous delivery right so the ability to have code change automatically build and test and be ready for release into production It's really an extension of continuous integration and it means that you can deploy all your changes to a testing environment or a staging environment and it's automatically done without a human being in the middle of that loop。

Next up is microservices and this one is an interesting one because it's not talked about as much a lot of times you'll hear only continuous integration or continuous delivery。

 but microservices are a critical component of DevOs because it means that you can build a single application that has a set of small services and each service is its own world and they can communicate with each other through let's say a queuing system where some other interface that allows this really robust architecture so by simplifying each of these services。

 it really adds a lot of scale and it's really the modern way that people are doing software development。

Infrastructure as code is another best practice that an organization must have。

 and the reason for this is that allows you to do continuous delivery and by checking in the infrastructure itself into。

 let's say your Git repository and allows you to develop automated and repeatable ways of orchestrating the infrastructure and this allows you to have the speed of delivery that comes with DevOs。

Monitoring and logging is an often let's say， misunderstood or left behind process。

 but it's one of the most critical things an organization can do as a DevOs best practice and what it does is it allows you to look at the metrics of an application。

 look at the infrastructure to see how the CPU load is doing or the memory or the disko and you can get to the root cause much quicker and then that change can be propagated through continuous delivery so there's a feedback loop where really it's a data- drivenriven approach it's got heavy tie into in fact data science because you look at the data you make a decision and then you do a deployment。

Also communication and collaboration isn't the last thing to think about it's actually one of the most important things to think about and what this means is that culturally your organization is constantly trying to figure out ways to have better communication that can mean through let's say ticket system or a chat system where people can talk about the different aspects of the source control also you can you can have these comments in technical documentation so by making this a priority you're going to implement DevOs best practices so really it's the combination of all of these that's a checklist and you can't leave one of them off each one of these things needs to be really in your infrastructure of your organization to do DevOs。



![](img/46d146094f5dc1da6cd0f14847d926a8_1.png)

![](img/46d146094f5dc1da6cd0f14847d926a8_2.png)