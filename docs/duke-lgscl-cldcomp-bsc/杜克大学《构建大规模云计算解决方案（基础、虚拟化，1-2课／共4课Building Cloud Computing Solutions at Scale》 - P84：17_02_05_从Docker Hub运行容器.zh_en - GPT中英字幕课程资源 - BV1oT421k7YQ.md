# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P84：17_02_05_从Docker Hub运行容器.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's run a container from Docker Hub Docker Hub is the world's easiest way to create manage and deliver containers according to their official documentation。

If I go to Docker Hub， one of the nice things about it is I can sign in if I want or I can also go through here and look at existing container。

 So one that's a good container to look at is Jupiter so if I wanted to set up a Jupyter-based environment on my OS 10 or Windows machine。

 it could be quite complex and one of the nice things about this Jupyterbased workflow is I could just scroll down here and do this Docker pull command so if I go here and I copy it and I go over to this terminal I can actually paste this in and set up。

A very complex Jupiter notebook workflow that the experts that created Jupiter can give me。

 So one of the things that's powerful about this ecosystem is that later I could then go through and try out different versions or maybe a more complex Jupiter setup without having to do anything to my local environment So you can see here that I've downloaded that newer image great。

 so let's look at the official docs here and see how we could actually leverage this。

 So one of the things that we could do is we could say this， we could say Docker run。😊。

And if I wanted to physically run the latest copy， I could say Docker run。

Jupiter sciippi notebook and put colon latest if I wanted to get the latest or some other version。

 so let's go ahead and do that。

![](img/cf7db06567df839741d64dbbfe634d09_1.png)

And what will happen is it'll spawn open a Jupyter notebook that has got all the latest features and everything installed for me。

 and this is really a big deal in the fact that it eliminates a vector of really confusion So I'm going to go through here and I'm going to put this in and there we go。

 So now you can see that I've got a Jupyter instance running and in fact I can see the output is in foreground mode here。

 So if you're playing around with Jupiter and Python。

 this is probably the recommended workflow for many people， especially if you're new to data science。

 and if I go here and I say new， I can select Python 3。

 if I want or I can even select a terminal so let's try that out real quick and just see what's going on here if I say you name a。

 you can see that it's actually running Linux itself So that's one of the really powerful things about this particular environment I can even run top I can see what's going on。

particular machine and so it it's a really powerful way to develop locally without having to really maintain this extremely complex workflow。

 So next up what I'm going to do is I'm going to say new I'm going to say Python3 and I'll go through here and try something out so here's a pandas library so I'll say import pandas as PD is a very common workflow as a data scientist and I'll create a data frame I'll say PD。

read CSv。And I happen to have some data that I've used previously in terms of my research in sugar consumption。

 and I'm going to put this inside of this。URL， right。

 and then I'll create this data frame and if I say Df dot describe。You'll be able to see。

 I'll just tab completete that。There we go you'll be able to see all of the descriptive statistics so this shows the sugar consumption by state and by education level right and so there's a correlation between education and sugar intake negative correlation so what we're going to do next here is do a plot so I'll say D plot and then you can see there's a visualization so in a nutshell really powerful way to develop complex applications without having to touch your operating system at all。

 the container itself solves a problem for you so I think whether it's a Jupyter notebook where it's a Postgres database or it's let's say a big data system this is the way to go in terms of simplifying how to get involved with systems engineering。



![](img/cf7db06567df839741d64dbbfe634d09_3.png)

![](img/cf7db06567df839741d64dbbfe634d09_4.png)