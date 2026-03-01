# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P31：31_03_05_持续交付介绍.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

What is continuous delivery If you've been around a software team， you'll have heard this term。

 This term means that the code is always in a deployable state。

 both in terms of the application software and the infrastructure needed to run the code this is really a modern best practice for code that needs to be deployed in a cloud in the old days。

 it used to be very difficult to completely get an automated infrastructure due to the fact that there's only a physical server if you wanted to have another version of your infrastructure。

 you would have to buy another server in the cloud。

 everything's virtualized so you can use infrastructure as code to automate and create essentially an infinite amount of new environments and if the build server is set up to listen to your source control repository you can go through a series of actions。

 a test phase， a Li phase， maybe some load testing and then your。Structure as code。

 will check the infrastructure and make sure it's set up properly and then deploy that code。

 So really， it's a modern software engineering best practice for cloud native applications。

 and really， all companies should be using something like this。

We talked about this earlier in terms of theory about what continuous delivery is。

 but let's dive into the details。 The way it works is you as the user。

 you may be developing code on your laptop and you'll check in your code into a source control repository and typically you would have。

 let's say the master branch here， which is the default branch and Github be the place where it would be hooked up to a particular environment what that means is that when you make the change a build server and this could be many different types。

 it could be， for example GiHub actions is one type it could be Jenkins。

 it could be a cloud nativeative one for example， like AWS code build。

But the core idea here is that this thing is where all the work is done in this build server right here and so all the work is done here and it goes through and it lynch your code。

 it test your code， it then deploys your code by checking out the branch that you've told that particular job to listen to and then it looks at the infrastructure as code and this could be terraform。

 it could be cloud formation， it could be some other kind of infrastructure like Pmi。

And and this infrastructure as code allows you to dynamically update a new environment or even create one。

 and typically that environment will be directly mapped to the branch in your source control so for example。

 you could have a development branch。You could have a staging branch。

And you could have a production branch and in each one of those situations。

 those branches could automatically create。A parallel environment。

 What's nice about that is that you could push your code into a development branch and that's maybe where you work most of the time。

 And then when you're ready to test， let's say a change that would be something that would go to production later。

 you can merge it into a staging branch， it'll automatically go through Lyn code test your code deploy it to your staging environment。

 you could then do a very extensive load test to verify that your web application could maybe scale to 100。

000 users and then after that's done， you say great。

 let's go ahead and merge it to production and it could go directly into production and what would happen is that it would do the same thing it would go through。

 take your code from staging that got merge into production。Lent the code， test the code。

 deploy the code So the core idea here is that really you're building a factory and the factory is just like any other factory where you want to have quality control。

 you want to have automation in this case though the factory build software and the deployment target is the infrastructure in the cloud and so continuous delivery means that your code is always in a deployable state。

 it doesn't necessarily mean you have to automatically push it to production because I could stage it in the staging environment but when I do want to push it to production。

 I can automatically do that by merging my code into a production branch。

 go through a series of quality control tests and then actually push that out。



![](img/98735f4e86920962a8e77f77149984a5_1.png)

![](img/98735f4e86920962a8e77f77149984a5_2.png)