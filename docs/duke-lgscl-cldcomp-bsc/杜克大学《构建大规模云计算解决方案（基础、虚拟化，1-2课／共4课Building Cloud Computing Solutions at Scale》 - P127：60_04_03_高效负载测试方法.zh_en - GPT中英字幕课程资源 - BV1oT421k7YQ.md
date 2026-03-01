# 杜克大学《构建大规模云计算解决方案（基础、虚拟化，1-2课／共4课Building Cloud Computing Solutions at Scale》 - P127：60_04_03_高效负载测试方法.zh_en - GPT中英字幕课程资源 - BV1oT421k7YQ

I wanted to start this story and talk about how load testing has saved my bacon more than one time。

 In fact， it's been one of the most effective tools I've used in my career。 One story in particular。

 that's interesting is when I was working at a software as a service company that did log analysis。

 we had many machines that were Java-based search engines that were looking at files and a lot of times they would disappear。

 And this became a critical bug for us because it would take quite a while to rebuild these servers。

 And it was just really difficult to know what's happening。

 part of the reason was because the machines were configured to not have swap。

 And what that meant was that they never saved their state。

 So we really knew never knew what was happening。 eventually。

 one of the things that we discovered was that it was a very complex and subtle issue where the machines themselves were oversubscribed with threads。

 So they had。They were told to use too much memory and too much concurrency and as a result。

 they were actually running up into a load limit where it exceeded the amount of memory that the machine would use so they would never really reach these conditions unless the machines were really under high stress。

 which wasn't that often and because there was no swap on the machines。

 they would immediately start the kernel panic where start the kernel itself would go into the outof memory agents on Linux and actually start killing things and then unfortunately because there was a supervisor process that would restart the Java processes they would get into this race condition where they would have a kernel panic so it was a very complex series of events that we really just would never have known to look at unless we did a load testing we didn't do load testing。

 I was able to detect that the old。Fashion way， but since then when I learned from my mistakes of trusting that we had an architecture that supported that level of concurrency。

 I learned that you can't trust you want to verify and so by building a comprehensive load test suite。

 we would have avoided those really subtle crashes and those subtle problems where there were really difficult do bugs so that's really what load testing does is it looks at the worst possible condition and it validates it repeatedly so that you can go in and go to the root cause analysis and fix your bugs。



![](img/08f406601061d093cd46c9a935397314_1.png)

![](img/08f406601061d093cd46c9a935397314_2.png)