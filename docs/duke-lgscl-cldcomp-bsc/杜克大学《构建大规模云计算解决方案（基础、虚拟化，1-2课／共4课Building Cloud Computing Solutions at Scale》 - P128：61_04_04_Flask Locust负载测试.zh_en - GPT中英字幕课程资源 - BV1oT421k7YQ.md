# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P128：61_04_04_Flask Locust负载测试.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/1eac1298243548f9cfb74ce1a446fce7_0.png)

Okay， let's get into some load testing here， what I'm going to do is take a look at this project called Docker flask Locus。

 it's in my GitHub repository knowAA Gi。And I'm going to go ahead and open up cloud9 again。

 this is my favorite environment here。I've already got one open， it's called DockerBuild。

And I've already checked out this repo and you can see where you're at if you go to get remote dashv。

 this will give you the access to the get repo that you're in。

 And what I'm going to do is I'm gonna make a very simple load test application that could be later used for a larger system。

 but but the logistics here are really going be similar， no matter what your microservice is。

 So first， I'll build a hello world flask application So just a few lines of code。

 I import the flask module， I go through here and I create one route。 All it does is run hello world。

 Let me show you how it runs if I type in Python。Apppt wpyY。

You can see it's going to run foreground mode and it's also going to run on port 8080。 Now。

 one of the things that's interesting about the cloud9 environment is that you do need to expose any port you want to interact with via the security groups。

 So I'm going to go over to this EC2 instance here。 and I'm going to look at the security groups。

And I'm going to find this Docker build instance I've got running which is right here and I'm going to ensure that the ports that I need to interact with are open so I've already done that but let me show you how you would do that you would click on edit and you can see that I've exposed port 9090 to everybody I've exposed port 8089 and I've also expose port 8080 so these are also some ports that I'm going to use in different capacities while I'm developing my Flaskg and it means that I can later then connect to that instance and how would I connect while then go to the instances tab here。

And you can see that this instance is running， that's that AWS Cloud 9 instance， and if I select it。

 you can see that in fact I can just copy this to clipboard。

 this is the public DNS address and I can create a new tab。

And I can go over here and type in colon 8080 and this should give me access to that flask gap there we go hellello world so if I go back to my console look I can see that I was actually a web request went in and if I go back here again and refresh it you can see that another request has gone in so pretty powerful workflow inside of cloud9 and immediately we can we can really get to work and start testing things out well the next thing that I'm going to do is I'm going go over to locus file here so I'm going to create a file called Locus file and I've already created this previously and I say from Locus import HttP locus task set between。

And all I'm going to do here is I'm going to create a function that is going to retrieve the main route here。

 which is just this Hol world route。And I'm going to create a user behavior。

And really this is just boilerplay code and then I'm going to put it inside of this class website user and I'm going to inher it from HP Locus so you don't really need to know about how to create these this is kind of boilerp code and if you want to make more of them you could potentially copy this code and make another route and then put it inside of here as a task but in our case what this is going to do is going allow us to run this command called Locuscus and I've installed that via this requirements file here so I have flask violentent locus and I've already covered that in previous videos about how you can create a virtual environment and I've inside a virtual environment and do an install so how do I run this and test this out and get this running locally here。

Well， what I can do is that I can kill this right here， kill this process。And start this app again。

 so we'll go Python app。And then what I can do in another window。

Here I can just type in the word locus and what this does is it actually looks for a file called Locus fileile and it starts to run it on port 8089 that's why I opened up that other port if we go to that port。



![](img/1eac1298243548f9cfb74ce1a446fce7_2.png)

You can see here that here's port 8089 if I refresh that。

 it asked me when I first log in how many users do I want to simulate。

 so this is a really powerful tool here， I can say I want to do let's say 10 users and I want to launch another user every second。

There we go and the host， well what's the host gonna be it's gonna to be the same host that I'm on。

 but it's gonna be the port 80-80。 so I'm gonna paste that in there and just take this out and say port 8080 because that's the port that flask is running on right here in this terminal let's go ahead and do that'll start swarming and immediately you can see here that it starts to show these statistics of all the different requests。

 And if I look at charts it'll actually start building these charts out in real time here So really。

 really powerful tool to use locus to test a microservice。

 you can then containerize app and test it the container you can then put it into Kubernetes and then have Kubernetes automatically do spawning So this is a very powerful technique that is really straightforward to do and go ahead and get started。



![](img/1eac1298243548f9cfb74ce1a446fce7_4.png)

![](img/1eac1298243548f9cfb74ce1a446fce7_5.png)

![](img/1eac1298243548f9cfb74ce1a446fce7_6.png)