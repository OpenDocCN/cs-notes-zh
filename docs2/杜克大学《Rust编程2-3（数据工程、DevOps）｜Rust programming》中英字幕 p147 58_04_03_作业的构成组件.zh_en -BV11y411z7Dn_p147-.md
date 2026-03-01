# 杜克大学《Rust编程2-3（数据工程、DevOps）｜Rust programming》中英字幕 p147 58_04_03_作业的构成组件.zh_en -BV11y411z7Dn_p147-

![](img/0cfb9945ae78a14aa707f8c8cc7c22c9_0.png)

What are the components of a job and sometimes not only a job but a pipeline in a C ICD environment。

 So I'm going to show you Github actions。 We haven't seen in detail Github actions yet。

But I want to show you one of these projects that I follow。

 this is a rust project and it has one of these jobs right here that I want to go into more detail so all of these you could actually say that well these is a job that is doing some testing Now a job can have one or more steps and all those steps will do something in this case this job is testing the latest stable is testing the night the nightly version is checking 1。

61 on 32 beat is doing 161 on something else that I can't tell right here and then 161 regular and then doing some Python bindings testing as well all of these are independent and all of these are working correctly now。

What what is the deal here well these might fail， but this might be fine。

 so when you're trying when you're separating the concerns there。

 you are making it easier to work with and roll back or just retest。

 make changes and then retest the things that are not quite working。



![](img/0cfb9945ae78a14aa707f8c8cc7c22c9_2.png)

So let's dive into one of these one of these steps so one of these steps will have other possible steps as well here we'll have a set set up the job then clone the actual code that is going to be under test there's going to be some setup perhaps for rust which is this is what the rust tool chain is there's zoom some checks and tests and then the job is going to be completed now that is a job is a series of steps to accomplish something and and then can be part of a bigger job sometimes also referred as to a pipeline where you're going to have like a series of jobs and series of steps all doing different things。

For some sort of an objective。If we go here to the project and we'll see these GiHub action syntax a little bit better in detail later。

 but if we go and look at tests， you will see that all of these steps are right there right are defined and you have you can have some separation of concerns so that is one way to do this and all of these will have the other thing that this will have will have a sort of trigger you can have a manual trigger you can have a trigger when there's a change to the code you can have basically trigger and a pull request if you're doing with GiHub and GiHub actions you can definitely take advantage of trigger and on pull requests。



![](img/0cfb9945ae78a14aa707f8c8cc7c22c9_4.png)

And I have another job here for a different project which is called Relay from the Gettcentry organization where you can see an actual pipeline。

 so what is this pipeline doing well you have these separate things not sequential but separate that the possibility of these job doing actually something in this pipeline depends on this one。

 so this could be a matrix， this could be several jobs to trying to do the same thing and have these conditions that require go from here all the way there。

 so if say for example files change， things look correct and then you can go here and say well these job was skippped so probably was a reason why these job was skip we don't know exactly why but these are some conditions that you can start playing around with you can set certain fl and certain configurations to skip。



![](img/0cfb9945ae78a14aa707f8c8cc7c22c9_6.png)

![](img/0cfb9945ae78a14aa707f8c8cc7c22c9_7.png)

Or to enforce certain things in your pipeline。So that in a nutshell is what are the components of a job a little bit of pipeline there as well。

 all in know this is a job to recap is a series of steps and a pipeline can be also a series of steps or a series of jobs that have a dependency between each other almost like following a recipe that you can skip certain things by following a specific order。



![](img/0cfb9945ae78a14aa707f8c8cc7c22c9_9.png)