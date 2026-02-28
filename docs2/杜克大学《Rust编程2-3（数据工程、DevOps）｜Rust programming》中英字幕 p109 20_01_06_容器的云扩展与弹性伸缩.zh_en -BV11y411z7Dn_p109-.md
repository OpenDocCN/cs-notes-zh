# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p109 20_01_06_容器的云扩展与弹性伸缩.zh_en -BV11y411z7Dn_p109-

Scaling and elasticity is a core component of cloud services。

 cloud services solve this problem by depending on certain constraints and certain rules it will allow your container your service to grow and scale horizontally what horizontally means it means that it will have many more container images or resources to deal with incoming traffic now in this case I want to quickly very quickly talk about deploying container apps on Azure but more than container the containerization or deploying the container app basically do the scaling and how does the scaling work and you can set certain rules and the rules are important because you can actually。



![](img/944f9b19937924bd181164525c719349_1.png)

Be able to fine tune exactly what that scaling means and you can see here that we have like the minimum number of replicas prohibition。

 maximum number of replicas prohibition so you can have a default like if you're say for example like a very quick example you have like an API and you want to have like the minimum value to be I want to have two container instances running at any given moment in time then you will have you'll have to set that minimum number of replicas prohibition and then you can set that even max maximum value up to 300 and。

How much are you going to be able to scale well by default you get 10 and the minimum value is 1 so you can scale from 0 to 1。

 but if you have like the default value to be like one or two。

 then you can definitely scale all the way to 300 right here。

And so you you can set those rules and you can set that the behavior and that elasticSity allows you to incrementally grow the number of images。

 but also reduce that the number of images as you no longer need needed and this is core to be able to have like a very efficient billing so you don't want to be running 300 containers if there's no traffic。

 but if you're getting a spike in traffic， you definitely want to handle it and you want to grow as needed within the constraints that you're putting and you have rules based on HTTP custom rules based on CPU and memory so say for example。

 if my CPU goes beyond these threshold I'll just keep launching more container images which is something really really useful and for HtTP well they give you examples and you can set the scale rules and the minimum maximum replicas and you can see here it's the full zero and it can go all the way to10 and you start adding those。

Rules and definitely have the custom one and the polyin interval。

 The polyin interval is actually pretty cool because you can set how many seconds it needs to wait until it starts triggering these or executing these constraints to scale horizontally now I'm going to go to the Yazure portal and this is my own accounts I'm going to go to I have container apps here and I can definitely go and click that。

 but I also prereated these testilereto scale and I'm going to click on container apps。

I already have these prereated how you created is not necessarily important for what we're trying to describe today which is actually going to look at scales and replicas and we're going to go here to scale and replicas over here on the left and when we click here by default default when you create one when you create an instance of container app on ash or you're going to get the default container I haven't deployed anything really。

 but we can actually see that the scale is from0 to 10 which as you saw those are the defaults and there are no scaling rules and how you add scaling rules you need to go to edit and deploy so let me click on that。

And then you can see that the container is the simple hello world which is a default one there you go and it's an Azure container and it only uses a quarter of a CPU and have a gig of Ram that's by default so you can say scale yes I want to add a scaling rule and then you can say well you know this is a test rule and I want to say I want to make it custom and then you can start seeing all of these things that you can do there and you can do Azure queue you can do HTP scaling concurrent request well if it goes beyond 100 yeah go ahead and scale it and scale it to10 that looks correct to me so definitely lots of flexibility and why is this important because it allows you to grasp an important concept on DevOs specifically which is beam flexible and allowing to you're allowing yourself in your organization your team your。

Your company to be able to deal with scaling when traffic grows and in a way that is almost semi automated with defining certain rules。

 now one thing I really like about Azure is that if I'm scroll all the way to the top here。

 you can actually look at the documentation because one thing is looking at the Azure portal and clicking a bunch of menus but if you want to automate these and remember automation is one of the foundational pieces of Devops。

 then you will want to go to the CI and the CI would allow you to do these things with a CICD system and then all of the examples would change。

 And if I go here you will start seeing that you'll get the Azure Ci command to try to set those rules instead of clicking some menus。

 So there you go that is a high overview， a quick overview of what is scaling in the cloud in this example with Azure。



![](img/944f9b19937924bd181164525c719349_3.png)