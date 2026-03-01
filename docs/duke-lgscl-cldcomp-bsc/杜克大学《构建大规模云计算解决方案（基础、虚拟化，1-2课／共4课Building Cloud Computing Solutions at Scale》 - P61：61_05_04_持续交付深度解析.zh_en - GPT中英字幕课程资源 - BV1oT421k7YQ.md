# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P61：61_05_04_持续交付深度解析.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's dive into continuous delivery and get into the details。

 a good question that maybe comes to mind if you haven't had a lot of experience with continuous delivery is why are we doing this。

 what problem does continuous delivery solve and really it is the Kaizezen problem I talked about it earlier how Kayzen is a concept that means continuous improvement so continuous improving what you're doing to make it better and in order to do that。

 you have to have automation and in order to always improve you have to have a set of quality controls so you need to test your code automatically you need to have an infrastructure thats item potentent or able to be deployed over and over again and the deployment itself has to be automated so that you can deploy it to whatever environment you need to so in practice the way this works is a developer is busy doing their work and they push。

Their code into source control So right here。Instead of GiHub。

 depending on what branch you push your code into， it'll trigger a change in the build server。

 Now the build server would then go through and test the code to make sure that there's no bugs。

 maybe link the code also it would look at the infrastructure as code using terraform or Pmi or cloud formation or whatever infrastructure as code service and then provision that particular cloud once that cloud is provision。

 maybe nothing has to change because there's no infrastructure changes but they could then you have this particular environment ready to go and you can test out your changes likewise if it was getting closer to production。

 maybe you would merge the master branch into the staging branch what would happen again is it would trigger a deployment process you would test your code Ly your code do infrastructure as code there's a new change。

 maybe there's a more powerful database that would get provisioned and then you could do。

Some kind of a load test right maybe in the staging environment。

 this would be where you would want to do some performance testing and determine that your application could accept 100000 users once you've done that。

 then you can merge again from staging to production and then automatically deploy those changes to your user So really the process of continuous delivery is in a way really intuitive。

 you're always making things better。 it's completely automatic。 there's not a human involved at all。

 the only place the human involved is the human is making the changes that originally go into the source control repository after that。

 there's no humans involved pushing buttons， making changes in a different location。

 So this is a great way to to really basically do a quality control checklist for continuous delivery if this is completely separated。



![](img/e01fec82762151aa40e8fbc125588d75_1.png)

From humans， then you know you have continuous delivery if humans are involved in any of these steps here where。

That it's required for a operations person to provision a machine or somebody in QA has to change some things around or change a configuration。

 you don't have continuous delivery， continuous delivery means that your code is always in a improved and deployable state it doesn't necessarily mean that you went directly to production but you could and that's really the advantage of using continuous delivery is this automated way to constantly improve things and in a speedy way get new changes to your customers。



![](img/e01fec82762151aa40e8fbc125588d75_3.png)