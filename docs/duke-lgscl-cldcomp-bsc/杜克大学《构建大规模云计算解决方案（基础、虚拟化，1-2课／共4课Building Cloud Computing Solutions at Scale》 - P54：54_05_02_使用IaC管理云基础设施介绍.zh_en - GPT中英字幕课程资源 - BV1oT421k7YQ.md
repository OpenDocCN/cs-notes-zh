# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P54：54_05_02_使用IaC管理云基础设施介绍.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

In this lesson， we learn to utilize infrastructure as code to manage a cloud infrastructure。

 Let's talk through the learning objectives。 First， we explain what infrastructure as code is。

Then we utilize infrastructure as code to manage cloud infrastructure。

Let's dive into a few of the key terms。Infrastructure as code itself is one of the key terms。

 and this really is code that's checked into a repo that deploys an infrastructure。

 it's as simple as that。Terraform is a popular version of infrastructure as code and it's also available to run on multiple cloud platforms。

 including GCP， AWS and Azure。Environment drift is a form of putting one environment into a state where you don't exactly know what's happening。

 and that's what infrastructure as code solves is stopping environments from drifting and changing because every time you do a deploy it。

 it rectifies that environment。A snowflake environment is a good example of what happens when you don't use automation to define your infrastructure。

 It's very easy for one person to do a change。 And then they forget about it。

 another person comes and they make a change。 before you know it。

 your environment is not reproducible。 It's a lot like the fairy tale humty dumpumpty when he falls on the ground and nobody can put them back together again。

 That's what in an environment that's a snowflake environment is like and will cover that into detail。



![](img/abd4e53066e58d1f8f8bdd41f910ea16_1.png)

![](img/abd4e53066e58d1f8f8bdd41f910ea16_2.png)