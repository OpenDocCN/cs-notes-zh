# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P101：34_03_07_微服务运行实践.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/871d6b277db89f2bf81fb679ee63f240_0.png)

Where do you run microservices？ That's a great question for an architect that's designing a system。

 There's a couple main categories。 First， you can run them in a container。

 And in terms of a container， it could be something like a actual service， for example。

 in the Google Cloud， there's a cloud run service that's a container as a service where you can take a microservice and push it out without needing to manage anything。

 Ally， you could deploy something to a more complex system like Kubernetes and that microservice could run in there。

 A second option is the cloud itself using cloud native capabilities。 And in particular。

 all cloud platforms now have this ability to write a function that maps to an event。

 And in that case， there would be a service like AWs Lambda， for example。

 or Google Cloud functions or Azure functions。 Another alternative is in developing a microservice is more of a holistic platform。

For example， elastic meanstock or let's say Google App Engine or maybe a more sophisticated service that maps together authentication as well。

 all of those platforms could be places that you could run microservices。



![](img/871d6b277db89f2bf81fb679ee63f240_2.png)

![](img/871d6b277db89f2bf81fb679ee63f240_3.png)