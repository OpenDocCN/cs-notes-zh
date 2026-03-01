# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P125：58_04_07_Google App Engine Rust微服务监控与日志.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/de1d9fbade31bfd14b19087f223e3828_0.png)

嗯。Here we have a rust microservice using the Actics web framework。

 and you can see here that it has the route here fruit。

 It also has a function that returns hellello world。

 And we can actually look through this code to see how when we deploy into production。

 what will happen。 It's also containerized And so this containerized application works very well for app engine。

 So if we go over to the deployed version of it inside of app Engine。

 You can see here that there's a dashboard that shows all of the different important summaries in this section。

 So we can see here that there's a number of requests here that we can look at we can also go into the billing status。

 look at errors if there were any errors。 we can also toggle through all the different settings。

 So request by type， for example， latency， we can also go to loading latency as well。

We can go to errors， we can also look at traffic， how much traffic has been received as sent。

 we can also go to utilization， and we can also go to the instances so how many instances are deployed。

 we can see there's two and we also can go down to memory usage which can be very important for microservices and we could even create an alerting policy based on that finally。

You can look through here and there's lots of different caching queries as well。

 And we want to look at the application pretty easy， we just go through here。 and again。

 here's our random fruit rustbased microservice we say fruit and we can run this over and over again。

 So really it's a very straightforward and comprehensive monitoring service just from the dashboard alone and we also could go through here and look at versions and even see which versions are actually serving out traffic in this case we can see this is 100% of the traffic and we could even stop or start the service from this dashboard。

 So really a onestop shop if you have a containerized rust microservice for Google app engine and the other thing that we can do that's also pretty handy is that we go over here and we go over and find logging。



![](img/de1d9fbade31bfd14b19087f223e3828_2.png)

![](img/de1d9fbade31bfd14b19087f223e3828_3.png)

We can even drill into the details even more。 So one of the ways that we could do that is we could actually create a customized query so we could even look through here and toggle just by resource type and get a good feel of everything that's happening。

 createate metrics， create alerts， those kinds of things and even do SQL queries。

 But I'm going to go through here and just look at something very simple。

 which is a query of that URL， right so we know that the fruit URL here is something that does get called。

 Let's go ahead and run a query。😊。

![](img/de1d9fbade31bfd14b19087f223e3828_5.png)

And we should be able to see here of course it is。 we can see that these are the app latency in seconds。

 we can see the name of the project and we can look at the timestamps of when were actually called and if I wanted to as well I could go ahead and create some kind of an alert based on this for example if it was maybe like call too many times we could do some kind of action based on it and we also can toggle through and look at different log names look at severity so there's really everything you need to debug a rustbased microservice with app engine and a combination of the dashboard for Google App engine and the log display blur will give you everything you need to debug your production application。

