# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P84：-084-Approaches to Testing Chap6 Video 14.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

In testing， our goal is to expose the existence of faults， those human errors in the system。😡。



![](img/ff190d094aa1cb1341eba3969e1efeb6_1.png)

So that they can be fixed and therefore not lead to failures。There are many ways of doing testing。

 the one you're most familiar with by now is unit testing。

 writing small tests for units of a program。

![](img/ff190d094aa1cb1341eba3969e1efeb6_3.png)

In OCll， that's typically a function that we're testing at the unit level。



![](img/ff190d094aa1cb1341eba3969e1efeb6_5.png)

Integration testing is that process of testing how they fit together Do two classes interact in the right way。

 do two OcheMl modules interact in the right way。This is， of course， a little bit more difficult。



![](img/ff190d094aa1cb1341eba3969e1efeb6_7.png)

System testing is at a higher level still， that's the notion of testing whether an entire software system with all of the software pieces that are part of it offer the right functionality。

 enough performance。

![](img/ff190d094aa1cb1341eba3969e1efeb6_9.png)

Acceptance testing is determining whether users believe that it meets their requirements。

 installation testing is testing， whether you can actually install the system in the environments in which it needs to run。

😡。

![](img/ff190d094aa1cb1341eba3969e1efeb6_11.png)

We are mostly just going to focus on unit testing here in this course if you ever go on to do say a master's in software engineering at some other university。

 you will discover you can take entire classes on testing， so it's a rich and deep field。



![](img/ff190d094aa1cb1341eba3969e1efeb6_13.png)

Regression testing is another important component of testing。



![](img/ff190d094aa1cb1341eba3969e1efeb6_15.png)

A regression here means that a previously fixed fault is somehow reintroduced into the code。😡。



![](img/ff190d094aa1cb1341eba3969e1efeb6_17.png)

![](img/ff190d094aa1cb1341eba3969e1efeb6_18.png)

Or to put it another way， you fix a bug one day and then yet somehow the next day that bug is back because somehow it got reintroduced into the codebase maybe that's because you messed up a gi merge or maybe it's because some other programmer didn't realize that the fix had been made and stomped all over it。

😡。

![](img/ff190d094aa1cb1341eba3969e1efeb6_20.png)

![](img/ff190d094aa1cb1341eba3969e1efeb6_21.png)

![](img/ff190d094aa1cb1341eba3969e1efeb6_22.png)

![](img/ff190d094aa1cb1341eba3969e1efeb6_23.png)

So regression testing。Is the process of running tests against new versions of software to ensure that no regressions have occurred？



![](img/ff190d094aa1cb1341eba3969e1efeb6_25.png)

Now， by far， the best way to do this。Is any time you write a unit test that exposes a fault。

Put that unit test into a test suite。And automate the running of it。

You're already doing this more or less with your O unit test suites in this course。

 You put a test into that suite。 It's going to run now and forever。

This is why it's really important to put all of those tests in the suite rather than just finding bugs in Utah and fixing them in the codeb。

😡。

![](img/ff190d094aa1cb1341eba3969e1efeb6_27.png)

When you take that knowledge out of your head that you got from Utah and put it into a test suite。

 you're guaranteeing that in the future should you ever mess up again。

 you're going to catch yourself immediately rather than having a latent fault in the system。

 Here's a fun fact。

![](img/ff190d094aa1cb1341eba3969e1efeb6_29.png)

![](img/ff190d094aa1cb1341eba3969e1efeb6_30.png)

![](img/ff190d094aa1cb1341eba3969e1efeb6_31.png)

What do you think the probability of undetected faults is as a function of the number of detected faults so far？

😡，Suppose there's been a lot of faults found in a system already。

Do you think that makes it more likely that there are still faults to be found or less likely？Well。

 the argument for it to be less likely would be there's only so many faults in the system。

 if I've found a lot of them already， then I'm probably most of the way done。

 there's probably very little left to do。嗯。啊。But that's not so young grasshopper。In fact。

 in studies done both in the late 70s and then repeated in the 2000s。

 the probability of undetected faults increases with the number of detected faults。

So the more bugs that have been found in a system so far。

 the more buggy that system still is likely to be。Now。

 the underlying root cause for this is not exactly understood。

One possibility is that programmers who write buggy code write buggy code。

 and so if you found a lot of faults so far， you're probably still going to find a lot more later on。

It might not just be because they write buggy code。

 it might be because the requirements were ill-spec。

 it might be because the programmer didn't understand them， it might be because when we fix bugs。

 there's a tendency to introduce new bugs right at the same time you go in。

 you patch a line of code and you didn't think deeply enough about that patch and actually at the same time as you're fixing one bug you've introduced to。

😡，So all of these are underlying phenomenon that can explain this statistical fact。

That there is always more bugs to be found if you've found some so far。

The moral act of that story is。Write， correct code first。



![](img/ff190d094aa1cb1341eba3969e1efeb6_33.png)

Don't write buggy code and then fix it later。So when should you stop testing？Well。

 here are some bad answers。The first is when time is up。

 you've just got a limited time to do it and then after an hour you're going to quit。

Another bad answer is when all tests pass， No， that just means you don't have enough tests yet。

 there's still more tests to be written。Perhaps the worst answer is when the 3110 testing Rurick says you're good and you don't need to write anymore because you've got all the points。

It's not about the points， it's about the testing。

![](img/ff190d094aa1cb1341eba3969e1efeb6_35.png)

So what are some good answers？One good answer is that you are following a testing methodology and that methodology has been completed。

We're going to talk about two different types of testing soon here to learn more about that。



![](img/ff190d094aa1cb1341eba3969e1efeb6_37.png)

In the future。We hope that there will eventually be enough research that has been completed on software engineering that we can do statistical estimation。

We'd like to know that the probability of undetected faults is actually low enough。



![](img/ff190d094aa1cb1341eba3969e1efeb6_39.png)

We don't really know how to do that yet， but people are working on。

Perhaps one day when I'm teaching this course in another 20 years。

 I'll be able to cite one of you and you'll have solved this problem for us。



![](img/ff190d094aa1cb1341eba3969e1efeb6_41.png)

![](img/ff190d094aa1cb1341eba3969e1efeb6_42.png)