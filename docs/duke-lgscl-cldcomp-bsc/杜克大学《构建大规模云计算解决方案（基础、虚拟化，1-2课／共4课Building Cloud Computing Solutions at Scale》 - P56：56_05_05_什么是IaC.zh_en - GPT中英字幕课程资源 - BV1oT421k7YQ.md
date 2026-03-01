# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P56：56_05_05_什么是IaC.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/8ec63010ce7a3f0869934820db43f132_0.png)

What is infrastructure as code infrastructure as code is literally the infrastructure checked in alongside of the source code of your project What this means is that you can have a repeatable item potentent process of deploying and configuring let's say your cloud environment and in practice this means that the code itself is one of the things that's deployed but also the environment and what's nice about this is that you can actually go through。

And build multiple environments you can build we'll call this in number of environments because everything is defined in code and you can create a template that has。

 let's say a staging environment， a production environment or any number of environments and all it is is a slight variant of what you've already got in your source control repository So in the terms of the process of how infrastructure as code is used is there's an event that's triggered and this is typically the push to let's say the master branch and after you push that code the build server goes through and looks at the regular source control process of let's say a test and a lint and some deploy step。

 but also the actual physical infrastructure is pushed out as well。

 so this could be configuring the load balancer or setting up the storage properly or creating user permissions and what's nice about this is it isn't a snowflake type deployment where。

Human went through， pushed some buttons and then you asked the human what they did and they don't know what exactly they did because it's so complex everything that they actually performed and that's really the key learning with infrastructure code is and it's a best practice for doing cloud based deployments if you're not using it you're not really doing the modern way of doing deployment and it solves a lot of problems in terms of repeatability and also in terms of business continuity if you don't have infrastructure as code you can have some big problems in let's say a key employee leaves well how do you even know what they did before infrastructure as code is really a best practice that all cloud solutions architects should copy and implement in their organization。



![](img/8ec63010ce7a3f0869934820db43f132_2.png)

![](img/8ec63010ce7a3f0869934820db43f132_3.png)