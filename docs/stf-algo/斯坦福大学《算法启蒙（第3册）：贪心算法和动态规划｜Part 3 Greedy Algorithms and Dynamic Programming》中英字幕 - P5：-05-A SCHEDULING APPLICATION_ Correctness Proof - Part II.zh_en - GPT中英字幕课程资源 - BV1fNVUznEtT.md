# 斯坦福大学《算法启蒙（第3册）：贪心算法和动态规划｜Part 3 Greedy Algorithms and Dynamic Programming》中英字幕 - P5：-05-A SCHEDULING APPLICATION_ Correctness Proof - Part II.zh_en - GPT中英字幕课程资源 - BV1fNVUznEtT

Okay， let's continue the proof of correctness of our greedy algorithm for minimizing sum of the weighted completion times。

 and let's move on to understanding the ramifications of the exchange of jobs suggested at the conclusion of the previous video。

So recall the basic idea is to use this observation that the optimal schedule Sigma star by virtue of our assumption of being different than the greedy one has to have this pair of consecutive jobs where the earlier one has the higher index。



![](img/03e247b5de07639b102f79c859866297_1.png)

![](img/03e247b5de07639b102f79c859866297_2.png)

So my question for you involves thinking about how the completion times of all of the jobs change after we make this exchange of the two jobs。

 I and J， which ones go up， which ones go down， which ones are unaffected。

 which ones can we not actually predict whether they go up or down。All right。

 so the answer to this quite key question is the third answer。 jobs other than I andJ are unaffected。

 the completion time of job I goes up and the completion time of job J goes down。

 So let's review why consider a job K other than I or J。

 It's probably easiest to see if it ensigma star K completes before I andJ is scheduled earlier than I andJ。

 Don't remember what the completion time of a job is it's just the time that needs to elapse before it gets done。

 So it's some of the job length up to and including that job itself。

 So if k was scheduled before I andJ before it's exactly the same after I andJ is swap。

 you don't know the difference exactly the same set of jobs precedes job K is before So it's completion time is the same。

 But if you think about it， this exact same argument is true for jobs K that succeed I andJ。

 So before we do the swap， it has to wait for a bunch of jobs to complete including I andJ。

 and after we swap I andJ it still has to wait for I andJ to complete。 Yeah。

 they complete an opposite order。 but who cares the amount of time that eapse is exactly the same。

 So importantly。Jobs other than I and J are completely agnostic to the swap their completion time is exactly the same as before so that's the first part so job I its completion time goes up。

 it's easy to see why it used to be before J now it has to wait for J。 In fact。

 we can say exactly how much completion time goes up by it goes up by exactly the length of J。

 that is the extra time which now needs to elapse before I gets completed。

By exactly the same reasoning， the completion time of job J actually drops。

 It has to wait for the same jobs to complete as before， except it no longer has to wait for job I。

 So not only can we say its completion time goes down。

 we can say that it goes down by precisely the length of job I。

 So now we're in a great position to finish off this proof。 Let's summarize what we've got so far。

 So for our cost benefit analysis of exchanging I and J。

 we discovered the cost is limited to an increase in the completion time of job I and the benefit is limited to the decrease in the completion time of job J。

 specifically the cost， the new cost incurred。By the exchange is the weight of job I times the amounts by which its completion time went up。

 namely the length of job J。 Similarlyly， the benefit of the exchange is the drop of LI and J's completion time and that gets multiplied by its weight of WJ。



![](img/03e247b5de07639b102f79c859866297_4.png)

![](img/03e247b5de07639b102f79c859866297_5.png)

So now finally， we're at the point where we can use the fact that this purportedly optimal schedule Sigma star schedules I and J in some sense incorrectly with a higher index job first despite it having a lower ratio in contrast to the principles followed by our greedy algorithm。

 so why is it relevant that the earlier job I has a higher index？



![](img/03e247b5de07639b102f79c859866297_7.png)

Well a higher index corresponds to a lower ratio remember we did this notation switch so that the first job has the highest ratio。

 the second job is the second highest ratio and so on， so the bigger your index。

 the further you are down in the ordering the lower your ratio， so because I is bigger than J。

 it means I's ratio is worse than J。The usefulness of this becomes even more apparent when we clear denominators。

 we multiply both sides by Li times LJ。And then we find that WI times LJ is strictly less than WJ times LI。

 but what of these， these are just the cost and benefit terms respectively of our thought experiment exchange of exchanging INJ。

So what does it mean that the benefit of the swap outweighs the cost。

 it means that if we take Sigma star this purportedly optimal solution and we invert the jobs INJ。

 we get a schedule with an even better weighted sum of completion times。

 but that is nuts That's absurd Sigma star was supposed to be optimal so here's our contradiction that completes the proof。



![](img/03e247b5de07639b102f79c859866297_9.png)