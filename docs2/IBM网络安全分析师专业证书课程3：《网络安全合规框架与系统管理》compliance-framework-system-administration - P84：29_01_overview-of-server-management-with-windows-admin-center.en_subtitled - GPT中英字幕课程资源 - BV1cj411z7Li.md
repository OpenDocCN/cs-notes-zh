# IBM网络安全分析师专业证书课程3：《网络安全合规框架与系统管理》compliance-framework-system-administration - P84：29_01_overview-of-server-management-with-windows-admin-center.en_subtitled - GPT中英字幕课程资源 - BV1cj411z7Li

![](img/8ae598164c94730a2774a956971eabe5_0.png)

In this video， you will learn to。Define types of active directory groups。

Describe an overview of features and tools within the Windows Administration Center。

 We're going to talk now about server management with with the Windows admin Center。



![](img/8ae598164c94730a2774a956971eabe5_2.png)

![](img/8ae598164c94730a2774a956971eabe5_3.png)

And leveraging active directory groups or security groups to manage accounts and to manage servers。

For active directory there really are two types of administrative responsibilities。

 service administrators and then data administrators。

 so service administrators are managing things in the environment such as what I have access to what I can do on on my device or with resources on the network and then there are what we call data administrators who are actually managing access to the data in the environment so things like customer records or employee records or any kind of sensitive information that the average end user doesn't need access to and there are two types of groups with an active directory by which we manage those so there's a distribution groups and those are used to create email distribution lists and then security groups and those are used to assign permissions to shared resources。

 you everybody in active。is going be part of a distribution group because most organizations are going to control their email through active directory。

 sign into AD and that's how your email is delivered to that particular machine know I launch I log into the machine launch as an example Microsoft outlooklook and then because I've logged in the machine as my AD account the machine knows。

 hey that this is this person here's the email is assigned to that person and so my email is delivered to me outlook through active directory essentially and then there are security groups which are assigned permissions to shared resources and when we say that they're used to assign if I'm part of a security group。

 that means that I have access to particular shared resources， the AD administrators。

 the person who actually assigns the permission but the security group is what controls the permission so through a security group I have access to particular service。

VersParticular printers， whatever is part of that security group in the environment。

And then let's talk about scope around those groups。

 so any group that is created within active directory is characterized by a scope which means the extent that that group is a part of the domain and what they can do in the domain and there are three scopes that are defined by active directory。

 universal global and domain local， and really this level of detail is more than most people would need to know about active directory。

 where we're really getting into kind of the minutia here but just things that are interesting to know about active directory。

 so when you first create an active directory domain or when an organization creates an active directory domain。

 they have these default group such as the domain admin groups and that's a security group that controls the domain basically。

And those predefined groups help control access of those shared resources and those specific domain wide administrative controls within Act directory。

The Windows admin Center is new with Windows Ser 2016 and that is a browserbased management tool that you can manage your Windows servers。

 it gives you really full control over all aspects of the server infrastructure and it's really useful in managing servers on private networks because they're still connected to your domain。

 but they may not be connected to the internet， many organizations will not connect their servers to the internet because they worry about about breaches in those kind of things。

 so the Windows admin center allows you to control those servers remotely even if they're not connected to the internet。

 and that is really one of the ways that organizations manage those servers through the Windows admin center they may have other tools as well。

 but that's one of the main ways that servers are managed through a Windows environment in an AD environment。



![](img/8ae598164c94730a2774a956971eabe5_5.png)