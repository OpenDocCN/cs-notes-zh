# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p112 23_02_03_监控工具概览.zh_en -BV11y411z7Dn_p112-

![](img/45016dcf956b341c1bbd48926290a3a3_0.png)

There are many different monitoring tools and tooling and instrumentation for applications。

 so I'm going to talk about a few that are very popular and one that I really like that is not tremendously popular these days。

 but in this case I'm going start with the elk stack also called the elastic stack。

 So what it is well you can see here it is referenced right there is the ekt so ekt stands for elasticastic search。

Kanana。And logtash beats is usually not mentioned in the acronym。

 but these combinations this combination of these four tools allows you to have a very nice monitoring for your applications Now there's the possibility of like roll your own your own service that will handle these。

 but you can also rely on cloud providers by implementing their own elastic elasticasticsearch。

 Kibaana beats and logtch， so what it is elasticastic search is essentially like like a store like a data store like a big database is not exactly a database。

 but all of the metrics， all of the information will go to elasticse。Kvaana is the dashboard。

 the front end where you can actually visualize Kivana will talk to Elasticse to produce those nice graphics of what's going on。

 Beas will look at the files that you have in your file system and will start shipping those files those log entries over to log sta and logt will parse them and you can set up certain rules like say for example we were seeing Enex style of logs and you can say well I'm going have a rule to only process error error logs from from my Enex web servers So the way this works is it starts with beats beat sends its logs to logtash logtash pares them and sends them to elasticastic search and then Kivaana looks at elasticastic search and produces nice a nice dashboard so so that is that is that's it those are the kind of like how it works。

And you can see that here we have like a quick overview of what Elastic searcharch is and then Kiana with a nice dashboard and the useful or the nice thing about this is that you can ingest from anywhere it doesn't matter as long as there's a log file you will be able to ship those logs and no prop。

 if I go here to Kiana， you will see that there's a nice dashboard。

 a nice way of integrating your data and it actually you can look very， very nice。 I mean。

 this is actually beautiful and this is all getting its information from Elasticsearch。

 you can see here that elasticasticsearch， of course is mentioned again So as long as you're capturing filtering and shipping your logs and they go to elasticasticse you have the ability to create very powerful dashboards that allows you to build these nice nice infrastructure for monitoring right so you have like a good dashboard off。

Being able to see exactly what is going on。 So the data store coming from， again。

 from log not log stabed Elastic search， and you're able to produce that。 no problem。

 So definitely a good， powerful set of tools。 They all have to work together。

 The architecture is slightly more complex。 We'll see those later。 But next。

 I wanted to show you graphite。😊，And graphite similarly。

 it has several things that work in unun and all of these allows you to produce graphics that are very compelling and be able to do some very good monitoring and understand what is what is going on across time。

 So what it is is a frontend， a web portion of it like a request will come into the web and then that would talk to both to carbon and to whisper whisper is that the data store how it's how those metrics are getting stored is a special type of database you can see that is referenced here。

 a simple database library for storing time series data everything is based on time series data and then you have carbon which is something that listens for those incoming metrics So the way this works is that applications will be sending and。

In their metrics this is useful if you have like a function that is doing lots of processing and you want to capture。

 for example， how much is this function taking to process my data and then that is usually pair with the Stat D which I really like it's not that very popular these days。

 but it used to be very popular you can see here it mentions graphite it requires you to run a demon which uses node JS and it will send those values over to something like carbon over to graphite and so that you can display them later so very nice。

 very easy to integrate with code and last is Prometheus which and you will see the intersection here of both monitoring and triggering some action so Prometheus is a different type of monitoring where you will see not only capturing metrics and other components。

show you here the architecture where you can also send alerts and you can trigger those by email or like in this case Pager duty and you can do all of those things now the interesting part of the architecture for Prometheus is that you will have servers that will have the ability to expose metrics and those metrics that are getting exposed will come over to Prometheus by doing pulling。

 so it will pull those metrics into the Prometheus server and then you can do visualsolization but not only that but you'll have like a Prometheus webUI or you will have like also Grfaana right here for visualoliization and exporting of those metrics we will see that there's the pull and push which we get into later but。

All of these components， both the Elk stack， which is elastic search， Ki and locktash， graphite。

 StaD and Prometheus， well those are very solid and depending on where you want to deploy them and how you want to use them。

 you will pick one or the other。

![](img/45016dcf956b341c1bbd48926290a3a3_2.png)