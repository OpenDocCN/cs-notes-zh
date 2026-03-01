# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P20：20_03_05_使用AWS Cloud9进行云开发.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

AWS cloud 9 is a cloud based development environment。

 and it solves a lot of problems that come up when developing with the cloud。

 There are similar environments for the Azure cloud or for the GCP cloud and really they all solve the same thing。

 which is you can develop inside the environment where your code will run。 So in the case of cloud 9。

 what happens is inside of AWS， you can provision a virtual machine。

And that virtual machine has several advantages to your laptop。 One is the permissions。

 so you can actually assign it rolebased permission。 So you can talk to the APIs。

 you can communicate with other services without having to manage those keys。

 So from a security perspective， this solves a lot of problems。

 The second thing is that the traffic itself。 So the network traffic is much faster because you're essentially opening up a shell inside of the actual location where you're communicating。

 if your laptop is on a spotty wireless connection somewhere it's going solve it's gonna to have a lot of problems communicating。

 But if you open up an instance inside the actual environment that you're working in。

 you're literally communicating with the data in the place that it needs to be。

 The other thing is that there's deep integration to other services。

And so that's really the other key aspect of something like Cloud9 is that you can deeply integrate with the cloud Lambda environment。

 which is a serverless capability。 you can also deeply integrate with running command line tools so in a nutshell if you're developing for the cloud environment most likely you're gonna have a much better experience using the native tools in this case AWS cloud9 so let's go ahead and look at that next。

To get started using AWS Cloud9， you'll need to log into your AWS account。

Here we have the AWS Management console， and I'll go ahead and find a service called Cloud 9。

I'll type in cloud 9 and this partial complete will give me the result。And from here。

 what I can do is create a new cloud9 environment， so I'll go ahead and select Cate Environ。

It's typically a good idea to give it some meaningful name。

 so in this case we'll call this cloud computing。For data。And then I'll put a description， you know。

 this is a demo。environmentvironment。Go ahead to the next step here。

A few things that are key to point out is that most likely the defaults are going to be good enough for you。

 especially if you're a student and you can leave the defaults that being said I'll go ahead and point out a few of these key features so the section here says create a new EC2 instance this is allows you to actually launch a new virtual environment there's some other advanced options here that you can also select in terms of instance type。

Most of the time this free tier eligible T2 micro is a good choice if you're going through and developing things and and making you know educational projects。

 now that being said， one really awesome feature of cloud9 is if I go ahead and I say other instance type here。

 I could decide that I want to use a really large machine For example。

 let's say I wanted to test some parallel computing with I don't know a 72 core machine with。😊。

Maybe 144 gigs of Ram。 Most people don't have access to that type of a piece of hardware。

 but you can actually spin one up， be charged only by the time you use the instance and actually test some really expensive operation by doing this parallel computing。

 So that's one of the really key features of cloud9 as well is the ability to size up your instance to many different types。

 So again， I'm going go through here and just pick the default。Also in terms of platform。

 it's probably a good idea to leave the defaults in most situations， there's either Amazon Linux。

 Amazon Linux2 or in the future there could be Amazon Linux 3 or maybe something like a Boonoo server a lot of times the defaults are going to give you the best experience when you're developing your project in this particular case I'm going to select Amazon Linux 2 because it contains a slightly newer version of Python。

Another thing to point out is in terms of cost saving settings。

 the default settings are pretty good in that if you get out of your machine and you close the web browser automatically。

 it'll hibernate， save all your settings and you won't be charged for those services。

 so this is a great feature as well。This is also a key thing to point out is this IEM role。

 as I mentioned earlier， one of the advantages to using AWS Cloud 9 is that whatever account you're logged into。

 the roles will be linked for you， and so what' will happen is that you don't have to manage the keys for an API call you'll be able to talk to services like S3 and copy data back and forth。

 so this is a really key issue that you get for free with cloud9 environment。

So once I go through here and I say next， it'll take， let's say。

 30 seconds to 45 seconds to spin this up。

![](img/256dcf29b303b22b40ef85b1029720ba_1.png)

Now that AWS Cloud9 has spun up， let's kick the tires and go through the core features。

 The first thing to be aware of is this environment tab here on the left。

 And if you notice it says Tilda environmentron， this means that if I do an LS。

 there's only a readmi file located right so this is the root of the drive。

 And if I type in PwD or printworking directory， you can see that this is where I want to do all my work in home EC2 user environment。

Next up， let me show you that it's got the AWS cloud tools already installed。

 so if I type in AWSS3LS， for example， I can list every single bucket that I have in my account。

There we go， which is pretty useful if I also wanted to copy data I could just go through here and do it AWSS3C。

 so this is really an incredible feature that you get this commandlan tool with all the ways to talk to the rest of AWS for free。

Another thing to be aware of here is that I can also upload and download file。

 so let's say I want to take this readme file here and I want to download it。

 I could right click and select download and this will allow me to download it to my local machine so this is a key feature and really a super useful thing that I can do if I want to work with data in this environment likewise if I wanted to go through here and upload I could also upload local files。

 let's say it's a CSV file or like a binary that I wanted to run inside this environment。



![](img/256dcf29b303b22b40ef85b1029720ba_3.png)

![](img/256dcf29b303b22b40ef85b1029720ba_4.png)

Next， the other thing that I'll show you is that if you go to this tab on the right here。

 there's several really interesting features first is collaborate what this does is it allows you to invite other people to your project and you can actually chat so you can do pair programming in your project this works really well for groups in a class for example or teammates in a particular company and to do that you can just go ahead and say share here and then invite someone to your particular account。

 so this is a really incredible feature that I've used before to debug things in production。

If we go to the AWS resources tab here next， this is another really incredible feature is that I can actually create AWS Lambda functions natively inside of here if I go ahead and I say。

Create a new Lambda function， it allows me to go through and say you know new Lambda or whatever I want to call this function。

 say next here， and then I can select from several runtime that are preinstalled inside of this application environment。

 node JS， Python 36。And then from here I could actually select different blueprints and then configure applications so this deep integration like I talked about before is one of the key features of cloud 9 and Y typically it would be a good idea to start here versus your local laptop Another thing to point out is that there's a rich debugger and you can put breakpoint and debug your code。

Another aspect as well that we'll get into a little bit is that if let's say I want to create a basic Python file here called hello I can use the command touch。

 which creates an empty file Okay let's go ahead and edit this hello file and you can see that it's got syntax highlighting and I could put in some statement like main return one or whatever it is I wanted to do and it's going to automatically figure out what is the proper syntax of Python So there's a lot of really powerful features that are included inside of here that give you the ability to directly build applications that are cloud native and that's the key advantage of the cloud9 environment。



![](img/256dcf29b303b22b40ef85b1029720ba_6.png)

![](img/256dcf29b303b22b40ef85b1029720ba_7.png)