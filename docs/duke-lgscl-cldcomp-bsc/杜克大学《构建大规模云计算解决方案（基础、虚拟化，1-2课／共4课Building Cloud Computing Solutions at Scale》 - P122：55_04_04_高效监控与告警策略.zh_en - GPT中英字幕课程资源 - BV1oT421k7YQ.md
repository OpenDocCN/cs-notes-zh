# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P122：55_04_04_高效监控与告警策略.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

Let's talk through alerting and why it's such an important role in an organization。

 including a software as a service organization early in my career when I was managing a software as a service company that was entirely cloud- focusedcused。

 we had some real problems with machines just disappearing and after a while we started to create these alerts that went through and looked at what was happening and we would use those alerts to wake us up in the morning and fix things later progressively there was more and more problems with our software product and we really didn't have time to fix them because of the rapid development lifecycle that we needed in a venturefunded company and so as a result for close to a year。

 many of the people on this small team would lose sleep and so I would say for close to a year many nights I didn't sleep because I was woken up at two in the morning and three in the morning four in the morning and eventually having had a background and statistics I started to think here。

Are we really alerting on the right thing here or are we just essentially flipping the coin and we're just getting woken up and so one of the things that I did is I looked at a year's worth of alerts and one of the things that I noticed was that in fact there was no discernible pattern other than it seemed random and so after I went through this conclusion and I determined that basically we had lost our sleep for a year and these alerts did nothing but just made us tired I turned them off and decided that we were going to try an experiment where we didn't have these alerts for a year it turned out that for a month and it turned out that nothing bad happened。

 what was happening was we just got caught in a really a cargo cult way of thinking about alerts and it really was damaging to us and it took a long time in fact。

 even for people in the company to believe that we didn't need to be woken up constantly and so I think one of the big takeaways with alerts。

Is that just like many things in life， you can have too much of a good thing so it's really the effective use of alerts like if you're going to credit an alert。

 make sure it's actionable and it's rare so that everybody's healthy。

 you have a work life balance and you can spend your time creatively making your product better。



![](img/6a7109b1d36b6f673f7734e994629dde_1.png)