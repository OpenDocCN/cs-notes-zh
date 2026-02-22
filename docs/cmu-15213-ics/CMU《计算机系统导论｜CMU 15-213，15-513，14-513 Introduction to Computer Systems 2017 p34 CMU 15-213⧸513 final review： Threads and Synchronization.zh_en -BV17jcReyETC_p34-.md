# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p34 CMU 15-213⧸513 final review： Threads and Synchronization.zh_en -BV17jcReyETC_p34-

All rightSo let's just start with the problem statement first， for threads and sechation。

 you have a new setup for TAs where they want to implement a new paradigm for office hours。

 so every time you walk into the room， youll have a table with several pens and notebooks and this is what you're supposed to do with them。



![](img/a55bae44c8e913fd3194e31ed8cc5a92_1.png)

You're going to wait until you're called and then you claim a pen and a notebook。

 then you use a pen to write down your question on the notebook and after you're done writing the question。

 you release a pen。Then you get grab a notebook and wait until the T is able to help you hold the notebook and after you're done talking to the TA。

 the TA wants you to write down the solution again on the notebook just to be sure that you've understood the concept once it're done doing that you release the notebook you release a pen and then you go home so un simpleim right so now as you can see there are several resources here one you have the notebooks to the pen the TAs can be considered a resource here and the students are definitely on the form of resource now how do you manage all the resources in a way such that they don't get deadlock with each other so you need to kind of implement an algorithm using lock。



![](img/a55bae44c8e913fd3194e31ed8cc5a92_3.png)

And make sure that they're not deadlock。So this is kind of a typical code type you're going to use for it。

 so we have a main function， which essentially just largests appeal threads。😊。

So what it does is it initializes with standard setups， say where you have five P， five notebooks。

 three Ts and 50 students and then so what it does is essentially creates some 50 friends representing almost 50 students。

 launches them and waits for them didn't kind of get done。😊。

So this is pretty straightforward and simple like that。



![](img/a55bae44c8e913fd3194e31ed8cc5a92_5.png)

So what happened was a student put some code for it for the worker thread because that's the main part we'd be focusing on and turns out that it works fine most of the time。

 but there is a deadlock once in a while， so the question here is what exactly is causing the deadlock。

Is it A， the deadlock is caused by the pen in the notebook， B。

 is the deadlock caused between the notebook and the TA， or is it C。

 the deadlock is caused between the TA and the10。So。

I'd give you guys a moment to think about it and then you can tell me what do you think and go a few examples out what might happen in each case。

对。Does anybody have an answer？Anybody？对。Raise your hand if you think it's a。

Raise your hand if you think it's B。And how about three。And I guess everyone else doesn't know。

 all right， let's find up。All right， so like I said， you have five pens， five notebooks。

 you have three yearss and 50 students。😊，I'm sorry， it just got affiliated。



![](img/a55bae44c8e913fd3194e31ed8cc5a92_7.png)

Okay let's just consider the case C where you have analyzing the deadlock between pen and TAs so as you can see you take a lock on the pen there and you give it up and then you get a lock on the TA and you give up the TA and can get a lot on the pen and give the pen here so technically there is no overlap here so what that means is there cannot be a case where a student who is talking to your TA is waiting on a pen。

😊，And vice versa， so what that means is a student who is holding a pen will not be waiting on a T ad so they cannot kind of deadlock to each other。

 right？Let's take a look at case B。😡，So there is an overlap here between the Ts and the notebooks。

A student who is holding a notebook may be waiting for a TA。

 but a student who is stopping to your TA will not be waiting on a notebook。

 he would already have the notebook。Right。So again， they cannot dead not。what about case eight？

There is an overlap yes， and turns't out the student who is holding a notebook may be waiting on a pen。

😊，And a student who is holding a fence may be waiting on the notebook。Now like I said。

 there are enough resources， there are five pens and five notebooks。

 so in most cases that probably would not get suck。

 but let's consider a case where you have five students who walk into a room。



![](img/a55bae44c8e913fd3194e31ed8cc5a92_9.png)

And they grab all the pen and they grab all the notebooks。

 and then there are other five students waiting behind them to grab the pen。So these five students。

 they give up the pen and wait on a TA and while they're doing that now five students who came in behind them kept all the pens。

😊，Now， after talking to the T， then it depends to write something on the paper again， right？

So now they cannot get the pen because other five students have taken it and those five students have taken the pen are waiting on the notebook。

 which these five people hold。So they kind of are waiting on each other and no one can move forward。

Does this make sense to everybody？Do you want me to go over this again？One more time。

So let's just consider a case where you have five students who walk into the class。

 they grab all the five pen and all the five notebooks。Now， after writing down the question。

 these five students are waiting on the TAs， so they give up the P。

 the five pens that they have given up are grabbed by the next five students who have now taken the P by waiting on the notebooks。

Now after consulting the TA for some time， these students they need the pen pens again。

 so they need five pens which are being held by five other students who are waiting on the notebook and these are five students here who have the notebook but are waiting on the pen so they're kind of waiting on each other and in that way no one can proceed forward so you have a deadlock there。

So it's answer A。The answer is optionuction A， that is a deadlock can because between the pen and the notebooks。

中国国自有对。Yeah， that's the next part of the problem。All right。



![](img/a55bae44c8e913fd3194e31ed8cc5a92_11.png)

So is there a way we can fix this problem without changing the procedure？Anyone yeah？证据后。



![](img/a55bae44c8e913fd3194e31ed8cc5a92_13.png)

Yes， so you basically reorder the locks in a way。So if we grab the notebook first and then grab the pen and maintain the reverse order here。

 why we releasing it？Things do overlap to an extent， but they're fairly simple。

 so if you do that if you grab the notebook before you take a pen and you release a pen first and then the notebook。

 then you would have a condition where there won't be a condition where a student is holding a pen will already have a notebook right up there。

😊，And a student who is talking to a T will already have a notebook and hence will not be waiting on the pen。

So if you have lock like this， you won't have a student who is waiting on a notebook。

 sorry who is holding a notebook but is waiting on a fan。喂。

So that's kind of about it and so that was a simple question at that。

 but you'd be getting different variance of this particular questions in your exam and it should be pretty straightforward and simple if you can get this one。

啊 pretty easily。Yeah so can we say that when there is an overlap we have to make sure that they're the loss or in the same world so the overlap is not necessarily a condition it's just like kind of an indicated for you to analyze the situation so if ever you see an overlap there you just say for example if I'm talking about this law so you just come here and analyze what are the different things that can be waiting on it or what are the different things that is waiting on before coming to this particular a statement and that's how you going can analyze it。

Can we exhibit it kind of as a rule that？If we do mirror。Unlocking as we did locking。

We won't have a dead or is that not safe to assume typicallyyp a lot of cases you have this thing called ordering of locks。

 so you grab like you kind of have a priority of locks in your head。

 you grab a lock first and then the other and if you maintain that ordering every time you're not guaranteed you not have a deadlock。

 but you tend to prevent deadlocks from happening。

![](img/a55bae44c8e913fd3194e31ed8cc5a92_15.png)