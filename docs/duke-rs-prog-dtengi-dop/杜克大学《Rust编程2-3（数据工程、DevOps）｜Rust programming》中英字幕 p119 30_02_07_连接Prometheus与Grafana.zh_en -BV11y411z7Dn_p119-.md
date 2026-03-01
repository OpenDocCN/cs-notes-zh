# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p119 30_02_07_连接Prometheus与Grafana.zh_en -BV11y411z7Dn_p119-

![](img/a6736d5debec587447a62ab15a5205e5_0.png)

Although there are many different ways to deploy Prometheus and Grfaa。

 what I'm going to show you today is a very straightforward way to start tinkering and connecting these two services and actually seen a little bit of action in the dashboard in this case for Grfaana and the way this is going to work I have a Docker composeos file we haven't seen Docker composeose files yet with containerization but is a nice way of developing we can develop with Docker composeos which allows you to have separate services in this case Prometheus here and Grfaa right there。

 so by doing this way I can have local files that are going to go into each container separately these are actual containers and these are going to be brought up by the image the images right here for Prometheus is this one and it's going to be named and this。

In the ports。 So these ports are going to be accessible for me in a local host。

 So 1990 is going to be what I'm going to be looking for and for Gra is going to be 3000。

 and for Grfaana I'm going to have admin admin as a default username and password which I will get prompted to probably do an update。

 Alright so this is the Docker composer it explains everything I'm going run。

 now let's take a look at the Prometheus that Yamo file。

 which is how we would actually configure is this Prometheus that Yamo file has a scrape interval of five seconds so。

Every five seconds it is going to reach to an endpoint or the configure endpoints that we're going to have It's going to also we're going to have a configurationration for the scraping and we're going to have a name a specific name and this is going to be important crucial in a moment you will see why and this is called acts monitoring we're going to honor the labels of anything that is being preconfigured there for the ats web framework the HttP that have running rust and we are going to basically go after a specific target So what is this host that Docker that internal well。

 we're only telling this special name to tell Docker hey， by the way。

 this is local host my machine the Docker host instead of doing local host because if I had local host here。

 the container is going to think this is。Actually， the local host of the container when it is in fact my system and the way to expose these on the host for Docker。

 then you will have to use something like host a Docker that internal Now in production you would have something probably different you would have some other an IP and an IP probably internal if you're doing the monitoring internally or some publicly accessible IP and probably if it's if it's publicly accessible。

 you would probably want to have some authentication。All right， so now that that's done。

 what I'm going to do is I'm going to run and I'm going to open the Docker compose once again。

So what I'm going to do is I'm going to open up the terminal and run that docker compose。

 so I'm going to toggle the terminal and and I'm going to make this slightly bigger and I'm going to say Docker composeose and the file I'm going to pass in is Docker dash compose。

That yao and I'm going to say up now this is not this is going to run in the foreground is not going to go to the background。

 so we'll see lots lots of output populating here here as these things are getting created Allright so that was wow that was pretty fast because I had already pulled the images if I scroll all the way up you will see that container Grfaa was created container Prometheus was created that took zero seconds and you start seeing a lot of Prometheus a lot Prometheus output there。

 So not only that， but also Grfaa you can see here that it takes a different coloring scheme。



![](img/a6736d5debec587447a62ab15a5205e5_2.png)

Alright so now we're going to switch away from our text editor here and we're going to go to the web browser okay for my browser I'm going to go to a couple places first of all I'm going to go to port 8080 local host that is my redacty application in rust that is running and exposing the the correct metrics and that is you know pull in everything correctly still so that that is fine I'm going to go back and then I'm going to open a new tab and I'm going to go to Grfaana and that is going to be local hostt on port 3000。



![](img/a6736d5debec587447a62ab15a5205e5_4.png)

![](img/a6736d5debec587447a62ab15a5205e5_5.png)

So I'm going to say local host for 3000。

![](img/a6736d5debec587447a62ab15a5205e5_7.png)

And it's going to prompt me to log in remember we said that default to be admin admin I'm going to log in and because this is the first time I'm going to say。

 hey， you need to change that password no problem and I'm going to change it and then I'm going to be logged in when you are in。

 you're gonna to be greeted with basically a few options that you have and but we want to add we want to add some some services right so how we're going to do this well I'm going to keep scrolling here you have advanced plugins tutorials and you want to add a source for where data is coming from right now the dashboard like the Grfaa is empty there's nothing connected to it so this is going to have to happen from here add your first your first data source Yes I want to go here and I want to actually go and add Prometheus so I'm going say I'm going。



![](img/a6736d5debec587447a62ab15a5205e5_9.png)

At Prometheus and when I clicked there， you saw that there was like a data source added。

 So perfect I've added Prometheus and I'm going to say， yeah。

 Prometheus 1 sounds okay to me and the Prometheus server URL is going to be HtTP。

 this is important is going to be Prometheus。For 90 1990。

 Now why Prometheus and not local host because remember this is running in a container and Docker composeos has already injected that name named host so it knows how where to go。

 So perfect I'm going to do that and now I'm going to scroll all the way to the I mean you have plenty of different options including authentication。

 I'm going go all the way to the bottom and I'm going to say click on save and test。

And it tells me successfully query the Prometheus API so now I've made sure that both Grrafaana and Prometheus are connected。

 Well that's great， it's all good so now it's saved and now I can take a look at the dashboards so I have Promeus stats Promeus to consumer stats but I want to add I want to add more basically something that connects to my rust application So for that I'm going to go here to these menu over there。

 I'm going to click here I'm going to go to dashboards and I'm going to click on dashboards I'm I'm going to add a new one I'm going to add a new new dashboard and these dashboard is going to greet me by hey you know you can add your new visualoliization so I'm going to click add visualization and it's going to ask me where what's my data source。

 this is the one that we created which is Prometheus 1 so I'm going to click on that one and it's going to be empty there's no data。

So that's fine， we are going to be adding some useful information there。

 so the information that we want， we can actually do all different kinds of things。

 but we are going to do how about total HtTP requests。

And or fail requests how about we do fail requests to say to see where our how is that looking and what I'm going to do is I'm going to click on code it kind of small there actually it's make it a little bit bigger there we go I'm going to click on code and I'm going to put in a query now let's break this down we're going to do sum for the rate of redactor HtTP requests total that remember that's a thing that is happening in the metrics that is exposed and the status is going to be for4 and we're going to normalize that for every five minutes I'm going to run the query and we see that we have something going on there for the last six hours seems something like I don't want how about it do for past one hour that's great for a past 15 minutes we have a few so if I start hitting hitting the server for some other some other nonexistent。

404 request， then I'm actually doing that in my browser and if I refresh。

 this will start seeing some actual more metrics there for404s now you can see here that it's starting to populate because it takes a second now you can see here that I have quite quite a few I was doing refresh on on there and that's fine what what are some of the other things that I can do well how about I do about when it's a status 200。

 so this looks this looks correct so let's add on our query I I'm going to scroll here and I'm going to add on our query so I'm going to put that query here。

 this is for 200 requests and I'm going to run that query and I have well I start having a nice graph right and that's coming from you can see there its some reactor HtP request all for 200s for every。

minutesutes and we start seeing like a decline in the 404 errors because I'm no longer reloading and the the actual request for the 200s。

 So there you go that is how you connect Grfaana with Prometheus talking to a Prometheus endpoint。

 which is a slash metrics on a rust HtTP API。

![](img/a6736d5debec587447a62ab15a5205e5_11.png)