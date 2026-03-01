# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P75：08_02_06_竞价实例工作原理.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's talk through this spot instance， walkthrough architecture。

In this first example here we have AWS Cloud 9， and this is really the docking station where I'd like to do commands。

 launch other instances， really do interactive things with the AWS platform so if you wanted to programmatically you could go through here and launch a spot instance using the AWS API or you also could separately in the AWS console。

 you could go through and launch a spot instance once you go through that setup the key components of launching a spot instance are one you'll need to bid on an instance just like you had bid on an auction you can bid what price you'd like to pay to launch a virtual machine。

 It can be up to 90% off so it's a huge savings and I'd recommend this for many people experimenting on the AWS platform once you do that really there's only a couple key things to。

Take care of other than the size of the virtual machine One of them is the security group and why is this so important Well。

 what's important about the security group is this is what port you can talk to when you launch the machine so this could be let's say port 80 if you were going to run a web service or port 22 if later you wanted to go through here and SSH in to control the machine。

 which is what we'll do in another video so in this example I would want to open up port 22 in the security group or else I couldn't SSH in。

Another component of the SSH mechanism is that you'll have to use a PM file and this will be the SSH key that will allow me to connect to that spot instance Finally if I wanted to do a separate API call。

 let's say I wanted to do natural language processing or you know some kind of image recognition service call I would have to assign a role to this spot instance so that it had the ability to make those connections so really there's only a few moving pieces here。

to care about again it's the bid， the security group and the rules and the SSH key Pm file。

 and then this is why I would recommend Cloud 9 is that you can make that SSH connection from the cloud9 environment and that's why it's so powerful is that instead of having to worry about your laptop and controlling everything from there if you keep a AWS cloud 9 instance available and you shut it down when you're not using it。

 what's nice about it is you can control lots of spot instances from this one instance and you have a reliable essentially transfer station to control other parts of the AWS infrastructure。

 so let's go ahead and get started with that right now。



![](img/21fce44dccf869e975550117adea1a4c_1.png)

![](img/21fce44dccf869e975550117adea1a4c_2.png)