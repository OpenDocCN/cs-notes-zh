# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P43：43_04_08_在EC2虚拟机上构建网站.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

In this section， we're going to get into building a HP or web server on an EC2 spot instance。

 How will this work， Well， in terms of architecture， first。

 we'll spin up a cloud 9 development environment。And then we'll also register a new Pm file that Pm file will allow us to make an SSH connection to the spot instance that will spin up。

 then we'll go into the console。Until tell the spot request to launch a new spot instance and this allows us to really get a good savings like maybe you know pennies on the dollar you know let's say it's 80% off to launch a spot instance is a little bit like a bargain store where if you want a prototype things a spot instance is a great way to try out a resource and it'll launch a virtual machine that we can do some testing on so then we'll go through and we'll install a web service get it running and then test it out in our browser and that'll give us a full prototype So this is really the idea here is when you're building things in the cloud if you do want to use a virtual machine this is gonna to be a great way to use this formula and it's something that you can repeat over and over again let's get started at how we can set up this Linuxbased web service First step we'll need to create a Pm key So I'm going to go to the console here and say。

Create key pair and I'll make this key pair called Ho web service。

And I'll leave everything default here and create this key pair。

 This will allow me to download this and put it into our cloud 9 environment。

 So I'll go over to cloud 9 now， refresh this。

![](img/1b8103e8e79e96cbf3a03c8d33254a38_1.png)

![](img/1b8103e8e79e96cbf3a03c8d33254a38_2.png)

And upload that Pm file。So we'll go to file， upload local files。And put that in there。

 great now because I've done that， I'll be able to do an SSH connection so we've been able to get these first three steps completed fairly quickly what I want to do。

 although I didn't do step two， we'll also want to create a security group so next step I'm going to go to the EC2 instance。

Cons here， and I'm going to go down to security groups。

And security groups allow us to open up specific ports。

 and we want to open up port 22 for SSH and port 80 for the web service。

 So we'll go here and we'll call this hello spot web service。

And it just we'll say this is for a spot web service。Great， I can leave everything default here。 Now。

 the only thing I need to do is add these two inbound rules。

 So the first inbound rule would be port 22。 And what we want to do is let everybody make a port 22 connection。

And then I'll also make another one for port 80， this will allow me to test out a web service and websites typically do want to have everyone have access to them unless they're a special internal web service。

Great now that I've created those two security groups inbound rules。

 I can now use that in the Pm file when I launch an instance。

 so we're pretty close to being ready to go here， I'm going to go over to Spot requestquest now and tell it that I want to launch a new instance。

Let's go ahead and go to S request here and I'm going to say request spot instance。

 and I'll also say I want to do a， you know I can select big data workload。

 that's a good template and I want to change this AMI here so that it's set to Amazon Linux too。

Let's go ahead and set this up。And this looks good， we got Amazon Linux2 here， quick start。

And if I scroll down here。The main thing that I'm going to need to make sure that I change is the ski pair right we know that we have one called hello。

 so I'm going to go ahead and find that there we go hellello web service， so that allows me to SSH。

And then the other thing is that I'm going to need to change the security groups because we know that we need to be able to SSH into this machine。

So here we go， here's Hello S web service， there's that group we set up。And from here。

 I'm pretty much ready to go， I can leave this at one target， I don't need to launch more than one。

And you can see here that I'm going to get roughly between 70 to 80% off。Okay。

 I'm going to go ahead and launch this。And whatll happen is when the request is submitted here。

 you'll see it'll go into this submitted state and if I click on the request ID。

 it'll show me more information about it and whether it's been fulfilled yet。

Typically what I do is I'll go to the instances now。And I'll look for the instant state。

 and you can see here that it's actually an pendingending state。

So we can refresh here and hopefully there we go looks like it's starting to initialize。

 so from now I can actually name this something I think that's always a good idea is to go through here and change the name and we'll call this spot web service that way I know what it is and I can easily terminate it later。

And then I'll also go and say connect。 and it'll give me the SH connection instruction。 So step one。

 they want me to run this Chamod command。 Chamod 400。

 So I'll go back to my cloud9 environment here and I'll run that particular command。

 Let me just move this。A little bit up here， so it's at the same level， we'll do this。There we go。

 So we'll say Chaad 400 Hello Web service Pm。Great。

 and then the next step will be to actually connect to it so I can go through here and copy this。

 and it will allow me to use that Pm to connect to this machine。Great， let's go ahead and do that。

Looks like things are able to connect here。 and so then I'll go through here and type these commands I had later。

 So first thing is I'll update the software on this machine。There we go。

 so this will update things here。That looks good。And while that's updating。

 the other thing that I'll do next is I'll want to install this HCP service so I'll kind of get that teed up。

There we go， next step， let's install that web service。

Great that installs Apache and then we can start Apache so we can go right here。And。Go back。Perfect。

 so now that the web service has started， what I can do is actually test it out and we know that that web service should be available。

Here， if I go back to this instance。And I go to this public address。

 I should be able to put this into a web browser， so let's go ahead and do that。And there we go。

 we've got a test page， so we've actually got things running now if I wanted to add more content to this。

 what I could do is I could go to this directory and fix it and change it up。

So let's go ahead and do that， let's go ahead and change some code here in the VarR WWWH directory。

 how would we do this so first up I would run this command which would allow the EC2 user to become as part of thepache group there we go Next up I would tell that new permission level to own those web directories that's where the data served out of。

And then I'm going to add these right permissions here。

 group right permissions so that basically in a nutshell。

 it'll make it so that I when I create a directory。

 they'll be created in a way that won't cause file permissions issues so if I go into a Var wwW here。

 we should see there's a file called HTML and what I could just do is say touchindex。 HTML。Html here。

And I could edit it。And we'll just put some HTML in here， HTML。And we'll say。Here。😔。

Maybe just a paragraph tag。Just say hi。And then in paragraph tag， there we go。

 and then maybe just close this out， we'll just say。Close out this HTML tag。Perfect， okay。

 it list looks like it's good to go and then I should just be able to restart this web service。

Let's just let's see if this restart command will work。Looks like it does。 And if I go back here。

 do we have a new web page。There we go， we have hi so pretty straightforward as well to do this the old fashionioned way and to put a file onto a web service there's pros and cons to this approach to the pro is that you have complete control and it's relatively straightforward to create web apps。

 the con is that this server is always running and you're paying for it unlike a static hosted website under S3。



![](img/1b8103e8e79e96cbf3a03c8d33254a38_4.png)

![](img/1b8103e8e79e96cbf3a03c8d33254a38_5.png)