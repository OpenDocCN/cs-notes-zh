# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P77：10_02_08_通过终端创建GCP虚拟机.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's go through how to launch a virtual machine on the Google Cloud platform。

 What we're going to do is spin up a Cloud shellll environment and then tell it from the command line to instantiate a virtual machine。

Once we've done that， we'll SSH in and then install a web server called Enginegen X。

 Let's go ahead and get started。 So first up。I'm going to select the Cloud shell here。

 so I'm going to activate this cloud shell environment。Okay。

 now that this Cloud shellll environment is ready to go。

 what I'm going to do is run a command that will launch another instance via the command line。

 so let's check out this command It's GCud， which is a main interface for launching subcommands。

Compute instances， create GCE lab dash machine type in one standard2。

 So this is a standard sized virtual machines， and then I'm going to tell it the zone。

 So this is dash dash zone。 La it in the central location。 So let's go ahead and run this command。

It's going to ask me to authorize and then this will launch the virtual machine programmatically So there's some key advantages in being able to do this from the Cloud shell without needing to navigate to the console Now you can see that this is in fact running great so what we can do is actually find this machine now。

There we go VM instances。And if you notice this machine allows us to connect to it。

 so if I want to connect to the machine， I can go ahead and select this。

Now that I've selected this machine， what I can do is go to SSH and say open SSH。



![](img/f1a09e1b08e3e57088fe6b89dd4372d8_1.png)

In a browser window， so let's go ahead and do that。Here we go。

 So you can see I've got it in another window right here and what's great about this is that I can run these simultaneously。

 so I have a separate window now that's running this terminal and I can do other things to this virtual machine。

 So what I'll do is log in as the root user。😊，So we'll go through here and log in as this route user。

And I'll run Appgit updateate， and this will allow me to update this Abuuntu operating system。Great。

 we got this thing running and then the next thing that I'll do is install Engine X。

 which is a web service。Let's go ahead and dismiss this warning and run this web service app gett install。

 So this command App gett is an auntu installation command when and you say app to get install in the name of the package。

 In this case， it will be engine X。Great， there we go， we've installed N X。

And how can we tell that it's running， well， one way you can do this is by running a command called。

PS A U W X。 So this essentially says， show me the process。

 and then I can grab through the text and find engine X。 And in fact， it is running。

 So we can see that this engine X process is running。 Great。

 So the next thing that I can do is close this。😊。

![](img/f1a09e1b08e3e57088fe6b89dd4372d8_3.png)

And go over to this external IP address and what I can do is actually open up this external IP address in another browser。

 So if I go through here and I throw this into a browser。



![](img/f1a09e1b08e3e57088fe6b89dd4372d8_5.png)

You'll notice that in fact， is running an external web service and I'll be able to connect to that EngineX host。

Well， one of the things that I notice here is that that port 80 or the H TTP port is not open。

 So what I can do is go back and go to firewalls。 So if I type in。



![](img/f1a09e1b08e3e57088fe6b89dd4372d8_7.png)

Farwall。And what I can do is create a new firewall rule and we'll call this web access。

And then if I scroll down here， I will want to make sure that it's the default here。

 which is incoming traffic and what I will say。Is the target tags？

Could be all instances in the network。And then I can say source IP range and we'll just say0。0。0。00。

 so all IP addresses。And additionally， we can select what protocol to allow， so I'll say TCP pour 80。

There we go。And then once I've selected this， this will create that firewall rule and we'll make this all lowercase to correct that error。

 and let's go ahead and say create。

![](img/f1a09e1b08e3e57088fe6b89dd4372d8_9.png)

All right， so now that that firewall rule is open， if I go back once this is woken up。

The virtual machine should allow me to then connect to that running port。

 so let's go ahead and refresh here and see if this works。 and there we go。 So we've got it set up。

 So this is another common error that you may find when you're creatingting virtual machines or creatinging resources in GCP is that you'll need to go to the firewall rules and select the appropriate port and the appropriate IP addresses that you'd like to talk to those resources。



![](img/f1a09e1b08e3e57088fe6b89dd4372d8_11.png)

![](img/f1a09e1b08e3e57088fe6b89dd4372d8_12.png)

![](img/f1a09e1b08e3e57088fe6b89dd4372d8_13.png)