# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P55：55_05_04_现实世界中的IaC.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

![](img/e708b33301c4ca0f538c3cb7ee7ee270_0.png)

I'd like to share a story about infrastructure as code in the real world。

 I was working as head of engineering at a software as a service company in the Bay Area and the founder of the company called me at two in the morning and said everything's down。

 There's nothing exists anymore。 Our entire infrastructure has been deleted。

 We were hosting things in the Amazon cloud and I looked on our dashboard and literally there was no servers available and it was really a grim time I drove into the office to see if I could figure out what was going on and later we started to figure out that what happened was there were some warnings about some retired virtual machines that had been ignored by the founder of the company they were in a spam folder and Bay eventually took these virtual machines down because there were older versions and we actually had months of notice but didn't get noticed until they finally got deleted。

So the only way to restore our entire company from scratch was to use infrastructure as code。

 so what I did was I went to our build system that had an infrastructure as code system called Puppet。

 which is an older one。That was very popular in let's say 2010 and it turns out that I couldn't get it to run it wasn't trying to figure out what was happening and later what we determined was that that version of puppet was a different version so we had kind of tweaked it and modified it and I had to find the version of puppet that we had that could basically unlock our entire ecosystem and rebuild our company from scratch。

 Fortunatelyly I found it on one machine there was a previous developer that had made their own version of puppet。

 put it on a machine， we found it and we recreated everything。

 it took a couple days but we didn't go out of business the moral a story is that I guess one thing is don't fork or change the infrastructure as code system use the default standards that's probably a best practice but the other one is how powerful infrastructure as code is on one hand we could rebuild the entire infrastructure and build an entire company。

Just by you know reinitiating everything that it did。

 but also how dangerous it is to not have a capability like that。

 it could take maybe months to completely restore an infrastructure so infrastructure as code is a critical component of modern software engineering and that's something that we're going to discuss in more detail in the rest of this lesson。



![](img/e708b33301c4ca0f538c3cb7ee7ee270_2.png)