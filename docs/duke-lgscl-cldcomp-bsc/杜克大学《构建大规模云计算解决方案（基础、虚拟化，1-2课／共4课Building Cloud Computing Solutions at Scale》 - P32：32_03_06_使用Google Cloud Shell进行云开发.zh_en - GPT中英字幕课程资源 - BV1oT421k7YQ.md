# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P32：32_03_06_使用Google Cloud Shell进行云开发.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

This is the Google Cloud platformform console and just like other cloud platforms。

 there is a Cloudhell environment that I would recommend for a Python developer。

 especially to get started with when you first start doing things in that cloud platform you can find that by going to this icon here and selecting Activate Cloud Shell。

When you click on that it'll spin up a cloud terminal and it'll have some pre-installed things on there that are very helpful。

 like a version of Python， some command line tools that come with the Google Cloud platform that lets you do administration and so really this is one of the core features of why a cloud channel environment is so important。

 And I would say this is really the default starting point for most of your projects。

 So once I go through。

![](img/fc6b049d57d5f404e2a18345edb29c27_1.png)

And I open up the shell here。 The first thing I'd probably recommend is just kind of kick the tires a little bit。

 So one of the things you can do is you can type in which Python and you can see that there is a python right there So if I run it。

 what is it Oh this one's a Python 2 So let's see if there's a Python3 here so if I go through here and I say Python3 Great I've got a Python3 as well So I would recommend creating a virtual environment and you can do it one of two ways on the Google Cloud they've pre-installed the tool called virtual environment So if I type in virtual enV I can actually go through here and run virtual enV and then create a new environment called this GCP。

Cloud。And go ahead and do that and notice how I put it into this tilde slash dot format so that it's hidden away and kind of out of my way here and then when I source it。

I'll go through here and say Tilda/ dotgCP cloud。GCP cloud bin activateate， there we go。

The next step that I would probably do is start to work with checking out a GitHub repo and so what I'm going to do here is。

Go to a gett repo that I've got set up。

![](img/fc6b049d57d5f404e2a18345edb29c27_3.png)

And I'll navigate over to it。 And this has got really everything I need inside of this。

 It's got some Gitthub action so I can test my code。

 It's got a really simple you know hello file here that just adds things together So I'm gonna go ahead and clone this and so how do I do this Well anytime you create a new environment and you haven't communicated yet with Github you'll need to create SSH key。

 So I'll just remind you what that would look like in this case it would be SSH hyphen keygenin T。



![](img/fc6b049d57d5f404e2a18345edb29c27_5.png)

RSA and then you would press return return and notice I've already done this so I don't have to do this。

 but in your case you would say you would just keep going and it would create this public key once you do that you would then need to put those keys into GiHub and that could actually be done via clicking on your profile over here。

But I'm just going to clone this， so I'm going to select this code icon here。

 make sure it's set to SSH and go to this and clone it， so we'll go ahead and say get clone。

And looks like this has already been cloned so I can actually just seed into it。

Do a get pulled to see if there's any changes？And looks like there's some small changes here now how to actually run this code。

 well if I type in and make install because I like to do make files here。

 it'll go through and check to see if I've got any new packages to install and looks like there's some updates here。

And I'll go through here and install this now。One of the things to point out here is if you're not a huge fan of doing everything in the command line and using command line editors。

 it also has a full IDE here so if I go ahead and I select this icon open editor。

 I can actually move this up。

![](img/fc6b049d57d5f404e2a18345edb29c27_7.png)

And get access to a full IDE here that I can actually play around with and you know build out a fullfledged project。

 so let's go through here and let's find this project that I've been working with So this one I believe is called what do we call this we call this。

GitHub actions demo， so let's go ahead and find that GitHub actions demo。 and if I select make file。

You can see that here's the make file。 And then if I go to hello， you can see here's a hello file。

 So if I wanted to， I could go through here and modify things。

 So the main takeaway here is that just like your laptop。

 the cloud environment in Google cloud platform really has everything you need。

 It's got the editor plus it's got a terminal and I also can do things like if I run GCud for example。

 it's got built in tools that are hooked into managing the Google cloud platform。

 So that's really the key takeaway， just like most cloud platforms is that you can tweak everything is saw project。

 go through here， kick the tires， you know run things and actually one other thing that I'll show you that's a neat little trick is if I go and I look at my history here and I go through here and I find let's say something I did with G cloudud。



![](img/fc6b049d57d5f404e2a18345edb29c27_9.png)

So if I want to go through here and log into my account to do some heavy lifting。

 how would I do this， I would type in G cloud off list。



![](img/fc6b049d57d5f404e2a18345edb29c27_11.png)

It would pop open a authorization， which would allow me to make API calls。



![](img/fc6b049d57d5f404e2a18345edb29c27_13.png)

And we'll go ahead and do that and now what I can do is I can actually run a cloud function that I built earlier that will translate some text from Wikipedia and translate it to a new language。



![](img/fc6b049d57d5f404e2a18345edb29c27_15.png)

Here we go and you can see here that not only can I build out and make my own projects。

 but I can call into the cloud environment， so that's really the key advantage of a cloud based environment is the hooks into everything else。



![](img/fc6b049d57d5f404e2a18345edb29c27_17.png)