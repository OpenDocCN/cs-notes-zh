# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P62：62_05_05_使用Azure持续部署Flask机器学习应用.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's go through an end to end continuous delivery process using Azure Pis。

 Azure app services and a flask machine learning application。

To start out with here is the interface for Azure DevOs organizations。

 I'm going to select this project that I've got set up here， flaskml deploy。Next。

 what I'll do is I'll look at this pipeline section。

You can see that I've recently run this application and if I click on this link。

 this will get me back to GitHub so you can see this is the application that I've got wired into this Azure pipeline service。



![](img/4b91cdd66c296f8a63c43bce7efa6f93_1.png)

And also， if I go to Azure Cloudhell。I can actually look at the name of this application。

 which is right here， and if I go ahead and open this up in a new tab。

You can see that it's actually a running service and it's also available via a predict API。

 and I can look at that from this file。Make predict Azure app。

 And you can see that I'm going to do a post operation using this script。

 So this is going to do this machine learning prediction。 So I'm going to go ahead and run that。

Verify that the service is serving traffic correctly。Great， that works。

 So we're really ready to go to make a change。 So how do I do continuous delivery。

 how to make this change Well， I can go to my get repo here， go to the application。

 and because Azure pipelines is hooked up automatically to listen for changes。

 I can easily make a small tweak and verify that it works。

 I'm going to go down to here and where it says psyt learn prediction home from Azure pipelines。

 what I will say is continuous delivery。 So I'll add next an extra statement here。😊。



![](img/4b91cdd66c296f8a63c43bce7efa6f93_3.png)

Here we go。So now I've added that extra statement that will allow us to verify that it will trigger a deploy。

That event， if we go back now to the pipeline and I select this service。

 we should see under pipelines that a new release has been triggered。 and in fact it has。

 so it's listen to that new event and it's queued up so I can actually just watch this if I select this and we can see it step by step go through and do the deploy first it'll build the application。

Once the build job is done， it usually takes a couple minutes， then it'll deploy the application。

 and then at that point I can even look in the log files and find the file thatll verify that it was actually deployed correctly。



![](img/4b91cdd66c296f8a63c43bce7efa6f93_5.png)

![](img/4b91cdd66c296f8a63c43bce7efa6f93_6.png)

Okay， it looks like things have deployed correctly。

 What I'm going to do is look at this deploy web app change and inside of here。

 I can look at each of the steps， Down artifact， use Python version。

 I'm going to select this icon here。 and if I go to the app service application URL I can go ahead and select that。

 So I'll open up a new terminal and let's see our changes are actually reflected here。

 So this is very powerful and maybe as a final step。 what I would do is go into。



![](img/4b91cdd66c296f8a63c43bce7efa6f93_8.png)

![](img/4b91cdd66c296f8a63c43bce7efa6f93_9.png)

Maybe the cloud shellll environment and do a final modification， but in a nutshell。

 we've been able to do end to end continuous delivery and make the change using Azure pipelines。



![](img/4b91cdd66c296f8a63c43bce7efa6f93_11.png)

![](img/4b91cdd66c296f8a63c43bce7efa6f93_12.png)