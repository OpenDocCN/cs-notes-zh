# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p121 32_02_10_Azure中的监控与日志记录策略.zh_en -BV11y411z7Dn_p121-

![](img/b02cc201231e3aae6c18896b62c2b76f_0.png)

Without going into much detail into how Azure works。

 I'm going to show you and demonstrate you how easy is to add instrumentation for monitoring and logging on Azure for containers specifically here we have the container apps service。

 and I'm going to very quickly going to create a container app。

 I'm going to create a new resource group， something that is actually required for for creating services on Azure。

 I'm going to say demo container。Container apps login and'm gonna make it something meaningful。

 container app name is going to be demo， Alfredo login。

 so something that will make me remember that this is in fact a demo and I need to destroy later and region West US2 sounds okay to me next I'm going say going say review and create this will be all the default number of CPU core is set to 0。

25 so a quarter of a CPU core and 500 megabytes of Ram the port is going to be 80 and is' going to accept traffic from anywhere。

 so I'm gonna to click create this is going to take a second and we'll come back once it's complete so deployment succeeded I'm going to click go to resource and I have these container app up and running now I'm not going to deploy anything custom I'm going to use use the default container app that is already running actually if I go here I have the application URL is going to run on  port 80 you will get these default。

Message and and the full container is running。 your Azure container app is live is running。 Okay。

 perfect， something' is deployed by default fault。 We don't care right now about the S specifics Now you have several things here like the activity log。

If we click here activity log you will see we don't have anything there。

 we have an instrument instrumented anything but I want to show you a little bit of what are some of the things that you can do so you have all of these for monitoring right there you have alerts。

 metrics， logs， log stream so one of the things that you can do is you can take a look at logs。

And you'll have some queries so you can click any of these you can say hey like I want to see if there are you have all of these prebad queries that you can do analyze errors。

 we're not interested in the errors， we can actually take a look at the log stream and the log stream will create a console and it will connect to it you can see it's connecting and it will produce all of the things that is regarding the actual container that has been deployed now。



![](img/b02cc201231e3aae6c18896b62c2b76f_2.png)

A couple things is connecting to the container， finally connects to the container and then it is it gives you details on where it's listening so if you were to deploy something like this then you will be able to actually see all of your logs being produced right there there's different options that you can have here in this case you have the system logs you have things that you know more to the system that is running your container app which is actually fine and this is an excellent way of inspecting what might be going on now whenever you are working with containers is good to also capture some of the metrics。

 some of the things that you're doing and in here you have everything by default fault you don't need to add absolutely anything new or anything to your container by default you will get all of these no problem。



![](img/b02cc201231e3aae6c18896b62c2b76f_4.png)

We can say well I want to check the CPU usage it looks correct， how about we check。

 we can check requests and we'll see that perhaps there's been some requests。

 well it doesn't log my requests right now， we can say Max， let's take a look average。

We can say network in。That's probably this is probably coming from my request that I just did in a a couple minutes ago。

 so the good thing about this is that you get all of these included because you've deployed these and it has no problems。

 you even have alerts so you can configure and you can say you can trigger your alerts and create。

 you can create your you can have your rules and you can create rules。

 no problem and define what is it that is going to be this thing that is going to alert you based on metrics so。

This is a very， very quick overview on how that looks like， why is it interesting？

And how you can add these without modifying at all the container。

 so this is definitely something to take into account when you're working with containers and in a cloud service provider like Azure。



![](img/b02cc201231e3aae6c18896b62c2b76f_6.png)