# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P64：64_05_08_为Hugo设置AWS Cloud9和GitHub初始环境.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

The first thing I'm going to do， which I think is a good pattern for anything you're doing with AWS。

 is to use Cloud 9。

![](img/5e66241dff24869c5fbe8e769428f898_1.png)

If you've already set up Cloud9 yourself and have GitHub keys created。

You're you're pretty much good to go。 You don't have to copy what I'm about to do。

 but just so you can see it again。 this would be only again the first time you set up cloud9。

 we're gonna go through and just create the SSH key so that it has linkage to a Github repository。

 So I'll go through here and I'll say Hugo。For Duke， and we'll put， I don't know， 107。

This is a temporary environment。For building Hugo websites。Okay， go ahead and do this。

 I'm just going to leave everything default。Keep it simple。And create this environment。

While that's being created， I'm going to also simultaneously go to GitHub and I'm going to create a new repo specifically for this web application。

And we'll go here and we'll call this Hugo。For Duke 1，7。And this is a。Sample Hugo website。

For Duke class， there you go。Maybe even make this a little bit bigger。And we'll add a Readme file。

And a get ignorere now I'm going to show you something with this get ignore that's going to be actually a very subtle but important thing。

And so just keep that in mind， we're going to come back to that。



![](img/5e66241dff24869c5fbe8e769428f898_3.png)

Okay， so I created empty rebo。And then this should be almost ready。

 should just take a second for this thing to wake up。

While this is waking up and before I set up the keys。

 one thing I'll bring up about this thing that we're going to show and just I'll do very。

 very limited and theoretical， I'm just going to do mostly practical。

 but I did want to just call this out explicitly is that we're going to be using IAAS。



![](img/5e66241dff24869c5fbe8e769428f898_5.png)

To do this， and we're going to use serverless at the same time。Hugo。We'll be running。

Inside of an S 3 bucket。 And that's infrastructure as a service。 It's。

 it's object storage and object storage。 The nice thing about it is that it has。119s reliability。

 So this means it's essentially will never go down。 It's we're talking milliseconds per year and。

The serverless built on top， what that means is that AWS has an offering thatll allow us to host websites that are globally scalable。

 essentially it could be again like Wall Street Journal New York Times level。

 just with this thing I'm about to show you。So really serverless is a way of I guess making a higher level abstraction on top of infrastructure as a service。

 but really the heavy lifting here is just this S3 bucket okay so this thing woke up and what I'm going to do first here is create the SSH keys again one more time I'll bring this up。

 you only have to do this the first time you create cloud9 if you've already created one of these don't worry about this。

 but I'll go through here and say SSH keys。Make them so SSH， keyjin， T， RSA。Press return。

 I think five times。 and then print this out this， this public key。

 So this is the public portion of a。An SSH key which is the part that you can share with anybody。

 I could put this on a website and it wouldn't matter。

And I'm going to go to the icon where my profile is。And then go to SSH and GPG keys。

 so a pretty pretty straightforward process to put your keys in， we'll just say Huo keys。Here we go。

And we'll confirm this。So once， once I've got that set up。

 then I'm going to go back to that repo that I created and check it out locally so that。

We've got this thing ready to go， so Hu go， Hugo for Duke， I'll click on this。

And this what I just showed you is probably going to be very common。

For many things that you would work on from the very beginning or if you're first starting at a company。

 this would be what I would recommend doing something like this。



![](img/5e66241dff24869c5fbe8e769428f898_7.png)