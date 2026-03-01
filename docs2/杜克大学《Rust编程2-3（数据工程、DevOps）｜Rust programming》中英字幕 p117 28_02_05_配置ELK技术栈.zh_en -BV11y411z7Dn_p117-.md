# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p117 28_02_05_配置ELK技术栈.zh_en -BV11y411z7Dn_p117-

So now what we need to do is we need to make sure that filebe that the one that will look at these entries and ship them off is correct。

 so now we'm going to edit Etsy filebe and filebe YaO。



![](img/d1e6ef1bc025178dadf1dde19af58639_1.png)

And well， I need super user permissions there。 Alright， so within here， I'm going to say inputs。

And we need to find that's a file stream。 Let's take a look if we find log。

 So we don't have a log here。 and let's。Let's go and search for paths。 Fbe inputs。

 So we're going to modify。 I'm going to set the numbers here so that you can take a look。

 So I'm going to modify these inputs。 And instead of a file stream。

 I'm going to say the type is a log the。TheIt's going to be enabled。

 So I'm to change it to true layer。 and then the paths。

 the paths for our engine X logs are going to be in bar log。And I'm going to say en next。

Andex slash start a log， and that will capture both error and access logs。 Okay， perfect。

 So we have type log。 So we need to get that through log sta and we to uncom the logt part and the fault is 50。

0，4，4。And we're going to leave elastic search there。 So when we're going to restart。

 we're going to do pseudo system， CTtL stop file beat。And now start star file bit again。

 and that is going to start able to produce all of these things over to engine X。 Okay， perfect。

 So now we're going to create a logtsh configuration directory and we're going to go et log stash and then in there。

 we should have a cof D directory， when I look in there。

 and we're going to call these file engine X that co。 So now in the same file we need not only input。

 but we need to filter and we're going to add a filter。

 which is G is the plugin and we will use this matching。

 So well use the combined Apache log and that will get us where we want。

 And now where do we want the output to go。 So we have the input。

 the filtering and we need to put the output， the output is going to elastic search and that is on port 9200。

On local host because everything is this is an all in one system so now we can right with that and we are going to start restart elasticse and restart Kivana as well All right I'm going I've restarted elastic search and now let's restart Kivaana that should be pretty fast and now we need to take a look at where where is Kivana running one thing that you might want to do and I'm here in slash at Si Kivana is go and look at Kivana Yael and change the server host from local host to0 that0 that0 if you want to expose Kivaana from the terminal now in order to do that I'm going to have to do some changes and I'm going to bring my browser in so you can see that elastic is ready to get started and I have to paste the enroll。



![](img/d1e6ef1bc025178dadf1dde19af58639_3.png)

And token from the terminal now if you're na sure， you can take a look at where do I find these。

 you can actually very very easily copy that and go back to your terminal。And paste that command。

 but that bin elastic search， I mean I don't have that in my path and this is why this doesn't really work。

 but we can try with what we had before in the terminal， which will be user share， create， create。



![](img/d1e6ef1bc025178dadf1dde19af58639_5.png)

Create enrollment token， scope， Ivana。And then we do that and then double generate the enrollment token from elastic search。

 and then we can actually copy that token into our web service。

 So let's go to the web service back again。

![](img/d1e6ef1bc025178dadf1dde19af58639_7.png)

And then click that， paste the enrollment token， and configure。



![](img/d1e6ef1bc025178dadf1dde19af58639_9.png)

Copy the code from the Kivaana server or run Kivaana verification code to retrieve it。

 so let's actually go back to the terminal and go and get this Kivaana verification code。



![](img/d1e6ef1bc025178dadf1dde19af58639_11.png)

And that is actually a different path these users share Kiana bining Kiana verification code。

 and the code is 451746。

![](img/d1e6ef1bc025178dadf1dde19af58639_13.png)

4，5，1，7。For。

![](img/d1e6ef1bc025178dadf1dde19af58639_15.png)

6， all right， so we're going to verify。And then it's going to configure and saving settings。

 starting elastic and completing the setup。 So that's very good that we have now everything altogether running in a single node。

 this is actually a virtual machine。 It's not a container。

 You wouldn't be able to do this in a container in a single container because it will require all these things require system D Now let's just wait until this completes to come back And because we don't have the username and password and can we have to go back to the terminal and run the reset password。

 this is all from the log output and then it will promise me if I want to continue if if I really want to do this。

 And yes， I want to do this and it will paste it to the terminal。

 I want to copy that and the username is elastic and that will be the password I'm going to log in。



![](img/d1e6ef1bc025178dadf1dde19af58639_17.png)

![](img/d1e6ef1bc025178dadf1dde19af58639_18.png)

And then its elastic is going to load and there's configuration recommended that is fine。

 I'm going explore on my own and'm going to have all of it ready ready to go So this is the home for elastic and we have the dashboard we have analytics so if you want to look at Kivana you would go into integrations and added it there。

 but essentially this means that elastic is good to go and you have everything you need in order in order to start looking at logs and looking at anomalies I mean this is a very compelling well put together login and monitoring and alerting system and this is all very powerful and you can actually start doing some spunking with alerts and rules and and do some of the some of the settings and start managing a fully。

out system Now， it took us quite a chunk of effort to get here， but it was very well worth it。

 Hopefully this is useful and you can actually start exploring on doing a more a production ready configuration and deployment with more servers and perhaps even a cluster。



![](img/d1e6ef1bc025178dadf1dde19af58639_20.png)