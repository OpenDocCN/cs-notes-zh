# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p113 24_02_04_推送与拉取策略.zh_en -BV11y411z7Dn_p113-

There are two main ways that you can actually do the monitoring and doing a little bit of login and trying to use login and monitoring for better management of your application and I'm going to start with elastic stack or the elk stack and the primary way that the elk stack works is push so there is actually two main ways of shipping information。

 one is push and the other one is pullinging so let's observe here a little bit on how this architecture works for the elk stack so you are going to start right here on the ingestion part and everything starts with beats so you have to install these it's called like an agent like a demon that will par filesacy will observe files like say for example。



![](img/5b16484f6d68a4644aed8719f077a5eb_1.png)

File and whenever it finds something interesting， it will send it to logtash and will concentrate on the Lt specifically which is elastic search Kivaana and logtash So again beats is not mentioned in the acronym。

 but it starts there you have to have that installed in your system and then that will push your information to logtash that is a push strategy because the server。

 the originating server let's assume that this is the server will start pushing that information to somewhere else in this case goes to logtash and logtash will have some rules that will parse and then from there it will go and push again to elastic search so you have one component over here going to logtsh and then going to elastic search and from elasticse you have Kivaana。

That will receive that information and will create a feedback loop that can actually provide for really nice metrics this elastic search and its components which is Kiana and lockt and beats。

 this is called a push and a push strategy because if this is the server。

 the server is in charge of pushing those all the way out。Now that's one strategy。

 the R strategy is a pool and a pool refers to a service that is pulling from its components and we've talked briefly about Prometheus before and I'm going to scroll here to the basic architecture of Prometheus so whenever you're deploying a Prometheus server which has its time series database as you can see right here。

The Prometheus server will actually scrape metrics from the application that is running somewhere so the application will usually export like a section like an endpoint in its API and Prometheus will just go and at a certain interval will start pulling those metrics。

 So this is a strategy called a pull strategy Now when would a pull strategy work better well。

 if you're dealing with containers， I would say a pull strategy like in Prometheus would work very well because all you need to do with your container in this case like if it was an API is just expose a specific endpoint and then Prometheus is just ping in that endpoint and retrieving that information back to its time series database now from from the Prometheus server in this case you can see that there's push alerts and that's fine you can set some triggers and those。

Tggers will actually go and do something in this case with another manager where you can set like some alerts like。

 say， for example， if you want to send emails or send text messages or other types of alerts stack can definitely happen now when would a push architecture work well well for servers or things that you can actually configure to have a demon running。

 if you go back to the elastic search to the Elt if you can actually do all of these configuration in a vision to your application that is running。

 then this definitely sounds like a good strategy this push strategy is less stress on the server that is actually receiving all of that information because this is just standing there and just receiving the information another another service that actually receives all of the information which。

A push strategy would be stats D which actually pushes that requires having the stat D demon and then pushing them out。

 Now this is the elastic stack， the elk stack and that's push as well。

 but Sta D is very similar And again Prometheus would be pulling from an exposed metric。

 So those are the two strategies that are very important and makes you makes it easier to understand when would one be more desirable than the other strategy。



![](img/5b16484f6d68a4644aed8719f077a5eb_3.png)