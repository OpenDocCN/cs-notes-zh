# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P39：39_04_03_构建多网站介绍.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

In this lesson we go over building multiple websites。 This includes static websites。

 serverless websites， virtualized websites and platform as a service。

 Let's take a look at the learning objectives。First， we build a static S3 website on AWS。 Next。

 we build a serverless website on AWS Lambda。We'll follow that up with building a website on an EC2 virtual machine。

And then finally， we'll build a website using pass AWS Beanstock。

 Let's go ahead and divide those terms up into some digestible chunks。

So the static website you may hear this a lot， it really means that you're generating HTML files and putting those HTML files somewhere like Amazon S3。

 why this is such an important technique is that it removes it the need to actually have servers in between that render out HTML。

 and so really it's the most modern way people are developing web applications。

 especially in terms of content management。S3 is another key term。

 it stands for object storage and it's Amazon's object storage system that has 119s reliability。

 so that means that it's 99。99999 etc cetera， reliable so essentially it's down for let's say a millisecond or so per year and that's one of the key advantages of S3。

AWS Lambda is a serverless technology that allows you to take a function and we'll cover a Python version and hook events to it。

 those events could be websites， that could be messages from a queue。

 that could be an event that you process， let's say a file goes into an S3 bucket。

EC2 stands for a virtual machine and Amazon has a couple flavors of this。

 one is on demand where you pay a little bit more for。

 but you can spend up a virtual maning time you want。

 and there's also spot instances which allow you to basically bid on a low price and use a virtual machine for an experiment。

AWS Beansstock is a platform as a service offering available in AWS and we're going to use it in conjunction with Flask to deploy a Python based web application。

 let's get started。

![](img/9d1b75bb7303361b7a0b471c76ba5d6f_1.png)

![](img/9d1b75bb7303361b7a0b471c76ba5d6f_2.png)