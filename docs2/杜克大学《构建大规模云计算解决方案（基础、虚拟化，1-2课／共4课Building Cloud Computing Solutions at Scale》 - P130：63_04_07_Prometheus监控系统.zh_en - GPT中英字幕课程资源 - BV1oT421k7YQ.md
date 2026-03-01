# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P130：63_04_07_Prometheus监控系统.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/2ed58a54b4ab78e5f640ea25f5b0c2ec_0.png)

Let's go ahead and get started with Prometheus， which is a very popular metrics and alerting solution that's often used alongside with containers and Kubernetes。

 so let's go ahead and use AWS， the Cloud9 environment。

And we'll use that to actually prototype what we're doing。 As I've mentioned other videos。

 Cloud 9 is often a shortcut to really productive workflows because it simplifies your environment and especially if you're going be doing something inside the cloud。

 It really is a great environment。 So I'm going to click on cloud 9 here。😊。

And I've already got some cloud9 environments opened up。

 I'm going to go ahead and click on this Docker build， I was doing some Docker work in there。

And what I'm going to do to start with is that I'm going to go ahead and download my Prometheus client here。

 so I'm going to go and find my Prometheus client， which is going to be in the Prometheus download section。

 so let's go ahead and put that in here。All right， and I'm going to go ahead and find this Linux executable。

 Here we go， I'll copy the link。And then if I go to this environment， I can type in W get。

Just like that。Now， when you're watching this video， your version may be a little bit newer。

 but you can go select that version all right， that looks like it's successful。So next up。

 what I'm going to do here is that I'm going to make this window a little bit bigger and I'm going to go ahead and look for that directory。

 there we go， and I'm going to unt it so I'm going to run the command tar X VFC and then Prometheus and do an autocomplete。

Great， that looks like that was able to bring it up there。 And next up， then what I'm going to do。

Is I'm going to Cd into that directory。And from here， I'm going to go ahead and create a config file。

 you notice that there's already a default config file so I can actually use my editor。

And take a look at that， so let's go ahead and look at that config file。Okay， great。

 and it's going to ask me to view it with a text editor。

I'll go ahead and do that and I'm going to paste in my own configure so I'm going to slightly change this one。

 Here we go， it's got Prometheus and it basically is going it's going to keep track of its own metrics so Prometheus is a metrics collection system but it also produces its own metrics and notice that it says port 9090 so。

The cloud9 environment is safe by default and so as a result I'm going to have to go ahead and clean that up a little bit。

 let's actually make this a little bit bigger， I'm going to have to clean that up a little bit by opening up a port so in order to open up that port。

And see the traffic in port 990， I'm going to go ahead and go back to AWS here。

And I'm going to type in EC2。And I'm going to find in the security group where that actually lives。

 so I'm going to go down to security groups here。And I'm going to find the one that says Docker in there。

 Let's see。 I think I can just do a control F docker。There we go。And if I click on it。

 notice that the inbound ports here。Or only port 22， so I'm going to need to open up another port。

Add a rule and this rule will be 9090。 So that's again。

 the port that's going to serve out the metrics website。Okay。Now that that's open。

 I can actually run Prometheus here and we can see this thing in action so I've saved the config file。

 how do I run Prometheus pretty straightforward， I just pass it in a config file so it looks like this dot slash Prometheus dash config I give it that Yaml file。

There we go and now it's running， it's running in foreground mode and foreground mode is a great way to observe what's happening on your system because you can see the output of the server and all I have to do now is find out what the IP address is so how can I do that why go back to this EC2 console here and if I go to my instances I can find that instance and you can see here that Docker build you can notice that it's running if I click on it I actually can get the publicly available DNS server somebody just copy that。

Put a tab open here and paste it in。 Now， remember， we told it to open up port 1990。

 So I'll need to say colon 9，0，9，0。Great， now that that's running what I can do。

Is take a look at maybe telling it to create some metrics。

 So one of the ways you can make it create metrics is by going to this metrics URL。

Let's go through here and。Let's go back here。And and I believe we can go to metrics is the is the URL metrics。

 There we go。 And now you can see it generated metrics。 So every time I called this page that was1，2。

3，4，5， it's itself kind create metrics。 So let's go back here。

And see if we can put in a command in the expression browser。Right here。

That will give us back those requests。 So I'm going to click on that， and then I'm going to say。嗯。

Execute， and you can see， in fact， it showed a bunch of value。

 So it was able to generate two metrics elements for each one of those calls that I did。

 Another way to look at metrics inside is to actually go in the graphs section here。

And if you click on graphs， you also can go through and look at different visualizations as well and look at the different counter so really this this interface here and let's pick。

One of the metrics here， which is。Let's see maybe the HTTP request or something like that。

 we execute that and if I graph it I can go ahead and see those requests。



![](img/2ed58a54b4ab78e5f640ea25f5b0c2ec_2.png)

![](img/2ed58a54b4ab78e5f640ea25f5b0c2ec_3.png)