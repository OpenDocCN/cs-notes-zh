# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p111 22_02_02_日志记录与监控的交叉点.zh_en -BV11y411z7Dn_p111-

Loin and monitoring is essential in DevOps settings when you want to try to apply some of these DevOps principles and I have here an example project that I wrote several years ago which is a query analyzer for Postgres SQL Now let me tell a little bit about the backstory about these which was a distributed cluster of Postgres Postgres SQL is a database and the database server and we were having some issues about some of the queries and after enabling because you can configure actually the login in Postqrel SQL and here have like a sample of the configuration that you can have not only the log name but you can actually set these to what type of login you can see this is actually very powerful you have actually standard error right here。



![](img/e83c20b808748306c4ef0603723ff3ec_1.png)

CB you can log to Cs log， which is a system stands for a system login It's like an actual part of the operating system OS10 and Linux and other UniX style of operating system has that and event log so you can you can definitely enable these and you can have the capturing of standard error as well so this is all very good and it requires you to set that login now why is this important。

 why is this relevant to what we're trying to do with DevOs applicable to actually any other application and that is because this error reporting and login allows us to do query analysis and this is a specific to Postgrel SQL but we'll see in a second how it's applicable to other types of applications so what these very small program can do is detect the slowest queries。

Find the usage like what's what' the top queries used like imaging someone is issuing one query and that's the slowest but there's one that is not too slow but is used many。

 many different times and so you can start seeing some of the disadvantages of certain queries that are happening for the application and then a weight which is time to execute multiply by times used。

 So this is a very a very useful metric because it allows you to get which ones are the most problematic queries Now this is all coming from the ability to look at logs and with that you can investigate more。

 So we have a clear separation of logging and monitoring logging more for like investigation and monitoring for triggering some sort of action there's also like a little bit of an in between between those。

you can actually do monitoring based on logging， so you can see here and I'll skip all of the actual granular details of this application。

 but at the end of the day we are able to capture all of these things and be able to do some accurate reporting and this is all basically possible because of logging。

Next， I want to show you， I'm going switch over to my terminal here and in my terminal。

 I want to run Nng X， a container running Nng X。 So I'm going to do Docker run and I'm going to map the port port 80 on Nng X to port 8080 on the host I'm going to run the Nng X latest version。

 So I'm going to do that and that's going to take a second to come up。 Alright。

 so that is coming up and there's a several things going on。

 the number of workers actually the workers are starting and using is giving me a little bit of information on how the serverries are starting。

 So this this is pretty good and pretty useful。

![](img/e83c20b808748306c4ef0603723ff3ec_3.png)

There's a lot of like debugging information specifically about Docker right here at the top。

 but aside from that， nothing， nothing else other than that this is starting。

 So in a separate window I'm going to start doing some requests to this endpoint and when I start doing the requests you'll start seeing all that information appear there now so far all of those are good request。

 but if I start typing on things that are going to cause some errors。

 you will see things are getting a little bit gnarly So let's try to decompose these a little bit and bit by piece。

 So first off， it's identifying the IP， this is the IP。

 the originating IP of where this is coming from because this is a container this need some tweaking to make it actually useful。

Now we have here the data and time and you can see it's separated in this format now that that is all good and then we have the get request I was doing in a get request with my browser what type of HTTP request I was doing and I was getting a three or4 three or4 meaning it' a type of redirect those details are not important and I was using this type of browser。

 this is an interesting piece of information that web servers can capture so you can tell that I was using an Apple computer and I was doing that type of request and so that's very good if I keep scrolling here so that we can find the actual error you can see there that I was trying to reach slash FffF which it' well it doesn't exist and I was using the host is something that that is important。

This is the actual host that is serving that request that is the IP and this right here is the port so you can start seeing that this is pretty useful to understand things that might not be going quite well if I actually go and clear all of these and and then do a request with curl。

I'm going to split my terminal here。 I'm going to do a curl。And I'm gonna post data。

 you will see that things right here at the top are not you know giving me an another type of error and saying hey this person is not only is no longer using a mozilla style of browser but is using the curl client which is coming from this guy right here and I'm doing a post request and I'm getting a 405。

 this is a response from the server and that's getting logged in now when is this useful in the context of monitoring because we I was telling you that there's an intersection Well the intersection here is that you could have monitoring in place that takes a look at these types these types of logs right here and then you can set some type of rule and you can say well if we start getting several 405s or 404s or several errors。

 especially if they're coming from a post， then we need to take some。



![](img/e83c20b808748306c4ef0603723ff3ec_5.png)

ActionSo once you start seeing errors and of course the most critical ones are the 500。

 if you're still seeing 500， which is like an internal server error well then you know that you need to take some action so you could have some monitoring based on logging some application that is taking a look at logs right there so that is logging and then yous there's the possibility also of looking more at at monitoring tools but for logging this is a very basic and allows you to have some sort of idea of why would you want to why would you want to enable logging and what type of verossity you would want to have in situations like this so that you can comprehend and understand where are these coming from。



![](img/e83c20b808748306c4ef0603723ff3ec_7.png)