# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P124：57_04_06_从零构建告警系统.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's go through and create an alert from scratch first I'll open up the Azure Cloud shellll environment here。



![](img/5f7d66cce089efb257260a2611ab0090_1.png)

And this will allow me to use some of the advanced capabilities of this editing system Why would I create an alert。

 we know this， this is a way of checking to make sure things are done properly in this scenario I'm going to simulate an installation script that I want to verify does exactly what I expect it to do where to check for file if the file doesn't exist then there'll be a problem and we'll need to raise some kind of an alert for the rest of my infrastructure so first I'll make a file here has a test file so this would be the file that I would want to check to make sure it existed and then I'll create this check ba script here。

Now， from the environment here in Cloudhell， I can click on this icon for open editor and I can go through here and now start editing this file。

 which is pretty handy。 So here we go。 Here's check do S H。

 What I can do is first add a shipang line here。 And so that would be pound exclamation point user bin in V bash。

 This allows me to execute this in a bash environment。

 and then I'll go through here and put in the path of that file。 So here we go。

 also do a test statement。 if test dash F。 and I'll say file。



![](img/5f7d66cce089efb257260a2611ab0090_3.png)

So basically， if this file exists， then go through an echo that it does exist， that looks good。

Here we go， fileile exists。But what I really want to check as well is I want to make sure that this file。

 if it doesn't exist， that I have some actionable error report plus also that it returns back a nonzero status code so we'll say first this doesn't exist if I can't find it and I want you to exit to which is a file doesn't exist status code and then I close it out with a Fi there we go so we'll go through here。

Perfect， now that that's actually set up here， I can make it executable so I can type in Chamod plus X。

And then put in the name of the file great， and from here I can just run it like a script。

 there we go， check。sh。The file exists。 Now， what happens if I rename the file So if I say move config to config2。

This should show that there's a problem if I run the check again。 There we go。

 Config file doesn't exist。 So even though this is a really simple example。

 this is exactly the kind of thing that you could build into your infrastructure to verify that things are working the way you expect and then to send alerts if there's something that another human would need to do to fix it。



![](img/5f7d66cce089efb257260a2611ab0090_5.png)

![](img/5f7d66cce089efb257260a2611ab0090_6.png)