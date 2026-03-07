# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p06 p5 Week 01, Segment 06 - Homework 1： Warming up to EC2 -BV11QQcYmEzD_p6-

Hello and welcome back to CS615 System Administration。In this video。

 well quickly summarize our first homework assignment。

 which is to get yourself set up for use with AWS EC2。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_1.png)

As mentioned in our introductory videos， we'll be using E C2 a lot in this class。

 and all of our work will be done from the command line。

 So one of the primary objectives of this assignment is to get you set up in your preferred environment to be ready to use AWS tools in general and in particular。

 to be able to launch and then access E C2 instances without any problems。As a second outcome。

 you'll also be asked to run a few command that will help you prepare for our week two materials when we will be talking about storage models and file systems。

The way we will do this is， as has also mentioned in our introductory video by using the command L tools。

Now you may set yourself up for using the AWS command line tools in your laptop or shared VPS or wherever you may choose。

 but I strongly recommend that you use the She service provided to you by Stevens another Linux lab name。

In our video on the use of Git， we already covered how to facilitate your SSH access to these systems。

 and they do have the AWS command line tools already installed。

 so it'll be a lot easier for you to start there。Next。

 as the assignment asks you to run a number of commands that you may follow online tutorials。

Or the very first stack overflow answer that pops up when you search how to start using AW U and Google。

 it's important for you to actually understand all the commands you run。Likewise。

 it's important for you to understand all the output of the commands。For this reason。

 the homework assignment also ask you to provide additional commentary in your submission as well as to describe any problems you run into。

The full homework assignment is linked to from the Q website and can be found at this link here。

When you're done getting set up， you should be able to launch E2 instances pretty much as I'm about to show you。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_3.png)

That is， we start out by SSH to Linux Lab。With the AWS command and utilities properly set up。

 you have a configuration that should look somewhat like this。

Please make sure to properly protect your config file as it will contain the private access key。

Please also do not send me your private AWS credentials。 They're supposed to remain private。Now。

 to launch a new NePSSD instance as per the assignment， we'll use the AWS EC2 run instances command。

Depending on your AWS setup， you may have to specify a security group or a subnet。

 although in many cases the default security group and Snet are okay to use。

My account is old enough that it still defaults to a nonVPC environment。

 meaning I had to create non default security groups and subness for many AMIs。

 but don't let us throw you off。If you can launch an instance without specifying these。

 let's find you。Likewise， you may have a default SSH key pair that's perfectly fine to use。

I use different keys based on where I launch things from。

 which is why you see me specify a non default key here here。

You may pick an instance type of your choosing， but need to make sure to pick the right architecture for the OSs in question。

So you may run a much simpler AWS command here， but either way。

 eventually you will have launched an instance and get back a bunch of Jason as shown here。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_5.png)

Jason output， by the way， is wonderful because you can then pipe that into JQ to extract the individual fields。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_7.png)

![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_8.png)

In this case， we'll manually grab the instance Id。

![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_10.png)

And because we're lazy and don't want to have to type this over and over again。

 we'll assign it an environment variable。

![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_12.png)

We can then check what the host name of the newly created instance is。By using AWS EC2。

 describe instances and pipe that into JQ as shown here。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_14.png)

![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_15.png)

Okay， so we got the host name。Let's see if the instance is up and running yet。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_17.png)

Nope， doesn't look like it。

![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_19.png)

Let's check the status。See， isn't Rick you wonderful？If you're not familiar with it。

 you should definitely check it out and practiceracise using it。 It's quite helpful。Anyway。

 the instance claims to be running。 So let's ping it again。H。Still not working。

Now this is one of those things that's a bit annoying with E C2。 You spin up an instance。

 but then you don't know when it's ready。We'll see some ways to determine when it should be available when we review your homework submissions。

 But perhaps you can look for some other AWS command that may be helpful here。Anyway。

 let's go back and check my uping。There， after some waiting， it seems to finally respond。

 So the instance should now be up and running。 Let's log in。We specify the rightness H key to use。

As well as the root user。Evoa， we logged into our NePSD instance。

We can confirm that this isn an AM D60， for instance。

And we can take a look at the boot messages via the D message command。

 which shows us how the colonel initialized the virtual hardware at boot time。Now。

 here you'd normally run the various other commands the assignment asks you to run。But for now。

 we'll just exit。Next， since AWS' resources cost money。

 we want to make sure that we remember to terminate the instance again whenever we're done using it。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_21.png)

So we simply run the AWS EC2 Terinate instances command。And there you have it。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_23.png)

When you're done with your homework one， you should be able to launch。

 access and terminate instances， just like I've shown you here。If you run into problems。

 make sure to send your questions to the class mailing list or ask on Slack。



![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_25.png)

Also， make sure to write up any issues you may have run into and to answer all the questions asked of here。

These links shown here may help you get set up。Thanks for watching。

 and good luck with the assignment。

![](img/4cb463de1f33acfc1bd439f4b6c7ad7b_27.png)