# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P57：57_05_06_在GCP上使用Terraform启动虚拟机.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's go through the Google Cloud shellll and use infrastructure as code with  Terraform to launch a virtual machine。

 First， I'll activate the Google Cloud Shell。 This will allow me to build solutions interactively using the B shellll。



![](img/bade02eab65b3b45eb8e3dbba9a314e7_1.png)

First up， I'll create a terraform command just to double check that it's installed right this is always a good idea and we can see that it's installed。

 you can see all the different options。Next up， what I'll do is I'll create an empty file called instance。

tf that will store my configuration that will launch our virtual machine。

Now I'm going to use the editor here so I'm going to say open editor and then this will actually let me edit in a gooeI environment。

 so this might be more helpful for people that don't have a lot of experience with a command line tool so let's go ahead and do that Here we go Here's instance。

 Tf and what's nice is you can see that this editor is also recognizes that it's a terraform file so it's got good support for it。



![](img/bade02eab65b3b45eb8e3dbba9a314e7_3.png)

So I'm going to copy the configuration data， I'll put it in here and notice that the only thing I'm going to need to do is put in my project ID inside of this section。

 I can get it by going up into the project ID section and grabbing it out of here。Great。

 copy that and I'll just paste this inside of this project ID。

Perfect now that I've got this project ID set， let's go through this configuration。

 So first I call this terraform right that's the name of the virtual machine。

 The machine type I'm going to select is in one standard one and this is the zone where this is the place inside of the Google cloud So the central part of the United States that I'm going launch it and then I tell it is well what image I want to run。

 So I'll tell it to run Deion 9。 and then I have a default network configuration。 So again。

 what's great about a infrastructure as code type configuration is that it's all defined it's declared inside。

 And if I check this later into a source control repository。

 other people can look at it and see exactly what's going happen。 So great。 this looks like it works。

😊，So let's go through here and save this out so I'm going to say file save perfect。

 and then I'll go ahead and go to the terminal Now that I've got the terminal open here。

 what I can do is do terraform and knit so I'll type in terraform。



![](img/bade02eab65b3b45eb8e3dbba9a314e7_5.png)

And then。Great， and so what this is going to do is in the background。

 make sure that I've got everything I need for Google to go through and run the infrastructure as code steps。

Great， you can see here that it downloaded the latest provider， which is the Google provider。

Now the next thing that I'm going to do is plan and this is a way of verifying that things will go the way I hope they go when I actually do the deployment。

 so let's go ahead and do that let's type interraform plan。All right。

And you can notice here that it goes through and it tells me all the different things that it's going to do。

 So terraform will perform the following actions， you know it tells me all the different configuration options。

 all the things with a boot disk right so it's pretty much ready to go and if I want tom I can now go ahead and apply that change so make the infrastructure work so to do that I'll type in terraform apply。

Terraform and a lot of times if you autocomple， it's a great way to make sure you don't make a typo。

 and let's go ahead and do terraform apply。And this actually goes through and performs these steps。

It's going to ask us a question， you know do you want to do these steps or not。

 and so I'm going to go ahead and say。Yes， to approve it。



![](img/bade02eab65b3b45eb8e3dbba9a314e7_7.png)

Perfect， and it's going to ask me to authorize this call。

 And then behind the scenes now it's going to go through and create that resource via the API on my behalf。

 And that's again， one of the great things about infrastructure as code is how useful it is in terms of simplifying the deployment process and making it repeatable。

 This will typically take a few minutes for the virtual machine to be available。

 so we'll wait a second and see what happens Great。

 it's already available you can see that it's complete。 So how would I find this virtual machine。😊。



![](img/bade02eab65b3b45eb8e3dbba9a314e7_9.png)

![](img/bade02eab65b3b45eb8e3dbba9a314e7_10.png)

Well， we could go back here and find this virtual machine inside using the instances。

So to find this virtual machine we could go to the dashboard and look at the compute instance resources here we go compute engine and there it is the virtual machine is running this is exactly what we told it to do it saysterraform is the name here's the zone it's in here's the IP address and if I wanted to I could also go through here and connect via a browser window and SSAT into it and do whatever work I needed to do there we go you can see here that everything was able to launch correctly so in a nutshell terraform is itemem potentent way to launch and configure resources and this is just the tip of the iceberg about what you can do with terraform。



![](img/bade02eab65b3b45eb8e3dbba9a314e7_12.png)

![](img/bade02eab65b3b45eb8e3dbba9a314e7_13.png)