# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P76：09_02_07_启动AWS竞价实例.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's go through and launch an AWS spot instance first we'll set up a cloud9 environment。

And then I'll go to the console and in this console， I'll tell the spot request。

Mechanism to launch a new instance what this does is allows us to。Effectively bid on the machine。

 get a machine， let's say 90% off， we'll say 90% off。And then once it's launched。

 I can SSH via the cloud9 environment。 Let's go ahead and get started。

 First we'll launch an AWS Cloud9 instance， so I'll find cloud9。

And I'll go through here and say create an environment。And in this environment。

 I'll call this spot connector。And I'll leave everything default here and again leave everything default and launch this。

What's useful about this Cloud9 environment for connecting to S instances is that I could upload my PM file and then I could launch multiple spot instances over and over again once I've set that up。

 so this is really the launching offtation。Great， so now that that's set up。

 I'm going to go ahead and launch the S instances via the AWS S request。

So I'll go over to spot request in the EC2。Cosul。And what I'll say is request spot instance。

From here， I'll go ahead and select one of these， it really doesn't particularly matter。

 but let's say big data workload And let's go through some of the key highlights of the spot interface。

 first， if you wanted to automate components of this you could launch it via template if you wanted to select a particular AMI So in this case the default is Amazon Linux。

 the newest version of Linux Linux， but I also could select。

 let's say a deep learning AMI if you're going to do Tensorflow or you know some other deep learning framework。

 this might be a good choice or if you wanted to go to abuuntu even Windows or Red Hat。

 there's lots of different options here for AMs or your own custom AI and AMI stands for Amazon machine image So you can preconfigure it as well and that's a useful way to get a head start on your spot instance in terms of networking。

 I'll leave everything default here。And the other thing that's really important is this key pair name section。

 so in my particular situation， we do is all create a new key pair。

And then I'll say create key here and we'll call this spot connector。

And this will allow me to SSH into this interface again multiple times。

 So now that I've downloaded that， I'm going to go back to my AWs cloud9 environment here。

 which should be waking up here in a second。Now that it's woken up， what I can do is I can say file。



![](img/553b0d1675e4ed622fa6d47d0e2b2ac8_1.png)

And I can upload that Pm file。 So go ahead and select that Pm file there we go spot connector。 great。

 Now that it's there。 it's ready for me to later connect to the spot instance。

 So if I go back again to my E C2 console and I refresh。

 Let's see if I can find that spot connector there we go。

 that's gonna allow me to make the connection。 So this is an easy mistake that it's a first timer could make is you forget to create a key pair and then you can never SSsH into your machine and then really it doesn't do anything for you。

 So the other thing that's important is if I go to additional configuration This is also a common mistake is you can set storage。

 you can do all kinds of things but typically the security group here is a very common mistake And what happens is that you need to create a specific security group that allows you to connect by default。

 nothing is open。 So even SSH is not open。 So how do we do this。 we can do the same thing。😊。



![](img/553b0d1675e4ed622fa6d47d0e2b2ac8_3.png)

![](img/553b0d1675e4ed622fa6d47d0e2b2ac8_4.png)

We can say create new security group。And I'm going to go through here and say， create security group。

I'll do the same thing。 I'll call the spot connect。And we can say allows。SSH。

Access to spot instances。There we go and now that I've got this set up and I need to set the inbound rule。

 so I'll say add rule。And we'll go through here and change this to a custom TCP port。

 and in our case， we'll say it's going to be port 22。

And will also allow it to access every single outside resource I could for security purposes。

 specifically assign it to my cloud9 instance， and that would be even more secure。

 but for now this is a reasonable security tradeoff now that I've done that I can go through here and say create security group。

And now that I've got that security group created， if I go back here and I go to a refresh。

 we should be able to see a spot connect here。There we go spot connect and I'll go ahead and select that so even if you create the security group if you forget to connect it。

 then you'll be very frustrated that you can't open up port 22 and again this is one of the most common mistakes。

Finally， probably a third common mistake is that if you want to access an API。

 let's say Amazon recognition or comprehend or some kind of AI API you have to set up an IAM rule and so you could do the same thing you go through here。

 create an IAM rule and then when the machine launches it can make those calls on your behalf。

 if you don't need those calls， then you don't need to set up an IAM rule， but this is a very。

 very common mistake as well。 So those are the three big mistakes that I see Finally。

 this user data section would be if you wanted to preconfigure some commands like let's say mount the elastic file system。

 this could be a reasonable place to put those commands。 All right now that I've got that set up。

I need to tell them how much capacity I need， I just want one instance。

And I'll do a fleet request as well and the fleet request all it means is that it's almost like you're making a request for a hotel room and you'll say I want a hotel room that has a king bed and I want to pay 70% off it's kind of the same thing it doesn't necessarily matter which room you're in you just want to deal so in this case you can see these are all pretty good priced and you'll get one of these。

All right， now that I go through and I scroll down here。

 you can see that the estimated savings would be about 72% and there's nine different types of instances I can choose from。

 so let's go ahead and launch this。Now once you submit the request。

 it'll be in this submit state here and what you can do to find out what's happening is you can actually click on it and it'll show you whether it's pending fulfillment or fulfilled so we can see this is in pending fulfillment and then if I go to instances here。

What you'll see is that the instances in pending state right so it hasn't been launched yet。

 so what I can do here is I can select this and I can say spot connector。

Spot right I can name it and this is often a great idea is to give in a name so that you don't later get confused about what's happening when you're launching your instance。

 it's very common to not know which instances are doing what right so I could go through here again and and we'll say spot connector。

And just make sure that it's got a name that is going to allow me to know what it is okay great。

 we see that it's running and it tells us what the type is so if I select this you can see that it' it's getting booted up right so it it's pretty much ready to go with in a couple minutes or so and so what we can do to connect to it is select this connect icon。

And it'll actually give us a set of instructions， so the first thing it's going to say is I need to run this Chamod 400 command to that PIM file。

 so I'm going to go back to spot instance virtual machine here in cloud 9。



![](img/553b0d1675e4ed622fa6d47d0e2b2ac8_6.png)

And I'm going to run this command， Chiman 400。 So this allows the correct Unix permission level to be set so that I can actually make this SSsH connection。

 Great， now if I go back to the next series of instructions。

 it says SH I spot connector and then E2 user at and then it shows me the address。

 So it gives me exactly the command to SSH into the machine。

 So we go back to cloud 9 here and I run that。

![](img/553b0d1675e4ed622fa6d47d0e2b2ac8_8.png)

You can see that it looks like it's working， it's been able to make an initial handshake so we know that the security groups work and if I say yes。

There we go。 Now I'm in Amazon Linux 2。 remember the host here was Amazon Linux 1。

 so I'm in a totally different machine， so I could go through here and say pseudo。

 you know yum update or whatever command I wanted to run here and and go through and do my commands or if I wanted to run Python or whatever it is that I need to do I have a sandbox environment to play around with。

 So that's really the key takeaway that many people you know really should be aware of when you're using spot instances I there an incredible cost savings and they're great for prototyping code and if you're doing deep learning。

 the deep learning instances can be great as well。 So how do we clean up our job here。

The next thing that I can do is if I go back to this environment here。

 I can go to EC2 and go to S requests， and this is typically the best way to clean it up is go to your spot request here。

Select it and say cancel request notice that。You want to leave this selected terminated instances so if I don't select this。

 it'll relaunch the spot instance again。 and so I want to terminate not just the instance but the request itself so I'm going to go ahead and cancel that there we go and we see it's being canceled I can verify this by going to instance and if I go to instance you can see it's shutting down and if I go back to cloud 9 you'll see oh oh it's been closed right so in a nutshell very easy to use spot instances once you know some of those gotchas that we went over。



![](img/553b0d1675e4ed622fa6d47d0e2b2ac8_10.png)

If I want to get rid of my cloud9 instance as well。

 all I have to do is close it and it'll go away because it automatically times out。



![](img/553b0d1675e4ed622fa6d47d0e2b2ac8_12.png)